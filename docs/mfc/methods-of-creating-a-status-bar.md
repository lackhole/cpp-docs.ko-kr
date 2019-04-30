---
title: 상태 표시줄을 만드는 방법
ms.date: 11/04/2016
helpviewer_keywords:
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
ms.openlocfilehash: a2301301d0012bd93ffedd0452dec140174402e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383895"
---
# <a name="methods-of-creating-a-status-bar"></a>상태 표시줄을 만드는 방법

MFC 상태 표시줄을 만드는 두 가지 클래스를 제공 합니다. [CStatusBar](../mfc/reference/cstatusbar-class.md) 하 고 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) (하는 Windows 공용 컨트롤 API를 래핑하여). `CStatusBar` 모든 기능을 제공 모음 공용 컨트롤 상태에 대 한 자동으로 상호 작용 하는 메뉴 및 도구 모음 및 있습니다;에 대 한 다양 한 일반적인 필수 컨트롤 설정 및 구조 처리 그러나 결과 실행 파일 일반적으로 보다 커지는 경우가 사용 하 여 만든 `CStatusBarCtrl`합니다.

`CStatusBarCtrl` 일반적으로 결과를 더 작은 실행 파일을 사용할 수도 `CStatusBarCtrl` 상태 표시줄을 MFC 아키텍처에 통합 하려는 경우. 사용 하려는 경우 `CStatusBarCtrl` 및 상태 표시줄을 MFC 아키텍처 통합, 상태 표시줄을 MFC 컨트롤 조작에 전달할 추가 주의 해야 합니다. 이 통신; 어렵지 않습니다. 그러나 사용 하는 경우에 필요 없는 추가 작업 것 `CStatusBar`입니다.

Visual C++ 상태 표시줄 공용 컨트롤을 활용 하려면 두 가지 방법을 제공 합니다.

- 상태 표시줄을 만드는 `CStatusBar`, 다음 호출 [CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl) 에 액세스 하는 `CStatusBarCtrl` 멤버 함수입니다.

- 상태 표시줄을 만드는 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)의 생성자입니다.

두 방법 중 하나는 상태 표시줄 컨트롤의 멤버 함수에 액세스할 수 있습니다. 호출 하는 경우 `CStatusBar::GetStatusBarCtrl`에 대 한 참조를 반환 하는 `CStatusBarCtrl` 개체 멤버 함수의 집합 중 하나를 사용할 수 있습니다. 참조 [CStatusBar](../mfc/reference/cstatusbar-class.md) 정보를 생성 하 고 상태를 사용 하 여 표시줄을 만드는 방법에 대 한 `CStatusBar`합니다.

## <a name="see-also"></a>참고자료

[CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
