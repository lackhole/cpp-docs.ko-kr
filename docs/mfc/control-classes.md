---
title: 컨트롤 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.control
helpviewer_keywords:
- static display controls [MFC]
- control classes [MFC]
- buttons, MFC control classes
- controls [MFC], MFC control classes
- controls [MFC]
- list boxes [MFC], MFC control classes
- control classes [MFC], MFC
- text, controls for input [MFC]
- user input [MFC], MFC control classes
ms.assetid: f9876606-9f5b-44cb-9135-213298d1df8f
ms.openlocfilehash: 79a71a4660cd49f85726d730c9fad0b2f10f83bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338170"
---
# <a name="control-classes"></a>컨트롤 클래스

컨트롤 클래스는 다양 한 정적 텍스트 컨트롤에서 트리 컨트롤에 이르기까지 표준 Windows 컨트롤을 캡슐화 합니다. 또한 MFC는 비트맵 및 컨트롤 막대를 사용 하 여 단추 등의 몇 가지 새로운 컨트롤을 제공 합니다.

컨트롤의 클래스 이름이 종료 "**Ctrl**" Windows 95 및 Windows NT 버전 3.51에서 새로 추가 된 합니다.

## <a name="static-display-controls"></a>정적 디스플레이 컨트롤

[CStatic](../mfc/reference/cstatic-class.md)<br/>
정적 디스플레이 창입니다. 정적 컨트롤 레이블, 상자 또는 대화 상자 또는 창에서 다른 컨트롤을 구분 하는 데 사용 됩니다. 그래픽 이미지 대신 텍스트 또는 상자를 표시할 수도 있습니다.

## <a name="text-controls"></a>텍스트 컨트롤

[CEdit](../mfc/reference/cedit-class.md)<br/>
편집 가능한 텍스트 컨트롤 창입니다. 편집 컨트롤은 사용자가 텍스트 입력에 사용 됩니다.

[CIPAddressCtrl](../mfc/reference/cipaddressctrl-class.md)<br/>
IP (인터넷 프로토콜) 주소를 조작 하는 편집 상자를 지원 합니다.

[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)<br/>
사용자 입력 수 및 텍스트 편집 컨트롤입니다. 에 캡슐화 된 컨트롤과 달리 `CEdit`, rich edit 컨트롤 문자 및 단락 서식 지정 및 OLE 개체를 지원 합니다.

## <a name="controls-that-represent-numbers"></a>숫자를 나타내는 컨트롤

[CSliderCtrl](../mfc/reference/csliderctrl-class.md)<br/>
슬라이더를 이동할 값 또는 값 집합을 선택 하는 포함 하는 컨트롤입니다.

[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)<br/>
화살표 단추 쌍 사용자 수 증가 또는 감소 값을 클릭 합니다.

[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)<br/>
점차 채워지는 왼쪽에서 오른쪽 작업의 진행률을 나타내는 사각형을 표시 합니다.

[CScrollBar](../mfc/reference/cscrollbar-class.md)<br/>
스크롤 막대 컨트롤 창입니다. 클래스 대화 상자 또는 창에서 사용자는 범위 내에서 위치를 지정할 수는 컨트롤로 사용에 대 한 스크롤 막대의 기능을 제공 합니다.

## <a name="buttons"></a>단추

[CButton](../mfc/reference/cbutton-class.md)<br/>
단추 컨트롤 창입니다. 클래스는 누름 단추, 확인란 또는 라디오 단추를 대화 상자 또는 창에 대 한 프로그래밍 인터페이스를 제공합니다.

[CBitmapButton](../mfc/reference/cbitmapbutton-class.md)<br/>
캡션 텍스트 대신 비트맵 단추입니다.

## <a name="lists"></a>목록

[CListBox](../mfc/reference/clistbox-class.md)<br/>
목록 상자 컨트롤 창입니다. 목록 상자에 사용자가 보고 있는 선택 항목의 목록을 표시 합니다.

[CDragListBox](../mfc/reference/cdraglistbox-class.md)<br/>
Windows 목록 상자의; 기능을 제공합니다. 목록 상자 내에서 파일 이름 및 문자열 리터럴과 같은 목록 상자 항목을 이동할 수 있습니다. 이 기능을 사용 하 여 목록 상자는 알파벳 이외의 주문에서 항목 목록에 대 한 유용한와 같은 프로젝트의 경로 이름이 나 파일을 포함 합니다.

