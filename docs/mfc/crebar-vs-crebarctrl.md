---
title: Crebar와 CReBarCtrl
ms.date: 11/04/2016
f1_keywords:
- CReBar
- CReBarCtrl
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
ms.openlocfilehash: a1b5cda729e760246449bf197fdc9b32752b96e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241789"
---
# <a name="crebar-vs-crebarctrl"></a>Crebar와 CReBarCtrl

MFC는 rebars 만들려는 두 클래스를 제공 합니다. [CReBar](../mfc/reference/crebar-class.md) 하 고 [CReBarCtrl](../mfc/reference/crebarctrl-class.md) (하는 Windows 공용 컨트롤 API를 래핑하여). `CReBar` rebar 공용 컨트롤의 기능을 모두 제공 수에 대 한 다양 한 일반적인 필수 컨트롤 설정 및 구조를 처리 합니다.

`CReBarCtrl` Win32 rebar 컨트롤에 대 한 래퍼 클래스 이며 쉽게 rebar MFC 아키텍처에 통합 하려는 경우 구현할 수 있습니다. 사용 하려는 경우 `CReBarCtrl` rebar MFC 아키텍처에 통합 하 고, rebar 컨트롤 조작 MFC에 전달할 추가 주의 해야 합니다. 이 통신; 어렵지 않습니다. 그러나 사용 하는 경우에 필요 없는 추가 작업 것 `CReBar`입니다.

Visual C++ rebar 공용 컨트롤을 활용 하려면 두 가지 방법을 제공 합니다.

- 사용 하 여 크기 조정 막대를 만들 `CReBar`, 다음 호출 [CReBar::GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl) 에 액세스 하는 `CReBarCtrl` 멤버 함수입니다.

    > [!NOTE]
    >  `CReBar::GetReBarCtrl` 캐스팅 하는 인라인 멤버 함수는 **이** rebar 개체의 포인터입니다. 즉, 런타임에 함수 호출 오버 헤드가 없습니다.

- 사용 하 여 rebar 만듭니다 [CReBarCtrl](../mfc/reference/crebarctrl-class.md)의 생성자입니다.

두 방법 중 하나는 rebar 컨트롤의 멤버 함수에 액세스할 수 있습니다. 호출 하는 경우 `CReBar::GetReBarCtrl`에 대 한 참조를 반환 하는 `CReBarCtrl` 개체 멤버 함수의 집합 중 하나를 사용할 수 있습니다. 참조 [CReBar](../mfc/reference/crebar-class.md) 생성 하 고 사용 하 여 rebar에 대 한 내용은 `CReBar`합니다.

## <a name="see-also"></a>참고자료

[CReBarCtrl 사용](../mfc/using-crebarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
