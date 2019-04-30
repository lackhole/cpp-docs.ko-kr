---
title: 'Windows 소켓: 보관이 포함 된 소켓의 작동 방법'
ms.date: 11/19/2018
helpviewer_keywords:
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
ms.openlocfilehash: 3af94bc881276238f1a8d2dbeeee4dca1f173a4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389455"
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Windows 소켓: 보관이 포함 된 소켓의 작동 방법

이 문서에서는 설명 하는 방법을 [CSocket](../mfc/reference/csocket-class.md) 개체를 [CSocketFile](../mfc/reference/csocketfile-class.md) 개체와 [CArchive](../mfc/reference/carchive-class.md) 개체는 Windows 통해 데이터 보내기 및 받기 간소화 하기 위해 결합 됩니다 소켓입니다.

문서 [Windows 소켓: 소켓을 사용 하 여 보관 예가](../mfc/windows-sockets-example-of-sockets-using-archives.md) 표시는 `PacketSerialize` 함수입니다. 보관 개체는 `PacketSerialize` 예제는 MFC에 전달 되는 보관 개체 유사 하 게 작동 [Serialize](../mfc/reference/cobject-class.md#serialize) 함수입니다. 필수 차이점은 소켓의 경우 표준 필요가 보관 파일에 연결 된 [CFile](../mfc/reference/cfile-class.md) 개체 (일반적으로 연결 된 디스크 파일)에 있지만 `CSocketFile` 개체입니다. 디스크 파일에 연결 하는 대신 합니다 `CSocketFile` 개체가 연결 하는 `CSocket` 개체입니다.

`CArchive` 개체 버퍼를 관리 합니다. 저장 (송신) 보관 파일의 버퍼가 가득 찬 경우, 연결 된 `CFile` 개체 버퍼의 내용을 씁니다. 버퍼를 플러시하는 소켓에 연결 하는 보관 파일의 메시지를 보내는 것과 같습니다. 로드 (수신) 보관의 버퍼가 가득 합니다 `CFile` 개체 버퍼를 다시 제공 될 때까지 읽기를 중지 합니다.

클래스 `CSocketFile` 에서 파생 되 `CFile`, 지원 하지 않습니다 하지만 [CFile](../mfc/reference/cfile-class.md) 위치 지정 함수 같은 멤버 함수 (`Seek`, `GetLength`, `SetLength`등), (함수 잠금 `LockRange`하십시오 `UnlockRange`), 또는 `GetPosition` 함수입니다. 모든 합니다 [CSocketFile](../mfc/reference/csocketfile-class.md) 개체를 수행 해야 쓰기 또는 읽기와 관련 된 바이트 시퀀스는 `CSocket` 개체입니다. 파일은 관여 하지 않기 때문에 등의 작업이 `Seek` 및 `GetPosition` 의미가 없습니다. `CSocketFile` 파생 된 `CFile`이므로 이러한 멤버 함수의 모든 일반적으로 상속 됩니다 것입니다. 이 지원 되지 않는 문제를 방지 하려면 `CFile` 에서 멤버 함수를 재정의할 `CSocketFile` throw 하는 [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)합니다.

합니다 `CSocketFile` 개체는 멤버 함수를 호출 해당 `CSocket` 보내거나 데이터를 수신 하는 개체입니다.

다음 그림은 통신의 양쪽 모두에 이러한 개체 간의 관계를 보여 줍니다.

![CArchive, CSocketFile 및 CSocket](../mfc/media/vc38ia1.gif "CArchive, CSocketFile 및 CSocket") <br/>
CArchive, CSocketFile 및 CSocket

이 복잡성의 목적은 소켓의 세부 정보를 직접 관리할 필요가 없도록 하기입니다. 소켓, 파일 및 보관 파일을 만들고 보관 파일에 삽입 하거나 보관 파일에서 추출 하 여 송신 또는 수신 데이터를 시작 합니다. [CArchive](../mfc/reference/carchive-class.md), [CSocketFile](../mfc/reference/csocketfile-class.md), 및 [CSocket](../mfc/reference/csocket-class.md) 백그라운드 세부 사항을 관리 합니다.

`CSocket` 개체는 실제로 두 가지 상태 개체: 경우에 따라 비동기 (일반적인 상태) 및 경우에 따라 동기입니다. 비동기 상태로 소켓 프레임 워크에서 비동기 알림을 받을 수 있습니다. 그러나 데이터를 보내거나 등의 작업 중 소켓 동기 상태가 됩니다. 이 소켓 동기 작업이 완료 될 때까지 비동기 알림의 받을 것을 의미 합니다. 모드를 전환 하기 때문에 예를 들어, 다음과 같이 수행할 수 있습니다.

[!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]

경우 `CSocket` 구현 되지 않았던 두 가지 상태 개체로 이전 알림이 처리 된 하는 동안 동일한 종류의 이벤트에 대 한 추가 알림을 받을 수 수 있습니다. 예를 들어, 발생할 수 있습니다는 `OnReceive` 알림을 처리 하는 동안는 `OnReceive`합니다. 위의 코드 조각에서 추출 `str` 아카이브에서 재귀가 발생할 수 있습니다. 상태를 전환 하 여 `CSocket` 추가 알림을 방지 하 여 재귀를 방지 합니다. 일반적인 규칙은 알림 내에서 알림이 표시 되지 않습니다.

> [!NOTE]
> A `CSocketFile` 없이 (제한 됨) 파일로 사용할 수도 있습니다는 `CArchive` 개체입니다. 기본적으로 `CSocketFile` 생성자 *bArchiveCompatible* 매개 변수가 **TRUE**합니다. 이 보관 파일 사용에 대 한 파일 개체를 지정 합니다. 개체를 사용 하는 파일을 보관 하지 않고, 전달 **FALSE** 에 *bArchiveCompatible* 매개 변수입니다.

"보관 호환 되는" 모드로 `CSocketFile` 개체는 더 나은 성능을 제공 줄이고 "deadlock."의 위험 교착 상태는 송신 및 수신 소켓은 서로 대기 하거나 일반적인 리소스를 대기 하는 경우 발생 합니다. 하는 경우이 상황이 발생할 수 있습니다는 `CArchive` 와 협력 하는 개체를 `CSocketFile` 와 서는 `CFile` 개체. 사용 하 여 `CFile`, 보관 파일을 요청한 것 보다 더 적은 바이트를 수신 하는 경우 파일의 끝에 도달 했음을 가정할 수 있습니다. 그러나 사용 하 여 `CSocketFile`, 데이터를 기반으로 하는 메시지 버퍼에서 여러 메시지를 포함할 수, 있으므로 요청 된 바이트 수보다 적은 받는 파일의 끝을 의미 하지 않습니다. 사용 하 여 처럼이 경우 응용 프로그램 차단 하지 않습니다 `CFile`, 버퍼가 비어 때까지 버퍼에서 메시지 읽기를 계속할 수 있습니다. 합니다 [IsBufferEmpty](../mfc/reference/carchive-class.md#isbufferempty) 함수 `CArchive` 보관 파일의 경우 버퍼의 상태를 모니터링 하는 데 유용 합니다.

자세한 내용은 참조 하세요. [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)<br/>
[CObject::Serialize](../mfc/reference/cobject-class.md#serialize)
