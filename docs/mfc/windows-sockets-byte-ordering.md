---
title: 'Windows 소켓: 바이트 순서 지정'
ms.date: 11/04/2016
helpviewer_keywords:
- byte order issues in sockets programming
- sockets [MFC], byte order issues
- Windows Sockets [MFC], byte order issues
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
ms.openlocfilehash: ca572ad32a9a46756cacf0221d80b2953b710723
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217573"
---
# <a name="windows-sockets-byte-ordering"></a>Windows 소켓: 바이트 순서 지정

이 문서 및 두 개의 참조 문서에서는 Windows 소켓 프로그래밍의 몇 가지 문제를 설명합니다. 이 문서에서는 바이트 순서에 대해 설명 합니다. 다른 문제는 문서에 적용 됩니다. [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md) 고 [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md)합니다.

사용 하거나 클래스에서 파생 되는 경우 [CAsyncSocket](../mfc/reference/casyncsocket-class.md), 이러한 문제를 직접 관리 해야 합니다. 사용 하거나 클래스에서 파생 되는 경우 [CSocket](../mfc/reference/csocket-class.md), MFC를 관리 합니다.

## <a name="byte-ordering"></a>바이트 순서 지정

다양 한 컴퓨터 아키텍처는 경우에 따라 서로 다른 바이트 순서를 사용 하 여 데이터를 저장 합니다. 예를 들어 Intel 기반 컴퓨터 (Motorola) Macintosh 컴퓨터의 반대 순서로 데이터를 저장 합니다. "Little-endian" 이라는 Intel 바이트 순서를 네트워크 표준 "Big-endian" 순서의 반대로 이기도 합니다. 다음 표에서 이러한 용어를 설명 합니다.

### <a name="big--and-little-endian-byte-ordering"></a>큰-및 Little Endian 바이트 순서 지정

|바이트 순서 지정|의미|
|-------------------|-------------|
|Big Endian|최상위 바이트 단어의 왼쪽된 끝에 있는 경우|
|Little Endian|최상위 바이트 단어의 오른쪽 끝에 있는 경우|

일반적으로 네트워크를 통해 송수신 하는 데이터에 대 한 바이트 순서로 변환에 걱정할 필요가 없습니다 있지만 바이트 순서를 변환 해야 하는 경우가 있습니다.

## <a name="when-you-must-convert-byte-orders"></a>바이트 순서를 변환 해야 하는 경우

다음과 같은 상황에서 바이트 순서를 변환 해야 합니다.

- 네트워크를 다른 컴퓨터로 보내는 데이터와 반대로 함으로써 해석 해야 하는 정보를 전달 합니다. 전달 하면 예를 들어, 포트 및 주소는 네트워크 이해 해야 합니다.

- 통신 하는 서버 응용 프로그램을 MFC 응용 프로그램이 아닙니다. (및에 대 한 소스 코드가 없는). 두 컴퓨터가 동일한 바이트 순서를 공유 하지 않을 경우 바이트 순서 변환을 호출 합니다.

## <a name="when-you-do-not-have-to-convert-byte-orders"></a>바이트 순서를 변환할 필요가 없습니다 경우

다음과 같은 경우에는 바이트 순서를 변환 하는 작업을 방지할 수 있습니다.

- 양쪽의 컴퓨터 수에 동의 하지 않고 바이트를 교환 하 고 두 컴퓨터가 모두 같은 바이트 순서를 사용 합니다.

- 통신 하는 서버에는 MFC 응용 프로그램입니다.

- 알릴 수 있도록 명시적으로 여부 바이트 순서를 변환 해야 하는지 여부를 통신 하는 서버에 대 한 소스 코드를 해야 합니다.

- MFC에 서버를 이식할 수 있습니다. 를 위해 매우 간단 하 고 결과 일반적으로 빠르고 작은 코드.

작업할 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)를 필요한 바이트 순서로 변환 모든 직접 관리 해야 합니다. Windows 소켓 "Big-endian" 바이트 순서 모델을 표준화 하 고이 순서와 다른 변환 함수를 제공 합니다. [CArchive](../mfc/reference/carchive-class.md)하지만 함께 사용 하면 [CSocket](../mfc/reference/csocket-class.md), 반대 ("Endian") 순서를 사용 하 하지만 `CArchive` 바이트 순서 변환 세부 사항을 처리 합니다. 이 응용 프로그램에서 표준 순서를 지정 하거나 Windows Sockets 바이트 순서로 변환 함수를 사용 하 여 사용 가능한 코드를 만들 수 있습니다.

