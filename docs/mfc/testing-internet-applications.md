---
title: 인터넷 응용 프로그램 테스트
ms.date: 11/04/2016
helpviewer_keywords:
- Web applications [MFC], testing
- debugging Web applications [MFC], testing applications
- testing [MFC], Internet applications
- debugging [MFC], Web applications
- Internet debugging and testing
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
ms.openlocfilehash: e582fd006a49e672fb21c86b054b8d35f489698f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306472"
---
# <a name="testing-internet-applications"></a>인터넷 응용 프로그램 테스트

특히 웹 서버에서 실행 중인 응용 프로그램에 대 한 인터넷에서 고유한 몇 가지 테스트 방법이 있습니다. 초기 테스트 아마도 할 것 테스트 서버에 연결 하는 단일 사용자 클라이언트를 사용 하 여 합니다. 이 코드를 디버깅에 유용 합니다.

실제 조건에서 테스트 하고자: 고속 연결 뿐만 아니라 낮은 고속 직렬 회선을 통해 연결 된 여러 클라이언트를 사용 하 여 모뎀 연결을 포함 합니다. 실제 조건을 시뮬레이션 하기 어려울 수 있습니다 하지만 가치가 분명히 시간 디자인 가능한 시나리오를 소비 하 고 실행 합니다. 가능 하면 수행 용량 및 스트레스 테스트 도구를 사용 하려고도 합니다. 특정 부류의 버그 타이밍 버그와 같은 찾으려고 하 고 재현 하기 어렵습니다.

인터넷 프로그래밍의 과제 중 하나는 가시성 합니다. 사이트에 여러 액세스 서버 느려질 수 있습니다. 정상적으로 저하 될 서버를 배치할 수 있습니다. 응용 프로그램 (예: 레지스트리에 쓰는 동안 또는 클라이언트에서 쿠키를 작성 하는 동안 데이터 손상) 하지 못하면 사용자의 컴퓨터에 안전 하지 않은 수 있는 모든 것을 방지 하려고 합니다.

## <a name="see-also"></a>참고자료

[MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)
