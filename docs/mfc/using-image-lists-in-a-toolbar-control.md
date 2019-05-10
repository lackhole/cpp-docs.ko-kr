---
title: 도구 모음 컨트롤에서 이미지 목록 사용
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
ms.openlocfilehash: d027f7834c67ad0ed51d1b7fda5b2704972efe38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411567"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>도구 모음 컨트롤에서 이미지 목록 사용

기본적으로 사용 하는 도구 모음 컨트롤에서 단추 이미지는 단일 비트맵으로 저장 됩니다. 그러나 단추 이미지 일련의 이미지 목록에도 저장할 수 있습니다. 도구 모음 컨트롤 개체는 최대 3 개의 별도 이미지 목록을 사용할 수 있습니다.

- 현재 사용할 수 있는 도구 모음 단추에 대 한 이미지 목록 포함 이미지를 사용할 수 있습니다.

- 이미지 목록 현재 해제 되어 있는 도구 모음 단추에 대 한 이미지를 포함 하는 사용 하지 않도록 설정 합니다.

- 현재 강조 표시 되는 도구 모음 단추에 대 한 이미지 목록 포함 이미지를 강조 표시 합니다. 이 이미지 목록 도구 모음 TBSTYLE_FLAT 스타일을 사용 하는 경우에 사용 됩니다.

사용 하 여 연결 하는 경우 이러한 이미지 목록 도구 모음 컨트롤에서 사용 되는 `CToolBarCtrl` 개체입니다. 호출 하 여이 연결이 이루어집니다 [CToolBarCtrl::SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist)를 [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist), 및 [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist)합니다.

MFC는 기본적으로 다음을 사용 합니다.는 `CToolBar` MFC 응용 프로그램 도구 모음을 구현 하는 클래스입니다. 그러나 합니다 `GetToolBarCtrl` 멤버 함수는 포함 된 검색에 사용할 수 있습니다 `CToolBarCtrl` 개체입니다. 다음에 대 한 호출 가능 `CToolBarCtrl` 반환된 된 개체를 사용 하 여 멤버 함수입니다.

다음 예제에서는 할당을 사용 하도록 설정 하 여이 기술을 보여 줍니다 (`m_ToolBarImages`)과 사용 안 함 (`m_ToolBarDisabledImages`) 이미지 목록에는 `CToolBarCtrl` 개체 (`m_ToolBarCtrl`).

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
>  도구 모음 개체에 의해 사용 되는 이미지 목록에는 영구 개체 여야 합니다. 따라서이 일반적으로 MFC 클래스의 데이터 멤버 이 예제에서는 주 프레임 창 클래스입니다.

이미지 목록 연관 되 면를 `CToolBarCtrl` 개체, 프레임 워크는 적절 한 단추 이미지를 자동으로 표시 합니다.

## <a name="see-also"></a>참고자료

[CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
