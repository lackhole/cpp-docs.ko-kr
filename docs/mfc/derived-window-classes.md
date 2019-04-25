---
title: 파생된 창 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- window class hierarchy
- hierarchies, window classes
- classes [MFC], derived
- CWnd class [MFC], classes derived from
- derived classes [MFC], window classes
- window classes [MFC], derived
ms.assetid: 6f7e437e-fbde-4a06-bfab-72d9dbf05292
ms.openlocfilehash: e86ca139b8470dce614564f0c0134a611adeda2c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153380"
---
# <a name="derived-window-classes"></a>파생된 창 클래스

Windows에서 직접 만들 수 있습니다 [CWnd](../mfc/reference/cwnd-class.md)에서 새 창 클래스를 파생 하거나 `CWnd`합니다. 일반적으로 사용자 지정 창을 만드는 방법입니다. 그러나 프레임 워크 프로그램에 사용 되는 대부분의 windows는 대신 중 하나에서 생성 된 `CWnd`-MFC에서 제공 하는 프레임 창 클래스를 파생 합니다.

## <a name="frame-window-classes"></a>프레임 창 클래스

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
SDI 프레임 창 단일 문서 및 뷰를 사용 합니다. 프레임 창에는 응용 프로그램에 대 한 주 프레임 창 이자 현재 문서 프레임 창입니다.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
MDI 응용 프로그램에 대 한 주 프레임 창으로 사용 합니다. 주 프레임 창은 MDI 문서 창 모두에 대 한 컨테이너와 해당 메뉴 모음을 공유 합니다. MDI 프레임 창에는 바탕 화면에 표시 되는 최상위 창이입니다.

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
MDI 주 프레임 창에서 열린 개별 문서에 사용 합니다. 각 문서와 뷰 MDI 주 프레임 창에 포함 된 MDI 자식 프레임 창으로 묶여 있습니다. MDI 자식 창에 일반 프레임 창과 유사 하지만 바탕 화면에 앉아 대신 MDI 프레임 창 내에 포함 되어 있습니다. 그러나 MDI 자식 창에는 자체의 메뉴 모음 없으며 포함 된 MDI 프레임 창의 메뉴 모음을 공유 해야 합니다.

자세한 내용은 [프레임 Windows](../mfc/frame-windows.md)합니다.

## <a name="other-window-classes-derived-from-cwnd"></a>CWnd에서 파생 된 다른 창 클래스

프레임 창 외에도 windows의 다른 몇 가지 주요 범주에서 파생 된 `CWnd`:

*Views*<br/>
뷰를 사용 하 여 만들어집니다 합니다 `CWnd`-파생 클래스 [CView](../mfc/reference/cview-class.md) (또는 해당 파생된 클래스 중 하나). 보기에는 문서와 사용자 간의 중개자 역할와 문서에 연결 됩니다. 뷰는 일반적으로 SDI 프레임 창 또는 MDI 자식 프레임 창 (또는 도구 모음 및/또는 상태 표시줄에서 포함 하지 않는 클라이언트 영역의 해당 부분)의 클라이언트 영역을 채우는 자식 창 (MDI 자식 하지 함).

*대화 상자*<br/>
대화 상자를 사용 하 여 만들어집니다 합니다 `CWnd`-파생 클래스 [CDialog](../mfc/reference/cdialog-class.md)합니다.

*폼*<br/>
대화 상자와 같은 대화 상자 템플릿 리소스를 기반으로 하는 폼 뷰 클래스를 사용 하 여 만들어집니다 [CFormView](../mfc/reference/cformview-class.md)를 [CRecordView](../mfc/reference/crecordview-class.md), 또는 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)합니다.

*컨트롤*<br/>
단추, 목록 상자 및 콤보 상자와 같은 컨트롤에서 파생 된 다른 클래스를 사용 하 여 만들어진 `CWnd`합니다. 참조 [항목을 제어](../mfc/controls-mfc.md)입니다.

*컨트롤 막대*<br/>
컨트롤을 포함 하는 자식 창 도구 모음 및 상태 표시줄을 예로 들 수 있습니다. 참조 [컨트롤 막대](../mfc/control-bars.md)합니다.

## <a name="window-class-hierarchy"></a>창 클래스 계층 구조

참조를 [MFC 계층 구조 차트](../mfc/hierarchy-chart.md) 에 *MFC 참조*합니다. 보기 설명 [문서/뷰 아키텍처](../mfc/document-view-architecture.md)합니다. 대화 상자에서 설명 [대화 상자](../mfc/dialog-boxes.md)합니다.

## <a name="creating-your-own-special-purpose-window-classes"></a>특수 한 용도의 창 클래스 만들기

클래스 라이브러리에서 제공 되는 창 클래스를 외에도 특수 한 용도의 자식 창이 필요할 수 있습니다. 이러한 창을 만들려면 직접 만들어보십시오 [CWnd](../mfc/reference/cwnd-class.md)-클래스를 파생 하 고 자식 창 프레임 또는 보기를 확인 합니다. 프레임 워크 문서 프레임 창 클라이언트 영역의 범위를 관리 하는 것을 염두에 두십시오. 대부분의 클라이언트 영역을 볼 수 있지만 다른 창에서 관리 하는, 예: 컨트롤 막대 또는 사용자 고유의 사용자 지정 windows와 공유할 수 있습니다 공간 보기입니다. 클래스의 메커니즘을 사용 하 여 상호 작용 해야 할 수 있습니다 [CView](../mfc/reference/cview-class.md) 하 고 [CControlBar](../mfc/reference/ccontrolbar-class.md) 프레임 창의 클라이언트 영역에서 자식 창의 위치를 지정 합니다.

[Windows 만들기](../mfc/creating-windows.md) 만들기 창 개체 및 관리 하는 windows에 설명 합니다.

## <a name="see-also"></a>참고자료

[창 개체](../mfc/window-objects.md)