[CComboBox](../mfc/reference/ccombobox-class.md)<br/>
콤보 상자 컨트롤 창입니다. 콤보 상자 편집 컨트롤 및 목록 상자 이루어져 있습니다.

[CComboBoxEx](../mfc/reference/ccomboboxex-class.md)<br/>
이미지 목록에 대한 지원을 제공하여 콤보 상자 컨트롤을 확장합니다.

[CCheckListBox](../mfc/reference/cchecklistbox-class.md)<br/>
사용자 수 선택 하거나 선택 취소, 각 항목 옆에 있는 확인란을 사용 하 여 항목의 목록을 표시 합니다.

[CListCtrl](../mfc/reference/clistctrl-class.md)<br/>
아이콘 및 레이블 파일 탐색기의 오른쪽 창에 비슷한 방식으로 구성 된 각 항목의 컬렉션을 표시 합니다.

[CTreeCtrl](../mfc/reference/ctreectrl-class.md)<br/>
파일 탐색기의 왼쪽된 창에 비슷한 방식으로 정렬 하는 레이블과 아이콘의 계층적 목록을 표시 합니다.

## <a name="toolbars-and-status-bars"></a>도구 모음 및 상태 표시줄

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)<br/>
Windows의 도구 모음 공용 컨트롤의 기능을 제공합니다. 대부분의 MFC 프로그램 사용 [CToolBar](../mfc/reference/ctoolbar-class.md) 이 클래스는 대신 합니다.

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)<br/>
일반적으로 응용 프로그램 상태 정보를 표시할 수 있는 창으로 구분 가로 창입니다. 대부분의 MFC 프로그램 사용 [CStatusBar](../mfc/reference/cstatusbar-class.md) 이 클래스는 대신 합니다.

## <a name="miscellaneous-controls"></a>기타 컨트롤

[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)<br/>
간단한 비디오 클립을 표시합니다.

[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)<br/>
응용 프로그램 도구의 용도 설명 하는 텍스트 한 줄을 표시 하는 작은 팝업 창입니다.

[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)<br/>
확장 된 편집 컨트롤 또는 사용자가 특정 날짜 또는 시간 값을 선택할 수 있도록 간단한 일정 인터페이스 컨트롤을 지원 합니다.

[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)<br/>
제목 또는 열에 대 한 레이블을 표시합니다.

[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)<br/>
사용자가 날짜를 선택 하도록 허용 하는 간단한 일정 인터페이스 컨트롤을 지원 합니다.

[CTabCtrl](../mfc/reference/ctabctrl-class.md)<br/>
사용자가 클릭할 수, 노트북의 구분선 유사한 탭 컨트롤입니다.

[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)<br/>
사용자를 신속 하 게 작업을 수행 하려면 사용자를 누를 수 있는 바로 가기 키 조합을 만들 수 있습니다.

[CLinkCtrl](../mfc/reference/clinkctrl-class.md)<br/>
마크업 텍스트를 렌더링 하 고 포함된 된 링크를 클릭할 때 적절 한 응용 프로그램을 시작 합니다.

[CHtmlEditCtrl](../mfc/reference/chtmleditctrl-class.md)<br/>
MFC 창에서 WebBrowser ActiveX 컨트롤의 기능을 제공합니다.

## <a name="related-classes"></a>관련된 클래스

[CImageList](../mfc/reference/cimagelist-class.md)<br/>
Windows 이미지 목록의 기능을 제공합니다. 이미지 목록은 목록 컨트롤 및 트리 컨트롤과 함께 사용됩니다. 이러한 컨트롤은 또한 동일한 크기의 비트맵 집합을 저장하고 아카이브하는 데 사용할 수 있습니다.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Windows 컨트롤과 연결 된 모든 보기에 대 한 기본 클래스입니다. 컨트롤에 따라 보기에 대 한 설명은 다음과 같습니다.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Windows 표준에 포함 된 뷰를 편집 컨트롤입니다.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
컨트롤을 편집 하는 풍부한는 Windows를 포함 하는 뷰입니다.

[CListView](../mfc/reference/clistview-class.md)<br/>
Windows 목록 컨트롤을 포함 하는 뷰.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Windows 트리 컨트롤을 포함 하는 뷰.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
