---
title: MFC의 Windows 소켓
ms.date: 11/04/2016
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
ms.openlocfilehash: 44a4838a1cd863bd484701966a156be9f61f8988
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510621"
---
# <a name="windows-sockets-in-mfc"></a>MFC의 Windows 소켓

> [!NOTE]
>  MFC는 Windows 소켓 1을 지원 하지만 [Windows 소켓 2](/windows/win32/WinSock/windows-sockets-start-page-2)는 지원 하지 않습니다. Windows 소켓 2는 windows 98와 함께 처음 제공 되며 Windows 2000에 포함 된 버전입니다.

MFC는 두 개의 MFC 클래스에 합의서 등 Windows 소켓을 사용 하 여 네트워크 통신 프로그램을 작성 하기 위한 두 가지 모델을 제공 합니다. 이 문서에서는 이러한 모델과 MFC 소켓 지원에 대해 자세히 설명 합니다. "소켓"은 통신의 끝점입니다. 응용 프로그램이 네트워크를 통해 다른 Windows 소켓 응용 프로그램과 통신 하는 데 사용 되는 개체입니다.

소켓 개념 [에 대 한 설명을 포함 하 여 windows 소켓에 대 한 자세한 내용은 windows 소켓: 배경](../mfc/windows-sockets-background.md).

##  <a name="_core_sockets_programming_models"></a>소켓 프로그래밍 모델

다음 클래스에서는 두 개의 MFC Windows 소켓 프로그래밍 모델을 지원 합니다.

- `CAsyncSocket`

   이 클래스는 Windows 소켓 API를 캡슐화 합니다. [Casyncsocket](../mfc/reference/casyncsocket-class.md) 은 네트워크 프로그래밍을 알고 있는 프로그래머를 위한 것으로, 소켓 API에 대 한 프로그래밍의 유연성을 향상 시킬 수 있는 프로그래머를 위한 것 이지만, 네트워크 이벤트 알림에 콜백 함수를 편리 하 게 사용할 수 있습니다. 에서 C++사용 하기 위해 개체 지향 형식의 패키지 소켓을 제외 하 고,이 클래스에서 제공 하는 유일한 추가 추상화는 특정 소켓 관련 Windows 메시지를 콜백으로 변환 하는 것입니다. 자세한 내용은 [Windows 소켓: 소켓 알림](../mfc/windows-sockets-socket-notifications.md).

- `CSocket`

   에서 `CAsyncSocket`파생 된이 클래스는 MFC [CArchive](../mfc/reference/carchive-class.md) 개체를 통해 소켓을 사용 하기 위한 높은 수준의 추상화를 제공 합니다. 보관이 포함 된 소켓을 사용 하는 경우 MFC의 파일 serialization 프로토콜을 사용 하는 것과 매우 비슷합니다. 이렇게 하면 `CAsyncSocket` 모델 보다 더 쉽게 사용할 수 있습니다. [CSocket](../mfc/reference/csocket-class.md) 은 Windows 소켓 api를 `CAsyncSocket` 캡슐화 하는의 많은 멤버 함수를 상속 합니다. 이러한 함수 중 일부를 사용 하 고 일반적으로 소켓 프로그래밍을 이해 해야 합니다. 그러나 `CSocket` 는 원시 API 또는 클래스 `CAsyncSocket`를 사용 하 여 직접 수행 해야 하는 통신의 여러 측면을 관리 합니다. 가장 중요 한 `CSocket` 것은의 `CArchive`동기 작업에 필수적인 블로킹 (Windows 메시지의 백그라운드 처리)을 제공 하는 것입니다.

및 개체 만들기 `CSocket` 및 `CAsyncSocket` 사용에 [대 한 자세한 내용은 Windows 소켓: 보관](../mfc/windows-sockets-using-sockets-with-archives.md) 및[Windows 소켓과 함께 소켓 사용: CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)클래스를 사용 합니다.

##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a>Windows 소켓 Dll

Microsoft Windows 운영 체제는 Windows 소켓 DLL (동적 연결 라이브러리)을 제공 합니다. 시각적 C++ 개체는 적절 한 헤더 파일 및 라이브러리와 Windows 소켓 사양을 제공 합니다.

Windows 소켓에 대 한 자세한 내용은 다음을 참조 하세요.

- [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)

- [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)

- [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 소켓: 작업 순서](../mfc/windows-sockets-sequence-of-operations.md)

- [Windows 소켓: 아카이브를 사용하는 소켓의 예](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows 소켓: 소켓과 아카이브를 함께 사용하는 방법](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 소켓: 소켓 클래스에서 파생](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows 소켓: 소켓 알림](../mfc/windows-sockets-socket-notifications.md)

- [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md)

- [Windows 소켓: 바이트 순서 지정](../mfc/windows-sockets-byte-ordering.md)

- [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md)

- [Windows 소켓: 포트 및 소켓 주소](../mfc/windows-sockets-ports-and-socket-addresses.md)

## <a name="see-also"></a>참고자료

[Windows 소켓](../mfc/windows-sockets.md)