통신의 양쪽을 작성 하는 경우 MFC 소켓을 사용 하기 위한 이상적인 사례: 양쪽 끝에서 MFC를 사용 합니다. Windows 소켓 변환 루틴 를사용하여와통신하는FTP서버와같은비MFC응용프로그램,바이트스왑직접보관개체에데이터를전달하기전에관리아마도해야하는응용프로그램을작성하는경우**ntohs**, **ntohl**하십시오 **htons**, 및 **htonl**. 비 MFC 응용 프로그램을 사용 하 여 통신에 사용 되는 이러한 함수의 예는이 문서의 뒷부분에 표시 됩니다.

> [!NOTE]
>  MFC 응용 프로그램 통신의 한쪽 끝 없는 경우 또한 하지 않도록 해야 스트리밍 C++ 에서 파생 된 개체 `CObject` 보관에 수신자가 처리할 수 없기 때문입니다. 참고 [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../mfc/windows-sockets-using-sockets-with-archives.md)입니다.

바이트 순서에 대 한 자세한 내용은 Windows SDK에서 사용할 수 있는 Windows Sockets 사양을 참조 하세요.

## <a name="a-byte-order-conversion-example"></a>바이트 순서로 변환 예제

다음 예제에 대 한 serialization 함수는 `CSocket` 보관을 사용 하는 개체입니다. Windows 소켓 API에서 바이트 순서로 변환 함수를 사용 하 여 보여 줍니다.

이 예제 시나리오를 작성 하는 소스 코드에 액세스할 수 없는 해야 하는 비 MFC 서버 응용 프로그램과 통신 하는 클라이언트를 제공 합니다. 이 시나리오에서는 비 MFC 서버는 표준 네트워크 바이트 순서로 가정해 야 합니다. MFC 클라이언트 응용 프로그램에서 사용 하는 반면를 `CArchive` 개체를 `CSocket` 개체 및 `CArchive` "Little-endian" 바이트 순서를 반대로 표준 네트워크를 사용 합니다.

통신 하려는 비 MFC 서버에 다음과 같은 메시지 패킷에 대 한 프로토콜을 설정된 한다고 가정 합니다.

[!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_1.cpp)]

MFC 말해에서이 다음과 같이 표시 됩니다.

[!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_2.cpp)]

C++, **구조체** 클래스와 동일한 작업을 기본적으로 됩니다. 합니다 `Message` 구조는 등 멤버 함수를 가질 수는 `Serialize` 위에 선언 된 멤버 함수입니다. `Serialize` 멤버 함수는 다음과 비슷합니다.

[!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_3.cpp)]

한쪽에서 비 MFC 서버 응용 프로그램의 경우 바이트 순서 간에 분명 한 불일치가 있기 때문에이 예제에서는 데이터의 바이트 순서로 변환에 대 한 호출 및 `CArchive` 반대쪽 MFC 클라이언트 응용 프로그램에서 사용 합니다. 이 예제에서는 다양 한 Windows 소켓을 제공 하는 바이트 순서로 변환 함수를 보여 줍니다. 다음 표에서 이러한 함수에 설명 합니다.

### <a name="windows-sockets-byte-order-conversion-functions"></a>Windows 소켓 바이트 순서로 변환 함수

|함수|용도|
|--------------|-------------|
|**ntohs**|호스트 바이트 순서로 (big Endian을 little Endian) 네트워크 바이트 순서에서 16 비트 수량을 변환 합니다.|
|**ntohl**|네트워크 바이트 순서에서 호스트 바이트 순서로 (big Endian을 little Endian)는 32 비트 수량을 변환 합니다.|
|**Htons**|호스트 바이트 순서에서 네트워크 바이트 순서로 (하도록 Little-endian big Endian)는 16 비트 수량을 변환 합니다.|
|**Htonl**|호스트 바이트 순서에서 네트워크 바이트 순서로 (하도록 Little-endian big Endian)는 32 비트 수량을 변환 합니다.|

이 예의 다른 지점은 통신의 한쪽 끝에 소켓 응용 프로그램 비 MFC 응용 프로그램을 경우 피해 야 할 다음과 유사 하 게 수행 하는:

`ar << pMsg;`

여기서 `pMsg` 에 대 한 포인터를 C++ 클래스에서 파생 된 개체 `CObject`합니다. MFC 응용 프로그램을 마치 것 처럼이 개체 및 서버와 관련 된 추가 MFC 정보를 이해 하지 못하기 보내집니다.

자세한 내용은 다음을 참조하세요.

- [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 소켓: 배경](../mfc/windows-sockets-background.md)

- [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)

- [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)
