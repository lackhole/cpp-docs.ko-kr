---
title: 'Windows 소켓: 아카이브를 사용 하는 소켓의 예'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], with archives
- examples [MFC], Windows Sockets
- Windows Sockets [MFC], with archives
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
ms.openlocfilehash: 4ea1e2911b156066360da09993fa7302db79f12b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305296"
---
# <a name="windows-sockets-example-of-sockets-using-archives"></a>Windows 소켓: 아카이브를 사용 하는 소켓의 예

이 문서에서는 클래스를 사용 하는 예제를 보여 줍니다 [CSocket](../mfc/reference/csocket-class.md)합니다. 이 예제에서는 사용 하 여 `CArchive` 소켓을 통해 데이터를 serialize 할 개체입니다. 문서 serialization 파일에서 아님을 note 합니다.

다음 예제에서는 보관 파일을 통해 데이터를 받고 보내는 데 사용 되는 방법을 설명 `CSocket` 개체입니다. 이 예제는 (동일한 컴퓨터에서 또는 네트워크에서 서로 다른 컴퓨터에서) 응용 프로그램의 두 인스턴스 데이터를 교환할 수 있도록 설계 되었습니다. 하나의 인스턴스가 다른 인스턴스에서 수신 하 고 승인 하는 데이터를 보냅니다. 응용 프로그램에서 교환을 초기화 하 고 서버로 또는 다른 응용 프로그램에는 클라이언트로 작동할 수 있습니다 하나입니다. 다음 함수는 응용 프로그램의 뷰 클래스에서 정의 됩니다.

[!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/cpp/windows-sockets-example-of-sockets-using-archives_1.cpp)]

가장 중요 한 점은이 예제는 해당 구조는 MFC의 철자와 병렬 `Serialize` 함수입니다. `PacketSerialize` 이루어져 있습니다 멤버 함수는 **하는 경우** 사용 하 여 문을 **다른** 절. 두 함수가 받을 [CArchive](../mfc/reference/carchive-class.md) 매개 변수로 참조: *arData* 하 고 *arAck*합니다. 경우는 *arData* 보관 개체 저장 (송신)에 대해 설정 됩니다는 **경우** 분기가 실행 되며; 않으면 *arData* 설정 됩니다 (수신)를 로드 하기 위한 함수가 사용 합니다 **다른** 분기 합니다. MFC의 serialization에 대 한 자세한 내용은 참조 하세요. [Serialization](../mfc/how-to-make-a-type-safe-collection.md)합니다.

> [!NOTE]
>  합니다 *arAck* 보관 개체의 반대로 간주 됩니다 *arData*합니다. 경우 *arData* 전송입니다 *arAck* 를 수신 하며 그 반대도 마찬가지로 적용 됩니다.

전송에 대 한 예제 함수는 지정 된 횟수, 데모용으로 난수 데이터가 생성 될 때마다 루프입니다. 응용 프로그램은 파일 등의 일부 원본에서 실제 데이터를 가져옵니다. 합니다 *arData* 보관의 삽입 연산자 (**<<**) 데이터의 세 개의 연속 된 청크의 스트림을 보내는 데 사용 됩니다.

- "헤더" 데이터의 특성을 지정 하는 (이 경우 값을 *bValue* 변수와 복사본 개수를 받게 됩니다).

   이 예제에 대 한 두 항목은 임의로 생성 됩니다.

- 지정 된 데이터의 복사본 수입니다.

   내부 **에 대 한** 보냅니다 루프 *bValue* 지정 된 횟수입니다.

- 라는 문자열이 *strText* 수신자가 해당 사용자에 게 표시 하는 합니다.

수신 함수는 비슷하게 작동에 보관 추출 연산자를 사용 하 여 (**>>**) 보관 파일에서 데이터를 가져옵니다. 수신 응용 프로그램이 표시할 보내는 응용 프로그램에 대 한 데이터를 수신, 최종 "Received" 메시지를 표시 하 고 "전송" 라는 메시지를 다시 보냅니다를 확인 합니다.

이 통신 모델에서 "Received" 라는 단어에서 메시지가 전송 된 *strText* , 변수가 통신의 한쪽 끝에 표시 하기 위해 특정 개수의 데이터 패킷 셨 기를 받는 사용자에 게 지정 수신 합니다. 수신자는 원래 보낸 사람의 화면에서 "전송"을 표시 하기 위해 라는 비슷한 문자열을 사용 하 여 회신 합니다. 두 문자열의 수신 통신이 성공이 발생 했음을 나타냅니다.

> [!CAUTION]
>  설정된(MFC 이외) 서버와 통신하도록 MFC 클라이언트 프로그램을 작성하는 경우 아카이브를 통해 C++ 개체를 전송하지 마십시오. 서버에 전송 하려는 개체 종류를 인식 하는 MFC 응용 프로그램 아닌 수신 하 고 개체를 deserialize 할 수 없습니다. 문서에 예로 [Windows 소켓: 바이트 순서](../mfc/windows-sockets-byte-ordering.md) 이 형식의 통신을 보여 줍니다.

자세한 내용은 Windows Sockets 사양을 참조: **htonl**를 **htons**를 **ntohl**를 **ntohs**합니다. 또한 자세한 내용은 다음을 참조 합니다.

- [Windows 소켓: 소켓 클래스에서 파생](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows 소켓: 소켓과 아카이브를 함께 사용하는 방법](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows 소켓: 배경](../mfc/windows-sockets-background.md)

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)<br/>
[CArchive::IsStoring](../mfc/reference/carchive-class.md#isstoring)<br/>
[CArchive::operator <<](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive::operator >>](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive::Flush](../mfc/reference/carchive-class.md#flush)<br/>
[CObject::Serialize](../mfc/reference/cobject-class.md#serialize)
