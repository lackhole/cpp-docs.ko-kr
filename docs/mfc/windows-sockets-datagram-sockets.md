---
title: 'Windows 소켓: 데이터 그램 소켓'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
ms.openlocfilehash: 14d33ece66d902b5705e573e9863ea78fff9737f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385288"
---
# <a name="windows-sockets-datagram-sockets"></a>Windows 소켓: 데이터 그램 소켓

이 문서에서는 데이터 그램 소켓을 사용할 수 있는 두 개의 Windows 소켓 유형 중 하나를 설명 합니다. (다른 유형은 합니다 [스트림 소켓](../mfc/windows-sockets-stream-sockets.md).)

데이터 그램 소켓 시퀀싱 하거나 중복 보장 되지 않는 양방향 데이터 흐름을 지원 합니다. 데이터 그램도는 반드시 신뢰할 수 없습니다. 도착 하는 데 실패할 수 있습니다. 잘못 된 순서와 중복 될 수 데이터 그램 데이터가 도착할 수 있습니다 하지만 받는 사람 내부 크기 제한 보다 작은 레코드는 레코드 데이터의에서 경계를 유지 됩니다. 시퀀싱 및 안정성 관리 책임이 있습니다. (안정성 로컬 영역 네트워크 [LAN]에 적합 한 경향이 있지만 등 광역 덜 [WAN] 인터넷과 같은 네트워크.)

데이터 그램은 "연결", 즉, 명시적 연결은 없습니다 설정 됩니다. 지정된 된 소켓 데이터 그램 메시지 보내기 및 지정된 된 소켓에서 메시지를 받을 수 있습니다.

데이터 그램 소켓의 예는 동기화 네트워크의 시스템 클록을 보관 하는 응용 프로그램. 이 어느 정도의 설정에서 데이터 그램 소켓의 추가 기능을 보여 줍니다: 많은 수의 네트워크 주소에 메시지 브로드캐스트 됩니다.

데이터 그램 소켓은 레코드 지향 데이터에 대 한 스트림 소켓 보다 효과적입니다. 데이터 그램 소켓에 대 한 자세한 내용은 Windows SDK에서 사용할 수 있는 Windows Sockets 사양을 참조 하세요.

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows 소켓: 배경](../mfc/windows-sockets-background.md)
