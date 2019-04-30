---
title: 'Windows 소켓: Casyncsocket 클래스 사용'
ms.date: 11/04/2016
f1_keywords:
- CAsyncSocket
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
ms.openlocfilehash: 51274791393d95517bd8de5ae7248dc634018037
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399566"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows 소켓: Casyncsocket 클래스 사용

이 문서에서는 클래스를 사용 하는 방법에 설명 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)합니다. 이 클래스는 매우 낮은 수준의 Windows Sockets API 캡슐화를 알아야 합니다. `CAsyncSocket` 네트워크 통신을 자세히 알고 있어야 하지만 네트워크 이벤트 알림에 대 한 콜백 편리 하 게 하는 프로그래머에 게 사용 됩니다. 이 가정에 따라이 문서에서는 기본 지침만 제공 합니다. 아마도 사용을 고려해 야 있습니다 `CAsyncSocket` Windows 소켓의 MFC 응용 프로그램에서 여러 네트워크 프로토콜을 사용 하 여 처리 편의성 유연성을 희생 하지 않으려는 경우. 클래스의 보다 일반적인 대체 모델에 사용 하 여 없습니다 것 보다 직접 직접 자세한 통신을 프로그래밍 하 여 더 나은 효율성을 가져올 수 있습니다도 수 수 있다고 생각 `CSocket`합니다.

`CAsyncSocket` 에 설명 되어는 *MFC 참조*합니다. Visual C++ Windows SDK에는 Windows Sockets 사양을 제공 합니다. 세부 정보에 남아 있습니다. Visual C++ 에 대 한 샘플 응용 프로그램을 제공 하지 않습니다 `CAsyncSocket`합니다.

클래스를 사용 하 여 네트워크 통신에 대 한 지식이 없는 하는 간단한 솔루션이 필요한 경우 [CSocket](../mfc/reference/csocket-class.md) 사용 하 여를 `CArchive` 개체입니다. 참조 [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../mfc/windows-sockets-using-sockets-with-archives.md) 자세한 내용은 합니다.

이 문에서는 다음과 같은 내용을 설명합니다.

- 만들기 및 사용을 `CAsyncSocket` 개체입니다.

