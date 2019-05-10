---
title: 'Windows 소켓: Stream 소켓'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- stream sockets [MFC]
ms.assetid: 31faaa34-a995-493f-a30b-b8115293d619
ms.openlocfilehash: 91f06c4a36e76638708edf085987e51418913fd6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337832"
---
# <a name="windows-sockets-stream-sockets"></a>Windows 소켓: Stream 소켓

이 문서에서는 스트림 소켓을 사용할 수 있는 두 개의 Windows 소켓 유형 중 하나를 설명 합니다. (다른 유형은 합니다 [데이터 그램 소켓](../mfc/windows-sockets-datagram-sockets.md).)

레코드 허물기 데이터 흐름에 대 한 Stream 소켓 제공: 양방향 바이트 스트림을 (응용 프로그램은 전체 이중: 수 모두 전송 하 고 소켓을 통해 수신). 스트림 시퀀스에서 중복 되지 않은 데이터를 전달할 의존할 수 있습니다. ("시퀀스" 의미는 패킷이 보낸 순서 대로 배달 합니다. "중복 되지 않은" 의미 특정 패킷을 한 번만 얻을 수 있습니다.) Stream 메시지 수신을 보장 되며 스트림을 많은 양의 데이터를 처리 하는 것이 적합 합니다.

네트워크 전송 계층 나눌 수도 적절 한 크기의 패킷을 데이터를 그룹화 합니다. `CSocket` 압축 및 수에 대 한 압축을 푼 클래스 처리 됩니다.

스트림을 기반으로 명시적 연결: 소켓은 소켓 B에 대 한 연결 요청 B 소켓 수락 하거나 연결 요청을 거부 합니다.

전화 통화를 스트림에 대 한 좋은 비유를 제공합니다. 정상적인 상황에서는 수신 파티는 말할지 모르겠지만, 중복 되거나 손실 없이 순서 대로 말하는 듣게 됩니다. Stream 소켓에 적합 한, 예를 들어, 구현 같은 전송 프로토콜 FTP (파일), 전송 ASCII 또는 임의 크기의 이진 파일을 용이 하 게 합니다.

데이터 도착 하도록 보장 되어야 하는 경우 및 데이터 크기가 크면 Stream 소켓은 데이터 그램 소켓에 것이 좋습니다. 스트림 소켓에 대 한 자세한 내용은 Windows Sockets 사양을 참조 하세요. Windows SDK에서 사용할 수 있습니다.

스트림 소켓을 사용 하 여 응용 프로그램 때문에 네트워크에서 받은 모든 소켓으로 브로드캐스트에 대 한 데이터 그램 소켓을 사용 하도록 설계 방법 보다 우수 수 있습니다.

- 브로드캐스트 모델 네트워크 flood (또는 "storm") 문제가 될 수 있습니다.

- 이후에 채택 클라이언트-서버 모델을 더 효율적입니다.

- 스트림 모델은 신뢰할 수 있는 데이터를 전송 하지 데이터 그램 모델을 제공 합니다.

- 최종 모델 활용 통신할 수 있도록 유니코드 및 ANSI 간 소켓 응용 프로그램 클래스 CArchive 클래스 CSocket 적합 합니다.

    > [!NOTE]
    >  클래스를 사용 하는 경우 `CSocket`, 스트림을 사용 해야 합니다. 으로 소켓 형식을 지정 하면 MFC 어설션이 실패 **SOCK_DGRAM**합니다.

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows 소켓: 배경](../mfc/windows-sockets-background.md)
