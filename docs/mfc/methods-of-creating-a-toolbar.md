---
title: 도구 모음을 만드는 방법
ms.date: 11/04/2016
helpviewer_keywords:
- CToolBarCtrl class [MFC], and CToolBar class [MFC]
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- toolbar controls [MFC]
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
ms.openlocfilehash: f269ad990042f51554ec598b0bddbe5a6d7776b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383927"
---
# <a name="methods-of-creating-a-toolbar"></a>도구 모음을 만드는 방법

MFC 도구 모음을 만들려면 두 클래스를 제공 합니다. [CToolBar](../mfc/reference/ctoolbar-class.md) 하 고 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) (하는 Windows 공용 컨트롤 API를 래핑하여). `CToolBar` 모든 도구 모음 공용 컨트롤의 기능을 제공 하면;에 대 한 다양 한 일반적인 필수 컨트롤 설정 및 구조를 처리 하 고 그러나 결과 실행 파일 일반적으로 보다 커지는 경우가 사용 하 여 만든 `CToolBarCtrl`합니다.

`CToolBarCtrl` 일반적으로 결과를 더 작은 실행 파일을 사용할 수도 `CToolBarCtrl` MFC 아키텍처에 도구 모음을 통합 하지 않을 경우. 사용 하려는 경우 `CToolBarCtrl` MFC 아키텍처에 도구 모음을 통합 하 고, mfc 도구 모음 컨트롤 조작에 전달할 추가 주의 해야 합니다. 이 통신; 어렵지 않습니다. 그러나 사용 하는 경우에 필요 없는 추가 작업 것 `CToolBar`입니다.

Visual C++ 도구 모음 공용 컨트롤을 활용 하려면 두 가지 방법을 제공 합니다.

- 사용 하 여 도구 모음을 만듭니다 `CToolBar`, 호출 [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl) 에 액세스 하는 `CToolBarCtrl` 멤버 함수입니다.

- 사용 하 여 도구 모음을 만듭니다 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)의 생성자입니다.

두 방법 중 하나는 도구 모음 컨트롤의 멤버 함수에 액세스할 수 있습니다. 호출 하는 경우 `CToolBar::GetToolBarCtrl`에 대 한 참조를 반환 하는 `CToolBarCtrl` 개체 멤버 함수의 집합 중 하나를 사용할 수 있습니다. 참조 [CToolBar](../mfc/reference/ctoolbar-class.md) 생성 하 고 사용 하 여 도구 모음 만들기에 대 한 내용은 `CToolBar`합니다.

## <a name="see-also"></a>참고자료

[CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