- [CAsyncSocket 사용 하 여 사용자의 책임](#_core_your_responsibilities_with_casyncsocket)합니다.

##  <a name="_core_creating_and_using_a_casyncsocket_object"></a> 만들기 및 CAsyncSocket 개체를 사용 합니다.

#### <a name="to-use-casyncsocket"></a>CAsyncSocket를 사용 하려면

1. 생성 된 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 개체를 사용 하는 개체의 내부 **소켓** 처리 합니다.

   소켓 만들기 2 단계 생성의 MFC 패턴을 따릅니다.

   예를 들어:

   [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]

     또는

   [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]

   위의 첫 번째 생성자는 만듭니다는 `CAsyncSocket` 스택의 개체입니다. 두 번째 생성자는 만듭니다는 `CAsyncSocket` 힙에 합니다. 첫 번째 [만들기](../mfc/reference/casyncsocket-class.md#create) 호출 위의 기본 매개 변수를 사용 하 여 스트림 소켓을 만듭니다. 두 번째 `Create` 호출은 지정 된 포트와 주소를 사용 하 여 데이터 그램 소켓을 만듭니다. (사용할 수 있습니다 `Create` 생성 방법 중 하나를 사용 하 여 버전입니다.)

   매개 변수를 `Create` 됩니다.

   - "Port": 정수 (short)입니다.

         For a server socket, you must specify a port. For a client socket, you typically accept the default value for this parameter, which lets Windows Sockets select a port.

   - 소켓 유형: **SOCK_STREAM** (기본값) 또는 **SOCK_DGRAM**합니다.

   - "Address" 형식인"또는"128.56.22.8"와 같은 소켓입니다.

         This is your Internet Protocol (IP) address on the network. You will probably always rely on the default value for this parameter.

   용어 "port" 및 "소켓 주소" [Windows 소켓: 포트 및 소켓 주소](../mfc/windows-sockets-ports-and-socket-addresses.md)합니다.

1. 소켓이 클라이언트인 경우 소켓 개체 서버에 연결 소켓을 사용 하 여 [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect)합니다.

     또는

   소켓이 서버인 경우 수신 대기를 시작 소켓 설정 (사용 하 여 [CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen)) 클라이언트에서 연결 시도를 합니다. 적용 사용 하 여 연결 요청을 받으면 [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept)합니다.

   연결을 허용한 후 암호 유효성 검사 등의 작업을 수행할 수 있습니다.

    > [!NOTE]
    >  합니다 `Accept` 멤버 함수는 비어 있는 새에 대 한 참조 `CSocket` 매개 변수로 개체입니다. 호출 하기 전에이 개체를 생성 해야 `Accept`합니다. 이 소켓 개체가 범위를 벗어나면 연결이 닫힙니다. 호출 하지 마십시오 `Create` 이 새 소켓 개체에 대 한 합니다. 예를 들어 문서를 참고 [Windows 소켓: 작업 시퀀스](../mfc/windows-sockets-sequence-of-operations.md)합니다.

1. 호출 하 여 다른 소켓와의 통신을 수행 합니다 `CAsyncSocket` Windows Sockets API 함수를 캡슐화 하는 개체의 멤버 함수입니다.

   Windows 소켓 사양 및 클래스를 참조 하세요 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 에 *MFC 참조*합니다.

1. 삭제 된 `CAsyncSocket` 개체입니다.

   스택에 소켓 개체를 만든 경우 포함 하는 범위를 벗어나면 해당 소멸자가 호출 됩니다. 힙에 소켓 개체를 만든 경우 사용 하는 **새** 연산자를 담당 하는 사용 하 여를 **삭제** 개체를 제거 하는 연산자입니다.

   개체의를 호출 하는 소멸자 [닫기](../mfc/reference/casyncsocket-class.md#close) 멤버 함수는 개체를 제거 하기 전에 합니다.

코드에서이 시퀀스의 예 (에 실제로 `CSocket` 개체)를 참조 하세요 [Windows 소켓: 작업 시퀀스](../mfc/windows-sockets-sequence-of-operations.md)합니다.

##  <a name="_core_your_responsibilities_with_casyncsocket"></a> CAsyncSocket 사용 하 여 사용자의 책임

클래스의 개체를 만들 때 [CAsyncSocket](../mfc/reference/casyncsocket-class.md), 개체를 Windows 캡슐화 **소켓** 처리 하 고 해당 핸들에 대 한 작업을 제공 합니다. 사용 하는 경우 `CAsyncSocket`, 직접 API를 사용 하는 경우 발생할 수 있습니다 하는 모든 문제를 사용 하 여 처리 해야 합니다. 예를 들어:

- "차단" 시나리오입니다.

- 보내는 컴퓨터와 받는 컴퓨터 간에 바이트 순서 차이입니다.

- 유니코드 및 멀티 바이트 문자 간 변환 (MBCS) 문자열을 설정 합니다.

이러한 용어와 추가 정보는 정의 참조 하세요. [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md), [Windows 소켓: 바이트 순서](../mfc/windows-sockets-byte-ordering.md), [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md)합니다.

이러한 문제가 발생 하더라도 클래스 `CAsycnSocket` 응용 프로그램에 필요한 모든 유연성 및 제어를 얻을 수 있습니다 하는 경우를 올바른 선택 일 수 있습니다. 클래스를 사용 해야 하는 그렇지 않은 경우 `CSocket` 대신 합니다. `CSocket` 많은 세부 정보를 숨깁니다: it에 대 한 액세스를 펌프 Windows 호출을 차단 하는 동안 메시지를 사용 하면 `CArchive`, 바이트 순서 차이점과 문자열 변환이 관리 하는 합니다.

자세한 내용은 다음을 참조하세요.

- [Windows 소켓: 배경](../mfc/windows-sockets-background.md)

- [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)

- [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)
