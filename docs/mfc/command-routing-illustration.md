---
title: 명령 라우팅 설명
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- command routing [MFC], OnCmdMsg handler
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
ms.openlocfilehash: 56d131151f2284f12a3b46a9acd3cfbd3c8b0f47
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164880"
---
# <a name="command-routing-illustration"></a>명령 라우팅 설명

예를 들어 MDI 응용 프로그램의 편집 메뉴에서 메뉴 항목을 모두 지우기에서 명령 메시지를 것이 좋습니다. 이 명령에 대 한 처리기 함수를 이런 경우 응용 프로그램의 문서 클래스의 멤버 함수에 있다고 가정 합니다. 메뉴 항목을 선택한 후 해당 명령에 해당 처리기 도달 하는 방법을 다음과 같습니다.

1. 주 프레임 창 명령 메시지를 먼저 받습니다.

1. 주 MDI 프레임 창은 현재 활성 상태인 MDI 자식 창의 명령을 처리할 수 있는 기회를 제공 합니다.

1. MDI 자식 프레임 창에 표준 라우팅 파악할 해당 기회 명령에 자신의 메시지 맵을 확인 하기 전에 합니다.

1. 뷰를 먼저 자신의 메시지 맵을 확인 하 고, 처리기를 찾는 다음에 라우팅하여 해당 명령을 관련된 문서.

1. 처리기는 문서를 자신의 메시지 맵을 확인 합니다. 이 문서 구성원 함수가 호출 되 고 라우팅이 중단 합니다.

문서에 처리기를이 없는 경우 해당 서식 파일에 명령을 라우팅합니다 다음 것입니다. 다음 명령은 보기와 프레임 창에 반환 됩니다. 마지막으로, 프레임 창에는 자신의 메시지 맵을 확인 합니다. 주 MDI 프레임 창으로 다시 및 응용 프로그램 개체에 다음 명령을 확인도 실패 한 경우 라우트됩니다-최종 대상을 처리 되지 않은 명령입니다.

## <a name="see-also"></a>참고자료

[프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)
