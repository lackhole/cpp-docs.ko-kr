---
title: MFC에서 사용할 수 있는 파생된 뷰 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
ms.openlocfilehash: 61b38f6147a8bde4f6eb42cd144f9f64dac8dbd8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152906"
---
# <a name="derived-view-classes-available-in-mfc"></a>MFC에서 사용할 수 있는 파생된 뷰 클래스

다음 표에서 MFC의 뷰 클래스와 서로 간의 관계를 보여 줍니다. 뷰 클래스의 기능 로부터 파생 된 MFC 뷰 클래스에 따라 달라 집니다.

### <a name="view-classes"></a>뷰 클래스

|클래스|설명|
|-----------|-----------------|
|[CView](../mfc/reference/cview-class.md)|모든 뷰의 기본 클래스입니다.|
|[CCtrlView](../mfc/reference/cctrlview-class.md)|기본 클래스 `CTreeView`, `CListView`를 `CEditView`, 및 `CRichEditView`합니다. 이러한 클래스를 통해 문서/뷰 아키텍처를 사용 하 여 표시 된 Windows 공용 컨트롤을 사용 하 여 수 있습니다.|
|[CEditView](../mfc/reference/ceditview-class.md)|Windows를 기반으로 간단한 뷰 편집 상자 컨트롤입니다. 입력 텍스트를 편집할 수 있습니다 및 간단한 텍스트 편집기 응용 프로그램에 대 한 기준으로 사용할 수 있습니다. `CRichEditView`을 참조하세요.|
|[CRichEditView](../mfc/reference/cricheditview-class.md)|포함 하는 뷰를 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) 개체입니다. 이 클래스는 유사 `CEditView`, 하지만 달리 `CEditView`, `CRichEditView` 서식 있는 텍스트를 처리 합니다.|
|[CListView](../mfc/reference/clistview-class.md)|포함 하는 뷰를 [CListCtrl](../mfc/reference/clistctrl-class.md) 개체입니다.|
|[CTreeView](../mfc/reference/ctreeview-class.md)|포함 하는 뷰를 [CTreeCtrl](../mfc/reference/ctreectrl-class.md) 시각적 개체의 솔루션 탐색기 창 유사한 뷰에 대 한 개체를 C++합니다.|
|[CScrollView](../mfc/reference/cscrollview-class.md)|기본 클래스 `CFormView`하십시오 `CRecordView`, 및 `CDaoRecordView`합니다. 보기의 콘텐츠 스크롤을 구현 합니다.|
|[CFormView](../mfc/reference/cformview-class.md)|폼 보기에 컨트롤을 포함 하는 뷰입니다. 폼 기반 응용 프로그램을 하나 이상의 폼 인터페이스를 제공합니다.|
|[CHtmlView](../mfc/reference/chtmlview-class.md)|웹 브라우저 보기는 네트워크 및 로컬 파일 시스템에서 응용 프로그램의 사용자 폴더 뿐 아니라 World Wide Web에서 사이트 탐색할 수 있습니다. 액티브 문서 컨테이너도 웹 브라우저 보기를 사용할 수도 있습니다.|
|[CRecordView](../mfc/reference/crecordview-class.md)|컨트롤에 ODBC 데이터베이스 레코드를 표시 하는 폼 보기입니다. 뷰의 기본 클래스는 프로젝트에서 ODBC 지원을 선택 하면 `CRecordView`합니다. 에 연결 된 뷰를 `CRowset` 개체입니다.|
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|컨트롤에서 DAO 데이터베이스 레코드를 표시 하는 폼 보기. 뷰의 기본 클래스는 프로젝트에서 DAO 지원을 선택 하면 `CDaoRecordView`합니다. 에 연결 된 뷰를 `CDaoRecordset` 개체입니다.|
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|컨트롤에 OLE DB 레코드를 표시 하는 폼 보기입니다. 뷰의 기본 클래스는 프로젝트에서 OLE DB 지원을 선택 하면 `COleDBRecordView`합니다. 에 연결 된 뷰를 `CRowset` 개체입니다.|

> [!NOTE]
>  MFC 버전 4.0부터 `CEditView` 에서 파생 된 `CCtrlView`합니다.

응용 프로그램에서 이러한 클래스를 사용 하려면 응용 프로그램의 뷰 클래스를 파생 합니다. 관련 정보를 참조 하세요 [스크롤 및 크기 조정 뷰](../mfc/scrolling-and-scaling-views.md)합니다. 데이터베이스 클래스에 대 한 자세한 내용은 참조 하세요. [개요: 데이터베이스 프로그래밍](../data/data-access-programming-mfc-atl.md)합니다.

## <a name="see-also"></a>참고자료

[뷰 사용](../mfc/using-views.md)
