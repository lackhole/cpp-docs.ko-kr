---
title: 컨트롤 막대 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.control
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
ms.openlocfilehash: 3426d84eab888a6fe78b663945776fff2fe708dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301957"
---
# <a name="control-bar-classes"></a>컨트롤 막대 클래스

컨트롤 막대 프레임 창에 연결 됩니다. 단추, status 창 또는 대화 상자 템플릿을 포함 합니다. 자유 부동 컨트롤 막대에도 도구 팔레트를 호출 하도록 연결 하 여 구현 되는 [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) 개체입니다.

## <a name="framework-control-bars"></a>프레임 워크 컨트롤 막대

이러한 컨트롤 막대는 MFC 프레임 워크의 필수적인 부분입니다. 이들은 사용 하기 쉽고 더 강력한 프레임 워크와 통합 되어 있으므로 Windows 컨트롤 막대 보다입니다. 대부분의 MFC 응용 프로그램 Windows 컨트롤 막대 보다는 이러한 컨트롤 막대를 사용합니다.

[CControlBar](../mfc/reference/ccontrolbar-class.md)<br/>
이 섹션에 나열 된 MFC 컨트롤 막대에 대 한 기본 클래스입니다. 컨트롤 막대는 창 프레임 창의 가장자리에 맞춥니다. 컨트롤 막대를 포함 하거나 `HWND`-기반 자식 컨트롤 또는 컨트롤을 기반으로 하지는 `HWND`, 도구 모음 단추와 같은 합니다.

[CDialogBar](../mfc/reference/cdialogbar-class.md)<br/>
대화 상자 템플릿을 기반으로 하는 컨트롤 막대입니다.

[CReBar](../mfc/reference/crebar-class.md)<br/>
컨트롤의 형태로 추가 자식 창을 포함할 수 있는 도구 모음을 지원 합니다.

[CToolBar](../mfc/reference/ctoolbar-class.md)<br/>
하지 비트맵 명령 단추를 포함 하는 도구 모음 컨트롤 창 기반는 `HWND`합니다. 이 클래스를 사용 하는 대부분의 MFC 응용 프로그램 대신 `CToolBarCtrl`합니다.

[CStatusBar](../mfc/reference/cstatusbar-class.md)<br/>
상태 표시줄 컨트롤 windows에 대 한 기본 클래스입니다. 이 클래스를 사용 하는 대부분의 MFC 응용 프로그램 대신 `CStatusBarCtrl`합니다.

## <a name="windows-control-bars"></a>Windows 컨트롤 막대

이러한 컨트롤 막대는 해당 Windows 컨트롤에 대 한 씬 래퍼입니다. 프레임 워크와 통합 되지 않은, 때문에 하기가 어렵습니다 보다 앞에 나열 된 컨트롤 막대를 사용 합니다. 대부분의 MFC 응용 프로그램 위에 나열 된 컨트롤 막대를 사용 합니다.

[CRebarCtrl](../mfc/reference/crebarctrl-class.md)<br/>
내부 제어를 구현 하는 `CRebar` 개체입니다.

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)<br/>
일반적으로 응용 프로그램 상태 정보를 표시할 수 있는 창으로 구분 가로 창입니다.

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)<br/>
Windows의 도구 모음 공용 컨트롤의 기능을 제공합니다.

## <a name="related-classes"></a>관련된 클래스

[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)<br/>
응용 프로그램 도구의 용도 설명 하는 텍스트 한 줄을 표시 하는 작은 팝업 창입니다.

[CDockState](../mfc/reference/cdockstate-class.md)<br/>
도킹 컨트롤 막대에 대 한 상태 데이터의 영구 저장소를 처리 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
