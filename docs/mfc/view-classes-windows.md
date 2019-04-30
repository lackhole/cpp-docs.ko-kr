---
title: 뷰 클래스(Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.view
helpviewer_keywords:
- form and record views [MFC]
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
ms.openlocfilehash: ad58fd6fa2548c2cf320baf75b8fc33a835ddd55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296620"
---
# <a name="view-classes-windows"></a>뷰 클래스(Windows)

`CView` 및 해당 파생된 클래스는 프레임 창의 클라이언트 영역을 나타내는 자식 창. 뷰는 데이터를 표시 하 고 문서에 대 한 입력을 수락 합니다.

뷰 클래스를 문서 클래스 및 문서 템플릿 개체를 사용 하는 프레임 창 클래스와 연결 됩니다.

[CView](../mfc/reference/cview-class.md)<br/>
문서 데이터의 응용 프로그램 관련 보기에 대 한 기본 클래스입니다. 뷰는 데이터를 표시 및 편집 하거나 데이터를 선택 하려면 사용자 입력을 허용 합니다. 뷰 클래스 또는 클래스에서 파생 `CView`합니다.

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
스크롤 기능이 보기에 대 한 기본 클래스입니다. 뷰 클래스를 파생 `CScrollView` 자동 스크롤에 대 한 합니다.

## <a name="form-and-record-views"></a>폼 및 레코드 뷰

폼 뷰 뷰 스크롤도 됩니다. 이러한 대화 상자 템플릿에 기반으로 합니다.

레코드 뷰 폼 보기에서 파생 됩니다. 또한 대화 상자 템플릿 외에도 데이터베이스에 대 한 연결이 있습니다.

[CFormView](../mfc/reference/cformview-class.md)<br/>
레이아웃을 대화 상자 템플릿에 정의 된 스크롤 보기입니다. 클래스를 파생 `CFormView` 대화 상자 템플릿을 기반으로 사용자 인터페이스를 구현 합니다.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
양식을 제공 데이터 액세스 개체 (DAO) 레코드 집합 개체에 직접 연결 하는 보기입니다. 모든 폼 보기와 같은 `CDaoRecordView` 대화 상자 템플릿을 기반으로 합니다.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
양식을 제공 개방형 데이터베이스 연결 (ODBC) 레코드 집합 개체에 직접 연결 하는 보기입니다. 모든 폼 보기와 같은 `CRecordView` 대화 상자 템플릿을 기반으로 합니다.

[CHtmlEditView](../mfc/reference/chtmleditview-class.md)<br/>
HTML WebBrowser 편집 플랫폼의 기능을 제공 하는 폼 보기입니다.

## <a name="control-views"></a>컨트롤 뷰

컨트롤 보기에는 해당 보기와 컨트롤을 표시합니다.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Windows 컨트롤과 연결 된 모든 보기에 대 한 기본 클래스입니다. 컨트롤에 따라 보기에 대 한 설명은 다음과 같습니다.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Windows 표준에 포함 된 뷰를 편집 컨트롤 (참조 [CEdit](../mfc/reference/cedit-class.md)). 컨트롤 지원 텍스트 편집, 검색, 교체 및 스크롤 기능을 편집 합니다.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
컨트롤을 편집 하는 풍부한는 Windows를 포함 하는 뷰입니다 (참조 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). 편집 컨트롤의 기능을 하는 것 외에도 다양 한 컨트롤 지원 글꼴, 색, 단락 형식 및 포함 된 OLE 개체를 편집 합니다.

[CListView](../mfc/reference/clistview-class.md)<br/>
Windows 목록 컨트롤을 포함 하는 뷰입니다 (참조 [CListCtrl](../mfc/reference/clistctrl-class.md)). 목록 컨트롤 아이콘 및 레이블 파일 탐색기의 오른쪽 창에 비슷한 방식으로 구성 된 각 항목의 컬렉션을 표시 합니다.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Windows 트리 컨트롤을 포함 하는 뷰입니다 (참조 [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). 트리 컨트롤에는 파일 탐색기의 왼쪽된 창에 비슷한 방식으로 정렬 하는 레이블과 아이콘의 계층적 목록을 표시 합니다.

## <a name="related-classes"></a>관련된 클래스

`CSplitterWnd` 단일 한 프레임 창 내에서 여러 뷰를 포함할 수 있습니다. `CPrintDialog` 및 `CPrintInfo` 뷰의 인쇄 및 인쇄 미리 보기 기능을 지원 합니다. `CRichEditDoc` 및 `CRichEditCntrItem` 사용 `CRichEditView` OLE 컨테이너 기능을 구현 합니다.

[CSplitterWnd](../mfc/reference/csplitterwnd-class.md)<br/>
사용자를 여러 개의 창으로 분할할 수 있는 창입니다. 이러한 창은 고정 된 크기를 사용자가 크기 조정할 수 있습니다.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
파일 인쇄를 위한 표준 대화 상자를 제공 합니다.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)<br/>
인쇄 또는 인쇄 미리 보기 작업에 대 한 정보를 포함 하는 구조체입니다. 사용한 `CView`아키텍처 인쇄 합니다.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
에 있는 OLE 클라이언트 항목의 목록을 유지 관리는 `CRichEditView`합니다.

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
OLE에 저장 된 항목에 대 한 클라이언트 쪽 액세스할는 `CRichEditView`합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
