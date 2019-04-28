---
title: 도구 모음 컨트롤의 모양 사용자 지정
ms.date: 11/04/2016
f1_keywords:
- TBSTYLE_
helpviewer_keywords:
- flat toolbars
- CToolBar class [MFC], styles
- transparent toolbars
- TBSTYLE_ styles [MFC]
- CToolBarCtrl class [MFC], object styles
- toolbar controls [MFC], style
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
ms.openlocfilehash: 8a0db3299ebb54d226edc1434dedbc6a04eb9b00
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241815"
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>도구 모음 컨트롤의 모양 사용자 지정

클래스 `CToolBarCtrl` 모양을 (및 경우에 따라 동작)의 도구 모음 개체에 영향을 주는 다양 한 스타일을 제공 합니다. 설정 하 여 도구 모음 개체를 수정 합니다 `dwCtrlStyle` 의 매개 변수를 `CToolBarCtrl::Create` (또는 `CToolBar::CreateEx`) 도구 모음 컨트롤을 처음 만들 때 멤버 함수입니다.

다음과 같은 스타일 "3D" 측면의 도구 모음 단추 및 단추 텍스트의 배치에 영향을 줍니다.

- **TBSTYLE_FLAT** 도구 모음 및 단추 모두 투명 하 게 되는 플랫 도구 모음을 만듭니다. 단추 텍스트 비트맵 단추 아래에 나타납니다. 이 스타일을 사용 하면 커서 아래에 있는 단추를 자동으로 강조 표시 됩니다.

- **TBSTYLE_TRANSPARENT** 투명 한 도구 모음을 만듭니다. 투명 한 도구 모음에서 도구 모음을 투명 하 게 되지만 단추가 없습니다. 단추 텍스트 비트맵 단추 아래에 나타납니다.

- **TBSTYLE_LIST** 위치 단추 오른쪽 단추 비트맵에는 텍스트입니다.

> [!NOTE]
>  Repaint 문제를 방지 하는 **TBSTYLE_FLAT** 하 고 **TBSTYLE_TRANSPARENT** 스타일 도구 모음 개체를 표시 하기 전에 설정 해야 합니다.

다음과 같은 스타일 도구 모음 사용자가 끌어서를 사용 하 여 도구 모음 개체 내에서 개별 단추 위치를 변경 하 고 삭제 하도록 허용 하는 경우를 결정 합니다.

- **TBSTYLE_ALTDRAG** ALT를 누른 채 끌어서 도구 모음 단추의 위치를 변경할 수 있습니다. 이 스타일을 지정 하지 않으면 사용자 키를 누른 채 단추 끌기를 가져야 합니다.

    > [!NOTE]
    >  합니다 **CCS_ADJUSTABLE** 스타일 도구 모음 단추를 놓을 수 있도록 지정 해야 합니다.

- **TBSTYLE_REGISTERDROP** 생성 **TBN_GETOBJECT** 알림 메시지를 요청 하려면 도구 모음 단추 위로 마우스 포인터를 이동할 때 대상 개체를 삭제 합니다.

나머지 스타일 도구 모음 개체의 시각적 및 비시각적 측면을 영향을 줍니다.

- **TBSTYLE_WRAPABLE** 단추의 여러 줄 수 있는 도구 모음을 만듭니다. 도구 모음 단추 수 "wrap" 다음 줄을 도구 모음 같은 줄에서 모든 단추를 포함 하도록 너무 좁게 면 합니다. 줄 바꿈 구분 및 바꿈은 경계에서 발생합니다.

- **TBSTYLE_CUSTOMERASE** 생성 **NM_CUSTOMDRAW** 알림 메시지를 처리할 때 **WM_ERASEBKGND** 메시지입니다.

- **TBSTYLE_TOOLTIPS** 응용 프로그램 도구 모음에서 단추에 대 한 설명이 포함 된 텍스트를 표시 하는 데 사용할 수 있는 도구 설명 컨트롤을 만듭니다.

Toolbar 스타일 및 확장된 스타일의 전체 목록은 참조 하세요. [도구 모음 컨트롤 및 단추 스타일](/windows/desktop/Controls/toolbar-control-and-button-styles) 하 고 [도구 모음 확장 스타일](/windows/desktop/Controls/toolbar-extended-styles) Windows SDK의 합니다.

## <a name="see-also"></a>참고자료

[CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
