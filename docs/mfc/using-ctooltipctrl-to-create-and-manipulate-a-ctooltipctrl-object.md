---
title: CToolTipCtrl을 사용하여 CToolTipCtrl 개체 만들기 및 조작
ms.date: 11/04/2016
f1_keywords:
- CToolTipCtrl
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
ms.openlocfilehash: b0f008c70eeb43455408e5b0ad302df6b923608e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411645"
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>CToolTipCtrl을 사용하여 CToolTipCtrl 개체 만들기 및 조작

예로 [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) 사용:

### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>CToolTipCtrl을 만들고 조작하려면

1. `CToolTipCtrl` 개체를 생성합니다.

1. 호출 [Create](../mfc/reference/ctooltipctrl-class.md#create) Windows 도구 설명 공용 컨트롤을 만들고 연결 하는 `CToolTipCtrl` 개체입니다.

1. 호출 [AddTool](../mfc/reference/ctooltipctrl-class.md#addtool) 도구에 커서를 가져갈 때 도구 설명에 저장 된 정보가 표시 되도록 도구 설명 컨트롤을 사용 하 여 도구를 등록 합니다.

1. 호출 [SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo) 를 도구용 도구 설명을 유지 관리 하는 정보를 설정 합니다.

1. 호출 [SetToolRect](../mfc/reference/ctooltipctrl-class.md#settoolrect) 를 도구용 새 경계 사각형을 설정 합니다.

1. 호출 [HitTest](../mfc/reference/ctooltipctrl-class.md#hittest) 는 지점에 지정 된 도구의 경계 사각형 안에 있는지 그리고 있다면 확인을 테스트 하려면 도구에 대 한 정보를 검색 합니다.

1. 호출 [GetToolCount](../mfc/reference/ctooltipctrl-class.md#gettoolcount) 도구의 수를 검색 하 여 도구 설명 컨트롤을 사용 하 여 등록 합니다.

## <a name="see-also"></a>참고자료

[CToolTipCtrl 사용](../mfc/using-ctooltipctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
