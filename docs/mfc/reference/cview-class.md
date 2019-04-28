---
title: CView 클래스
ms.date: 11/04/2016
f1_keywords:
- CView
- AFXWIN/CView
- AFXWIN/CView::CView
- AFXWIN/CView::DoPreparePrinting
- AFXWIN/CView::GetDocument
- AFXWIN/CView::IsSelected
- AFXWIN/CView::OnDragEnter
- AFXWIN/CView::OnDragLeave
- AFXWIN/CView::OnDragOver
- AFXWIN/CView::OnDragScroll
- AFXWIN/CView::OnDrop
- AFXWIN/CView::OnDropEx
- AFXWIN/CView::OnInitialUpdate
- AFXWIN/CView::OnPrepareDC
- AFXWIN/CView::OnScroll
- AFXWIN/CView::OnScrollBy
- AFXWIN/CView::OnActivateFrame
- AFXWIN/CView::OnActivateView
- AFXWIN/CView::OnBeginPrinting
- AFXWIN/CView::OnDraw
- AFXWIN/CView::OnEndPrinting
- AFXWIN/CView::OnEndPrintPreview
- AFXWIN/CView::OnPreparePrinting
- AFXWIN/CView::OnPrint
- AFXWIN/CView::OnUpdate
helpviewer_keywords:
- CView [MFC], CView
- CView [MFC], DoPreparePrinting
- CView [MFC], GetDocument
- CView [MFC], IsSelected
- CView [MFC], OnDragEnter
- CView [MFC], OnDragLeave
- CView [MFC], OnDragOver
- CView [MFC], OnDragScroll
- CView [MFC], OnDrop
- CView [MFC], OnDropEx
- CView [MFC], OnInitialUpdate
- CView [MFC], OnPrepareDC
- CView [MFC], OnScroll
- CView [MFC], OnScrollBy
- CView [MFC], OnActivateFrame
- CView [MFC], OnActivateView
- CView [MFC], OnBeginPrinting
- CView [MFC], OnDraw
- CView [MFC], OnEndPrinting
- CView [MFC], OnEndPrintPreview
- CView [MFC], OnPreparePrinting
- CView [MFC], OnPrint
- CView [MFC], OnUpdate
ms.assetid: 9cff3c56-7564-416b-b9a4-71a9254ed755
ms.openlocfilehash: 06c6d4dff28399f3d8e6ac7f46d9ed751850036f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323341"
---
# <a name="cview-class"></a>CView 클래스

사용자 정의 뷰 클래스에 대한 기본 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE CView : public CWnd
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|이름|설명|
|----------|-----------------|
|[CView::CView](#cview)|`CView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CView::DoPreparePrinting](#doprepareprinting)|인쇄 대화 상자를 표시 하 고 프린터 장치 컨텍스트를 만듭니다. 재정의 하는 경우 호출 된 `OnPreparePrinting` 멤버 함수입니다.|
|[CView::GetDocument](#getdocument)|뷰와 연결 된 문서를 반환 합니다.|
|[CView::IsSelected](#isselected)|문서 항목이 선택 되어 있는지 테스트 합니다. OLE 지원에 필요합니다.|
|[CView::OnDragEnter](#ondragenter)|항목을 먼저 보기의 끌어서 놓기 영역으로 끌 때 호출 됩니다.|
|[CView::OnDragLeave](#ondragleave)|끌어 온된 항목을 끌어 놓기 영역의 보기를 벗어날 때 호출 됩니다.|
|[CView::OnDragOver](#ondragover)|뷰를 끌어 놓기 영역 위로 항목을 끌 때 호출 됩니다.|
|[CView::OnDragScroll](#ondragscroll)|커서를 창의 스크롤 영역으로 끄는 여부를 확인 하기 위해 호출 됩니다.|
|[CView::OnDrop](#ondrop)|뷰를 기본 처리기의 끌어서 놓기 영역으로 항목 삭제 된 경우 호출 됩니다.|
|[CView::OnDropEx](#ondropex)|뷰를 기본 처리기의 끌어서 놓기 영역으로 항목 삭제 된 경우 호출 됩니다.|
|[CView::OnInitialUpdate](#oninitialupdate)|문서에 뷰를 처음 연결 된 후 호출 됩니다.|
|[CView::OnPrepareDC](#onpreparedc)|전에 호출 합니다 `OnDraw` 화면 표시에 대 한 멤버 함수를 호출 또는 `OnPrint` 인쇄 또는 인쇄 미리 보기에 대 한 멤버 함수를 호출 합니다.|
|[CView::OnScroll](#onscroll)|OLE 항목 보기의 경계를 벗어난 끌면 호출 됩니다.|
|[CView::OnScrollBy](#onscrollby)|활성 전체 OLE 항목을 포함 하는 뷰가 스크롤될 때 호출 됩니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CView::OnActivateFrame](#onactivateframe)|뷰를 포함 하는 프레임 창이 활성화 또는 비활성화 하는 경우 호출 됩니다.|
|[CView::OnActivateView](#onactivateview)|보기 활성화 될 때 호출 됩니다.|
|[CView::OnBeginPrinting](#onbeginprinting)|인쇄 작업을 시작; 호출 그래픽 장치 GDI (인터페이스) 리소스를 할당할 재정의 합니다.|
|[CView::OnDraw](#ondraw)|문서의 화면 표시, 인쇄 또는 인쇄 미리 보기에 대 한 이미지를 렌더링 하기 위해 호출 됩니다. 필요한 구현입니다.|
|[CView::OnEndPrinting](#onendprinting)|인쇄 작업이 끝나면; 호출 GDI 리소스 할당을 취소 하려면 재정의 합니다.|
|[CView::OnEndPrintPreview](#onendprintpreview)|미리 보기 모드 종료 될 때 호출 됩니다.|
|[CView::OnPreparePrinting](#onprepareprinting)|문서가 인쇄 되거나; 미리 보기 전에 호출 인쇄 대화 상자를 초기화 하려면 재정의 합니다.|
|[CView::OnPrint](#onprint)|인쇄 문서 페이지 미리 보기를 호출 합니다.|
|[CView::OnUpdate](#onupdate)|문서가 해당 하는 보기에 알리기 위해 호출 수정 합니다.|

## <a name="remarks"></a>설명

뷰를 문서에 연결 되어 있고 문서와 사용자 간의 중개자 역할: 뷰 화면 또는 프린터 문서의 이미지를 렌더링 한 문서에는 작업으로 사용자 입력 해석 합니다.

뷰는 자식 프레임 창입니다. 둘 이상의 보기 프레임 창 분할기 창의 경우 처럼를 공유할 수 있습니다. 뷰 클래스, 프레임 창 클래스 및 문서 클래스 간의 관계에서 설정 되는 `CDocTemplate` 개체입니다. 사용자의 새 창이 열립니다 또는 기존 분할 하는 경우 새 뷰를 생성 한 프레임 워크 및 문서에 연결 합니다.

뷰를 하나의 문서에 연결할 수 있지만 문서를 한 번에 연결 된 뷰를 여러 개 있을 수 있습니다-예를 들어 문서의 분할 창에서 또는 여러 문서 MDI (인터페이스) 응용 프로그램에서 여러 자식 창에 표시 됩니다. 응용 프로그램는 지정 된 문서 형식에 대 한 다양 한 뷰를 지원할 수 있습니다. 예를 들어 워드 프로세서 프로그램 섹션 제목만 표시 하는 개요 보기 및 문서의 전체 텍스트 뷰를 모두 제공할 수 있습니다. 이러한 여러 유형의 보기 분할자 창을 사용 하는 경우 별도 프레임 창 또는 단일 프레임 창에 별도 창에 배치할 수 있습니다.

뷰는 여러 가지 메뉴, 도구 모음 또는 스크롤 막대에서 끌어서 놓기, 뿐만 아니라 명령을 통해 입력 키보드 입력, 마우스 입력 등의 입력 처리를 담당 수 있습니다. 보기는 프레임 창의 전달한 명령을 받습니다. 뷰의 지정된 된 명령을 처리 하지 않습니다는 관련된 문서에 명령을 전달 합니다. 모든 명령 대상에 같은 뷰는 메시지 맵을 통해 메시지를 처리합니다.

뷰는 저장 하지 않습니다를 표시 하 고 문서의 데이터를 수정 합니다. 문서는 데이터에 대 한 필요한 정보를 사용 하 여 뷰를 제공합니다. 문서 데이터 멤버를 직접 제공 멤버 함수를 호출 하는 뷰 클래스에 대 한 문서 클래스에 보기 액세스를 할 수 있습니다.

문서의 데이터가 변경 되 면 변경 내용을 담당 보기 일반적으로 호출 하는 [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) 함수를 호출 하 여 다른 보기에 알립니다, 문서에는 `OnUpdate` 멤버 함수에 대 한 각 합니다. 기본 구현을 `OnUpdate` 뷰의 전체 클라이언트 영역을 무효화 합니다. 문서의 수정된 부분에 매핑되는 클라이언트 영역 지역에만 무효화 하도록 재정의할 수 있습니다.

사용 하도록 `CView`클래스에서 파생 되 고 구현 합니다 `OnDraw` 화면 표시를 수행 하는 멤버 함수입니다. 사용할 수도 있습니다 `OnDraw` 인쇄 및 인쇄 미리 보기를 수행 하 합니다. 프레임 워크에는 인쇄 및 문서 미리 보기에 대 한 인쇄 루프를 처리 합니다.

스크롤 막대 메시지를 처리 하는 뷰를 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) 하 고 [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) 멤버 함수입니다. 스크롤 막대에서에서 메시지 처리 이러한 함수를 구현 하거나 사용할 수는 `CView` 파생 클래스 [CScrollView](../../mfc/reference/cscrollview-class.md) 처리를 스크롤 하 합니다.

외에 `CScrollView`에서 파생 된 다른 9 개 클래스를 제공 하는 Microsoft Foundation Class 라이브러리를 `CView`:

- [CCtrlView](../../mfc/reference/cctrlview-class.md), 문서-뷰 아키텍처를 트리, 목록, 서식 있는 편집 컨트롤의 사용을 허용 하는 뷰입니다.

- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md), 대화 상자 컨트롤의 데이터베이스 레코드를 표시 하는 뷰입니다.

- [CEditView](../../mfc/reference/ceditview-class.md), 여러 줄로 된 간단한 텍스트 편집기를 제공 하는 뷰입니다. 사용할 수는 `CEditView` 문서에 대 한 뷰를 비롯 하 여 대화 상자에 컨트롤로 개체입니다.

- [CFormView](../../mfc/reference/cformview-class.md), 대화 상자 컨트롤을 포함 하 고 대화 상자 템플릿 리소스를 기반으로 하는 스크롤 가능한 뷰입니다.

- [CListView](../../mfc/reference/clistview-class.md), 문서-뷰 아키텍처 목록 컨트롤을 사용 하 여 사용을 허용 하는 뷰입니다.

- [CRecordView](../../mfc/reference/crecordview-class.md), 대화 상자 컨트롤의 데이터베이스 레코드를 표시 하는 뷰입니다.

- [CRichEditView](../../mfc/reference/cricheditview-class.md), 문서-뷰 아키텍처 풍부한 편집 컨트롤의 사용을 허용 하는 뷰입니다.

- [CScrollView](../../mfc/reference/cscrollview-class.md)를 자동으로 스크롤 지원을 제공 하는 뷰입니다.

- [CTreeView](../../mfc/reference/ctreeview-class.md), 문서-뷰 아키텍처 트리 컨트롤을 사용 하 여 사용을 허용 하는 뷰입니다.

합니다 `CView` 클래스에 파생 된 구현 클래스가 `CPreviewView`는 인쇄 미리 보기를 수행 하는 데 프레임 워크에서 사용 됩니다. 이 클래스는 단일 또는 이중 페이지 미리 보기 도구 모음 등 인쇄 미리 보기 창에 고유한 기능에 대 한 지원 및 확대/축소를 미리 보기 이미지 확대를입니다. 호출 하거나 재정의할 필요가 `CPreviewView`의 멤버 함수 (예를 들어, 하려는 경우 인쇄 미리 보기 모드에서 편집을 지원) 인쇄 미리 보기에 대 한 고유한 인터페이스를 구현 하는 경우가 있습니다. 사용 하 여 대 한 자세한 내용은 `CView`를 참조 하세요 [문서/뷰 아키텍처](../../mfc/document-view-architecture.md) 하 고 [인쇄](../../mfc/printing.md)합니다. 또한 [기술 참고 30](../../mfc/tn030-customizing-printing-and-print-preview.md) 인쇄 미리 보기를 사용자 지정에 대 한 자세한 내용은 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CView`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cview"></a>  CView::CView

`CView` 개체를 생성합니다.

```
CView();
```

### <a name="remarks"></a>설명

새 프레임 창 개체를 만들거나 창을 분할 하는 경우 생성자를 호출 하는 프레임 워크. 재정의 된 [OnInitialUpdate](#oninitialupdate) 멤버 함수는 문서에 연결 된 후에 뷰를 초기화할 수 있습니다.

##  <a name="doprepareprinting"></a>  CView::DoPreparePrinting

재정의에서이 함수를 호출 [OnPreparePrinting](#onprepareprinting) 인쇄 대화 상자를 호출 하 여 프린터 장치 컨텍스트를 만듭니다.

```
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>매개 변수

*pInfo*<br/>
현재 인쇄 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체를 가리킵니다.

### <a name="return-value"></a>반환 값

0이 아닌 인쇄 또는 인쇄 미리 보기를 시작할 수 있습니다. 작업이 취소 된 경우 0입니다.

### <a name="remarks"></a>설명

이 함수의 동작은 인쇄 또는 인쇄 미리 보기에 대 한 호출 여부에 따라 다릅니다 (지정 된 합니다 `m_bPreview` 의 멤버는 *pInfo* 매개 변수). 파일로 인쇄 하는 경우이 함수에서 값을 사용 하 여 인쇄 대화 상자를 호출 하는 합니다 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체입니다 *pInfo* 가리키는; 함수를 만들고 사용자가 대화 상자를 닫은 후에 프린터 장치 컨텍스트 대화 상자에서 지정 된 사용자 설정에 따라 및 통해이 장치 컨텍스트를 반환 합니다 *pInfo* 매개 변수입니다. 이 장치 컨텍스트를 사용 하 여 문서를 인쇄 합니다.

이 함수는 현재 프린터 설정을 사용 하 여 프린터 장치 컨텍스트를 만듭니다 파일을 미리 볼 경우 이 장치 컨텍스트는 미리 보기 중 프린터를 시뮬레이션 하는 데 사용 됩니다.

##  <a name="getdocument"></a>  CView::GetDocument

보기의 문서에 대 한 포인터를 가져오려면이 함수를 호출 합니다.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CDocument](../../mfc/reference/cdocument-class.md) 뷰와 연결 된 개체입니다. 뷰는 문서에 연결 되어 있지 않으면 NULL입니다.

### <a name="remarks"></a>설명

이 문서의 멤버 함수를 호출할 수 있습니다.

##  <a name="isselected"></a>  CView::IsSelected

지정된 된 문서 항목 선택 되었는지 여부를 확인 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>매개 변수

*pDocItem*<br/>
테스트 중인 문서 항목을 가리킵니다.

### <a name="return-value"></a>반환 값

지정된 된 문서 항목을 선택 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 FALSE를 반환합니다. 선택 사용 하 여 구현 하는 경우이 함수를 재정의할 [CDocItem](../../mfc/reference/cdocitem-class.md) 개체입니다. 보기 OLE 항목을 포함 하는 경우이 함수를 재정의 해야 합니다.

##  <a name="onactivateframe"></a>  CView::OnActivateFrame

뷰를 포함 하는 프레임 창이 활성화 또는 비활성화 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual void OnActivateFrame(
    UINT nState,
    CFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>매개 변수

*nState*<br/>
프레임 창 되 고 있는지 여부를 지정 합니다. 활성화 또는 비활성화 합니다. 다음 값 중 하나일 수 있습니다.

- 프레임 창 WA_INACTIVE는 비활성화 합니다.

- WA_ACTIVE 마우스 이외의 다른 몇 가지 메서드를 통해 프레임 창이 활성화 되 고 (예: 창을 선택 하는 키보드 인터페이스 사용)를 클릭 합니다.

- 마우스 클릭 하 여 프레임 창의 WA_CLICKACTIVE는 활성화 하는 중

*pFrameWnd*<br/>
활성화 하는 프레임 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

뷰와 연결 된 프레임 창이 활성화 또는 비활성화 하는 경우에 특수 한 처리를 수행 하려는 경우이 멤버 함수를 재정의 합니다. 예를 들어 [CFormView](../../mfc/reference/cformview-class.md) 저장 하 고 포커스가 있는 컨트롤을 복원 하는 경우이 재정의 수행 합니다.

##  <a name="onactivateview"></a>  CView::OnActivateView

보기 활성화 또는 비활성화 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual void OnActivateView(
    BOOL bActivate,
    CView* pActivateView,
    CView* pDeactiveView);
```

### <a name="parameters"></a>매개 변수

*bActivate*<br/>
보기를 새로 여부를 나타내는 활성화 또는 비활성화 합니다.

*pActivateView*<br/>
활성화 중인 뷰 개체를 가리킵니다.

*pDeactiveView*<br/>
다음은 비활성화 된 뷰 개체를 가리킵니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 활성화 되 고 보기에 포커스를 설정 합니다. 보기 활성화 또는 비활성화 하는 경우에 특수 한 처리를 수행 하려는 경우이 함수를 재정의 합니다. 예를 들어, 비활성 뷰에서 현재 보기를 구분 하는 특수 한 시각적 큐를 제공 하려는 경우 사용자는 검사를 *bActivate* 매개 변수 및 보기의 모양을 적절 하 게 업데이트 합니다.

합니다 *pActivateView* 하 고 *pDeactiveView* 활성 뷰가 변경 없이 응용 프로그램의 주 프레임 창이 활성화 된 경우 매개 변수 같은 보기 가리킵니다-예를 들어, 포커스 되 면 MDI 자식 창 간에 전환 하는 경우 대신 하나의 뷰에서 다른 응용 프로그램 내에서 또는를 다른 응용 프로그램에서 전송 합니다. 필요한 경우 뷰를 다시 해당 색상표를 실현할 수 있습니다.

이러한 매개 변수가 서로 다르면 때 [CFrameWnd::SetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview) 에서 다른 뷰를 사용 하 여 호출 됩니다 [CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview) 를 반환 합니다. 분할을 사용 하 여 가장 자주 발생합니다.

##  <a name="onbeginprinting"></a>  CView::OnBeginPrinting

`OnPreparePrinting` 이 호출된 후 인쇄 또는 인쇄 미리 보기 작업을 시작할 때 프레임워크에서 호출됩니다.

```
virtual void OnBeginPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 디바이스 컨텍스트를 가리킵니다.

*pInfo*<br/>
현재 인쇄 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체를 가리킵니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 인쇄용으로 특별히 필요한 GDI 리소스(예: 펜 또는 글꼴)를 할당하려면 이 함수를 재정의합니다. GDI 개체를 사용하는 각 페이지에 대한 [OnPrint](#onprint) 멤버 함수 내에서 디바이스 컨텍스트로 GDI 개체를 선택합니다. 동일한 view 개체를 사용하여 화면 표시와 인쇄를 모두 수행하는 경우 각 화면 표시에 필요한 GDI 리소스에 별도의 변수를 사용합니다. 이렇게 하면 인쇄하는 동안 화면을 업데이트할 수 있습니다.

또한 이 함수를 사용하여 프린터 디바이스 컨텍스트의 속성에 따라 초기화를 수행할 수 있습니다. 예를 들어 문서를 인쇄하는 데 필요한 페이지 수는 사용자가 인쇄 대화 상자에서 지정한 설정(예: 페이지 길이)에 따라 다를 수 있습니다. 이러한 상황에서는 일반적인 경우와 달리 [OnPreparePrinting](#onprepareprinting) 멤버 함수에서 문서 길이를 지정할 수 없습니다. 대화 상자 설정에 따라 프린터 디바이스 컨텍스트가 만들어질 때까지 기다려야 합니다. [OnBeginPrinting](#onbeginprinting) 은 프린터 장치 컨텍스트를 나타내는 [CDC](../../mfc/reference/cdc-class.md) 개체에 대한 액세스를 제공하는 첫 번째 재정의 가능 함수이므로 이 함수에서 문서 길이를 설정할 수 있습니다. 이때까지 문서 길이를 지정하지 않으면 인쇄 미리 보기 중에 스크롤 막대가 표시되지 않습니다.

##  <a name="ondragenter"></a>  CView::OnDragEnter

마우스 놓기 대상 창의 스크롤되지 않는 지역에 먼저 들어가면 프레임 워크에서 호출 됩니다.

```
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pDataObject*<br/>
가리키는 합니다 [COleDataObject](../../mfc/reference/coledataobject-class.md) 뷰의 끌어 놓기 영역으로 끌고 있는 합니다.

*dwKeyState*<br/>
보조키의 상태를 포함합니다. 다음은 개수에 관계 없이 다음의 조합입니다. MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, 및 MK_RBUTTON 합니다.

*point*<br/>
마우스의 현재 위치 클라이언트 영역을 기준으로 보기.

### <a name="return-value"></a>반환 값

DROPEFFECT에서 값을 열거 drop 사용자이 위치에 있는 개체를 삭제 하는 경우 발생 하는 형식을 나타내는 형식입니다. Drop 유형의 일반적으로 나타난 현재 키 상태에 따라 달라 집니다 *dwKeyState*합니다. 표준 매핑의 keystates DROPEFFECT 값에는 다음과 같습니다.

- 이 창의 DROPEFFECT_NONE 데이터 개체를 삭제할 수 없습니다.

- DROPEFFECT_LINK MK_CONTROL에 대 한 &#124; MK_SHIFT 개체 및 해당 서버 간의 연결을 만듭니다.

- DROPEFFECT_COPY MK_CONTROL에 대 한 삭제 개체의 복사본을 만듭니다.

- DROPEFFECT_MOVE MK_ALT에 대 한 원래 개체를 삭제 하 고 삭제 개체의 복사본을 만듭니다. 이것이 일반적으로 기본 놓기 효과 뷰에이 데이터 개체 받아들일 수입니다.

자세한 내용은 MFC 고급 개념 샘플을 참조 하세요 [OCLIENT](../../overview/visual-cpp-samples.md)합니다.

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행 DROPEFFECT_NONE 반환 하는 것입니다.

이 함수에 대 한 이후 호출에 대 한 준비를 재정의 합니다 [OnDragOver](#ondragover) 멤버 함수입니다. 이번에 나중에 사용에 대 한 데이터 개체에서 필요한 모든 데이터를 검색 합니다 `OnDragOver` 멤버 함수입니다. 뷰를 사용자에 게 시각적 피드백을 제공 하려면이 이번에도 업데이트 되어야 합니다. 자세한 내용은 문서를 참조 하세요. [끌어다 놓습니다. 놓기 대상 구현](../../mfc/drag-and-drop-implementing-a-drop-target.md)합니다.

##  <a name="ondragleave"></a>  CView::OnDragLeave

해당 창에 대 한 유효한 놓기 영역 밖으로 마우스를 이동할 때 프레임 워크에서 끌기 작업 중 호출 합니다.

```
virtual void OnDragLeave();
```

### <a name="remarks"></a>설명

현재 보기 중에 수행 된 모든 작업을 정리 해야 할 경우이 함수를 재정의할 [OnDragEnter](#ondragenter) 하거나 [OnDragOver](#ondragover) 개체를 끌어서 놓을 때 시각적 사용자 피드백을 제거 하는 등 호출 .

##  <a name="ondragover"></a>  CView::OnDragOver

놓기 대상 창 위로 마우스를 이동 하는 경우 프레임 워크에서 끌기 작업 중 호출 합니다.

```
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pDataObject*<br/>
가리키는 합니다 [COleDataObject](../../mfc/reference/coledataobject-class.md) 놓기 대상 위로 끄는 합니다.

*dwKeyState*<br/>
보조키의 상태를 포함합니다. 다음은 개수에 관계 없이 다음의 조합입니다. MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, 및 MK_RBUTTON 합니다.

*point*<br/>
뷰 클라이언트 영역을 기준으로 현재 마우스 위치를 지정 합니다.

### <a name="return-value"></a>반환 값

DROPEFFECT에서 값을 열거 drop 사용자이 위치에 있는 개체를 삭제 하는 경우 발생 하는 형식을 나타내는 형식입니다. Drop 유형의 현재 키 상태에 나타난 것 처럼 종종 따라 *dwKeyState*합니다. 표준 매핑의 keystates DROPEFFECT 값에는 다음과 같습니다.

- 이 창의 DROPEFFECT_NONE 데이터 개체를 삭제할 수 없습니다.

- DROPEFFECT_LINK MK_CONTROL에 대 한 &#124; MK_SHIFT 개체 및 해당 서버 간의 연결을 만듭니다.

- DROPEFFECT_COPY MK_CONTROL에 대 한 삭제 개체의 복사본을 만듭니다.

- DROPEFFECT_MOVE MK_ALT에 대 한 원래 개체를 삭제 하 고 삭제 개체의 복사본을 만듭니다. 이것이 일반적으로 기본 놓기 효과 보기 데이터 개체를 받아들일 수입니다.

자세한 내용은 MFC 고급 개념 샘플을 참조 하세요 [OCLIENT](../../overview/visual-cpp-samples.md)합니다.

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행 하 여 DROPEFFECT_NONE 반환 합니다.

끌기 작업 중 사용자 시각적 피드백을 제공 하려면이 함수를 재정의 합니다. 이 함수를 지속적으로 호출 되므로 그 안에 포함 된 모든 코드 최적화 해야 최대한 많이 있습니다. 자세한 내용은 문서를 참조 하세요. [끌어다 놓습니다. 놓기 대상 구현](../../mfc/drag-and-drop-implementing-a-drop-target.md)합니다.

##  <a name="ondragscroll"></a>  CView::OnDragScroll

호출 하기 전에 프레임 워크에서 호출 [OnDragEnter](#ondragenter) 또는 [OnDragOver](#ondragover) 스크롤 영역에는 지점 인지 여부를 확인 합니다.

```
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*dwKeyState*<br/>
보조키의 상태를 포함합니다. 다음은 개수에 관계 없이 다음의 조합입니다. MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON, 및 MK_RBUTTON 합니다.

*point*<br/>
커서를 화면을 기준으로 픽셀의 위치를 포함 합니다.

### <a name="return-value"></a>반환 값

DROPEFFECT에서 값을 열거 drop 사용자이 위치에 있는 개체를 삭제 하는 경우 발생 하는 형식을 나타내는 형식입니다. Drop 유형의 일반적으로 나타난 현재 키 상태에 따라 달라 집니다 *dwKeyState*합니다. 표준 매핑의 keystates DROPEFFECT 값에는 다음과 같습니다.

- 이 창의 DROPEFFECT_NONE 데이터 개체를 삭제할 수 없습니다.

- DROPEFFECT_LINK MK_CONTROL에 대 한 &#124; MK_SHIFT 개체 및 해당 서버 간의 연결을 만듭니다.

- DROPEFFECT_COPY MK_CONTROL에 대 한 삭제 개체의 복사본을 만듭니다.

- DROPEFFECT_MOVE MK_ALT에 대 한 원래 개체를 삭제 하 고 삭제 개체의 복사본을 만듭니다.

- DROPEFFECT_SCROLL 끌기 스크롤 작업을 수행 하려고 합니다. 또는 대상 뷰에서 발생 했음을 나타냅니다.

자세한 내용은 MFC 고급 개념 샘플을 참조 하세요 [OCLIENT](../../overview/visual-cpp-samples.md)합니다.

### <a name="remarks"></a>설명

이 이벤트에 대 한 특별 한 동작을 제공 하려는 경우이 함수를 재정의 합니다. 기본 구현은 각 창의 테두리 내 기본 스크롤 영역에 커서를 끌 때 자동으로 windows를 스크롤합니다. 자세한 내용은 문서를 참조 하세요. [끌어다 놓습니다. 놓기 대상 구현](../../mfc/drag-and-drop-implementing-a-drop-target.md)합니다.

##  <a name="ondraw"></a>  CView::OnDraw

문서의 이미지를 렌더링 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnDraw(CDC* pDC) = 0;
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
문서의 이미지 렌더링에 사용 되는 장치 컨텍스트를 가리킵니다.

### <a name="remarks"></a>설명

프레임 워크가 화면 표시, 인쇄 및 인쇄 미리 보기를 수행 하려면이 함수를 호출 하 고 각각의 경우에서 다른 장치 컨텍스트를 전달 합니다. 기본 구현은 없습니다.

문서의 뷰를 표시 하려면이 함수를 재정의 해야 합니다. 사용 하 여 그래픽 장치 인터페이스 (GDI) 호출을 만들 수는 [CDC](../../mfc/reference/cdc-class.md) 가리키는 개체를 *pDC* 매개 변수입니다. 그리기 전에 장치 컨텍스트로 GDI 리소스, 예: 펜 또는 글꼴을 선택 하 고 선택을 취소 하 고 나중에 수 있습니다. 종종 그리기 코드 장치 독립적인; 수 있습니다. 즉, 해당 이미지를 표시 하는 장치의 종류에 대 한 정보를 필요 하지 않습니다.

그리기를 최적화 하려면 호출을 [RectVisible](../../mfc/reference/cdc-class.md#rectvisible) 지정 된 사각형을 그릴지 여부를 확인 하려면 장치 컨텍스트의 멤버 함수입니다. 일반적인 화면 표시 및 인쇄를 구분 하는 경우 호출 된 [IsPrinting](../../mfc/reference/cdc-class.md#isprinting) 장치 컨텍스트의 멤버 함수입니다.

##  <a name="ondrop"></a>  CView::OnDrop

유효한 놓기 대상 위에 데이터 개체를 놓을 때 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnDrop(
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

' pDataObject * 가리키는 합니다 [COleDataObject](../../mfc/reference/coledataobject-class.md) 놓기 대상으로 하는 삭제 됩니다.

*dropEffect*<br/>
사용자가 요청한 놓기 효과입니다.

- DROPEFFECT_COPY 삭제할 데이터 개체의 복사본을 만듭니다.

- DROPEFFECT_MOVE 현재 마우스 위치에 데이터 개체를 이동합니다.

- DROPEFFECT_LINK은 데이터 개체와 해당 서버 간의 링크를 만듭니다.

*point*<br/>
뷰 클라이언트 영역을 기준으로 현재 마우스 위치를 지정 합니다.

### <a name="return-value"></a>반환 값

드롭다운에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행 하지 하 고 FALSE를 반환 합니다.

보기의 클라이언트 영역으로 OLE 놓기의 효과 구현 하려면이 함수를 재정의 합니다. 데이터 개체를 통해 검사할 수 있습니다 *pDataObject* 클립보드 데이터 형식 및 데이터 삭제 지정된 된 지점에 있습니다.

> [!NOTE]
>  프레임 워크를 재정의 하는 경우이 함수를 호출 하지 않습니다 [OnDropEx](#ondropex) 이 뷰 클래스에 있습니다.

##  <a name="ondropex"></a>  CView::OnDropEx

유효한 놓기 대상 위에 데이터 개체를 놓을 때 프레임 워크에서 호출 됩니다.

```
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pDataObject*<br/>
가리키는 합니다 [COleDataObject](../../mfc/reference/coledataobject-class.md) 놓기 대상으로 하는 삭제 됩니다.

*dropDefault*<br/>
현재 키 상태를 기반으로 기본 놓기 작업에 대 한 사용자가 선택 하는 효과입니다. DROPEFFECT_NONE 수도 있습니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 합니다.

*dropList*<br/>
목록 놓기 소스가 지원 되는 놓기 효과입니다. 비트 OR를 사용 하 여 드롭 효과 값을 결합할 수 있습니다 ( **&#124;**) 작업입니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 합니다.

*point*<br/>
뷰 클라이언트 영역을 기준으로 현재 마우스 위치를 지정 합니다.

### <a name="return-value"></a>반환 값

지정 된 위치에서 삭제 시도에서 발생 하는 놓기 효과 *지점*합니다. 지정 된 값 중 하나 이어야 합니다 *dropEffectList*합니다. 끌어서 놓기 작업 결과 주의 섹션에 설명 합니다.

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행 하 고 프레임 워크를 호출 하는 것을 나타내려면 더미 값 (-1)을 반환 하는 것은 [OnDrop](#ondrop) 처리기입니다.

이 함수를 마우스 오른쪽 단추 끌어서 놓기 효과 구현 하려면 재정의 합니다. 마우스 오른쪽 단추 끌어서 놓기 일반적으로 표시 메뉴 선택 마우스 오른쪽 단추를 놓을 때.

재정의가 `OnDropEx` 를 마우스 오른쪽 단추를 쿼리해야 합니다. 호출할 수 있습니다 [GetKeyState](/windows/desktop/api/winuser/nf-winuser-getkeystate) 에서 마우스 오른쪽 단추 상태를 저장할 사용자 [OnDragEnter](#ondragenter) 처리기입니다.

- 마우스 오른쪽 단추 다운 된 경우 재정의 놓기 소스에서 지 원하는 놓기 효과 제공 하는 팝업 메뉴가 표시 됩니다.

   - 검사할 *드롭 목록* 놓기 원본에서 지 원하는 놓기 효과 확인 하려면. 팝업 메뉴에서 이러한 작업에만 사용 하도록 설정 합니다.

   - 사용 하 여 [SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem) 기반으로 기본 동작을 설정 하려면 *dropDefault*합니다.

   - 마지막으로, 팝업 메뉴에서 사용자 선택 항목으로 표시 된 작업을 수행 합니다.

- 마우스 오른쪽 단추를 아래쪽 없는 경우 재정의 처리 해야이 표준 삭제 요청으로 합니다. 에 지정 된 효과 사용 하 여 *dropDefault*합니다. 재정의 나타내는 더미 값 (-1)을 반환할 수 있습니다 또는 `OnDrop` 이 놓기 작업을 처리 합니다.

사용 하 여 *pDataObject* 검사할는 `COleDataObject` 클립보드 데이터 형식 및 데이터 삭제 지정된 된 지점에 있습니다.

끌어서 놓기 작업 결과 놓기 작업을 사용 하 여 연결 된 동작을 설명 합니다. 끌어서 놓기 작업 결과의 다음 목록을 참조 하세요.

- DROPEFFECT_NONE 저장이 허용 되지 않습니다.

- DROPEFFECT_COPY 복사 작업이 수행 됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행 됩니다.

- DROPEFFECT_LINK 링크에서 끌어 놓은 데이터를 원본 데이터를 설정 됩니다.

- DROPEFFECT_SCROLL 끌기 스크롤 작업을 수행 하려고 합니다. 또는 대상에서 발생 했음을 나타냅니다.

기본 메뉴 명령을 설정에 대 한 자세한 내용은 참조 하세요. [SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem) Windows sdk에서 및 [CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu) 이 볼륨에 있습니다.

##  <a name="onendprinting"></a>  CView::OnEndPrinting

문서 인쇄 되거나 미리 본 후 프레임 워크에서 호출 됩니다.

```
virtual void OnEndPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 디바이스 컨텍스트를 가리킵니다.

*pInfo*<br/>
현재 인쇄 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체를 가리킵니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 에 할당 된 GDI 리소스를 해제 하려면이 함수를 재정의 합니다 [OnBeginPrinting](#onbeginprinting) 멤버 함수입니다.

##  <a name="onendprintpreview"></a>  CView::OnEndPrintPreview

사용자가 인쇄 미리 보기 모드를 종료할 때 프레임 워크에서 호출 됩니다.

```
virtual void OnEndPrintPreview(
    CDC* pDC,
    CPrintInfo* pInfo,
    POINT point,
    CPreviewView* pView);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 디바이스 컨텍스트를 가리킵니다.

*pInfo*<br/>
현재 인쇄 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체를 가리킵니다.

*point*<br/>
미리 보기 모드에서 마지막으로 표시 된 페이지에 지정 합니다.

*pView*<br/>
미리 보기에 사용 되는 뷰 개체를 가리킵니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현을 호출 합니다 [OnEndPrinting](#onendprinting) 주 프레임 창을 인쇄 미리 보기 이전 상태로 시작 하는 멤버 함수 및 복원 합니다. 미리 보기 모드 종료 될 때 특수 한 처리를 수행 하려면이 함수를 재정의 합니다. 예를 들어, 미리 보기 모드에서 일반적인 표시 모드를 전환 하는 경우 문서의 사용자의 위치를 유지 하려는 경우 스크롤할 수 있습니다 위치에서 설명 하는 *가리킨* 매개 변수 및 `m_nCurPage` 합니다 소속`CPrintInfo` 는 구조체를 *pInfo* 매개 변수를 가리킵니다.

기본 클래스 버전을 항상 호출 `OnEndPrintPreview` 에서 함수의 끝에 일반적으로 재정의 합니다.

##  <a name="oninitialupdate"></a>  CView::OnInitialUpdate

전에 호출 됩니다 프레임 워크에서 뷰를 먼저 문서에 연결한 후 뷰 처음에 표시 됩니다.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>설명

이 함수의 기본 구현을 호출 합니다 [OnUpdate](#onupdate) 힌트 정보 없이 멤버 함수 (즉, 0에 대 한 기본값을 사용 하는 *lHint* 매개 변수 및 NULL에 대 한는  *pHint* 매개 변수). 문서에 대 한 정보를 필요로 하는 일회 초기화를 수행 하려면이 함수를 재정의 합니다. 예를 들어, 응용 프로그램에 고정 크기 문서를 뷰의 스크롤 제한 문서 크기를 기준으로 초기화 하려면이 함수를 사용할 수 있습니다. 사용 하 여 응용 프로그램에서 가변 크기의 문서를 지 원하는 경우 [OnUpdate](#onupdate) 스크롤 업데이트 제한 될 때마다 문서 변경 합니다.

##  <a name="onpreparedc"></a>  CView::OnPrepareDC

전에 프레임 워크에서 호출 합니다 [OnDraw](#ondraw) 전과 화면 표시에 대 한 구성원 함수가 호출 되는 [OnPrint](#onprint) 인쇄 또는 인쇄 미리 보기 기간 동안 각 페이지에 대 한 멤버 함수를 호출 합니다.

```
virtual void OnPrepareDC(
    CDC* pDC,
    CPrintInfo* pInfo = NULL);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
문서의 이미지 렌더링에 사용 되는 장치 컨텍스트를 가리킵니다.

*pInfo*<br/>
가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 경우 현재 인쇄 작업을 설명 하는 구조 `OnPrepareDC` 인쇄 또는 인쇄 미리 보기에 호출 되는 `m_nCurPage` 멤버 인쇄할 페이지 지정 합니다. 이 매개 변수는 NULL 경우 `OnPrepareDC` 화면 표시를 위해 호출 되 고 있습니다.

### <a name="remarks"></a>설명

화면 표시에 대 한 함수를 호출 하는 경우이 함수의 기본 구현은 아무 작업도 수행 하지. 그러나이 함수는 파생된 클래스에서 재정의와 같은 [CScrollView](../../mfc/reference/cscrollview-class.md); 장치 컨텍스트의 특성을 조정 하려면, 결과적으로 기본 클래스 구현을 재정의 맨 앞에 호출 항상 해야 합니다.

기본 구현에서는 검사에 저장 된 페이지 정보를 인쇄에 대 한 함수를 호출 하면 합니다 *pInfo* 매개 변수입니다. 문서의 길이 지정 하지 `OnPrepareDC` 문서 1 페이지 짜리를 가정 하 고 한 페이지를 인쇄 후 인쇄 루프를 중지 합니다. 설정 하 여 인쇄 루프를 중지 하는 함수는 `m_bContinuePrinting` FALSE로 구조체의 멤버입니다.

재정의 `OnPrepareDC` 다음 이유 중 하나:

- 지정된 된 페이지에 대 한 필요에 따라 장치 컨텍스트의 특성을 조정 합니다. 예를 들어, 매핑 모드 또는 장치 컨텍스트의 다른 특성을 설정 하는 경우이 함수에서 수행 합니다.

- 인쇄 하면서 페이지 매기기를 수행 합니다. 사용 하 여 인쇄를 시작할 때 문서 길이 지정 하는 일반적으로 [OnPreparePrinting](#onprepareprinting) 멤버 함수입니다. 그러나 기간을 미리 문서 (예를 들어, 인쇄할 때 레코드 수를 지정 하지 않은 데이터베이스에서)를 알 수 없는 경우, 재정의 `OnPrepareDC` 인쇄 되는 동안 문서 끝에 대 한 테스트 합니다. 있으면 문서 인쇄를 더 이상 설정 합니다 `m_bContinuePrinting` 의 멤버는 `CPrintInfo` 구조 FALSE로 합니다.

- 페이지 단위로 프린터 이스케이프 코드를 보냅니다. 이스케이프 코드를 보낼 `OnPrepareDC`를 호출 합니다 `Escape` 멤버 함수는 *pDC* 매개 변수입니다.

기본 클래스 버전을 호출 `OnPrepareDC` 재정의의 시작 부분입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#183](../../mfc/codesnippet/cpp/cview-class_1.cpp)]

##  <a name="onprepareprinting"></a>  CView::OnPreparePrinting

문서는 인쇄 하거나 미리 보기 전에 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>매개 변수

*pInfo*<br/>
현재 인쇄 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체를 가리킵니다.

### <a name="return-value"></a>반환 값

Nonzero; 인쇄 하려면 인쇄 작업이 취소 된 경우 0입니다.

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행하지 않습니다.

인쇄 및 인쇄 미리 보기를 사용 하도록 설정 하려면이 함수를 재정의 해야 합니다. 호출 된 [DoPreparePrinting](#doprepareprinting) 멤버 함수에 전달 합니다 *pInfo* 매개 변수를 다음 해당 반환 값을 반환 `DoPreparePrinting` 인쇄 대화 상자를 표시 하 고 프린터 장치 컨텍스트를 만듭니다. 기본값 이외의 값을 사용 하 여 인쇄 대화 상자를 초기화 하려는 경우 멤버에 값을 할당 *pInfo*합니다. 예를 들어, 문서 길이 알고 있는 경우 값을 전달 합니다 [SetMaxPage](../../mfc/reference/cprintinfo-structure.md#setmaxpage) 멤버 함수 *pInfo* 호출 하기 전에 `DoPreparePrinting`입니다. 이 값의에서 표시 됩니다: 인쇄 대화 상자에서 범위 부분의 상자입니다.

`DoPreparePrinting` 미리 보기 작업에 대 한 인쇄 대화 상자를 표시 되지 않습니다. 인쇄 작업에 대 한 인쇄 대화 상자를 무시 하려는 경우 확인 합니다 `m_bPreview` 소속 *pInfo* FALSE이 고 전달 하기 전에 TRUE로 설정 `DoPreparePrinting`; 나중에 FALSE로 다시 설정 합니다.

에 대 한 액세스를 필요로 하는 초기화를 수행 해야 하는 경우는 `CDC` 재정의 (예를 들어 문서 길이 지정 하기 전에 페이지 크기를 알아야 하는 경우), 프린터 장치 컨텍스트를 나타내는 개체를 `OnBeginPrinting` 멤버 함수입니다.

값을 설정 하려는 경우는 `m_nNumPreviewPages` 또는 `m_strPageDesc` 의 멤버는 *pInfo* 매개 변수를 호출한 후 작업을 수행 `DoPreparePrinting`합니다. `DoPreparePrinting` 멤버 함수 집합 `m_nNumPreviewPages` 응용 프로그램에서 찾을 값입니다. INI 파일을 설정 하 고 `m_strPageDesc` 를 기본값으로 합니다.

### <a name="example"></a>예제

  재정의 `OnPreparePrinting` 호출 `DoPreparePrinting` 재정의에서 프레임 워크는 인쇄 대화 상자를 표시 되 고 프린터 DC 생성 되도록 합니다.

[!code-cpp[NVC_MFCDocView#184](../../mfc/codesnippet/cpp/cview-class_2.cpp)]

문서를 포함 하는 페이지 수를 알고 있는 경우 최대 페이지에서 설정할 `OnPreparePrinting` 호출 하기 전에 `DoPreparePrinting`입니다. 프레임 워크는 최대 페이지 번호를 인쇄 대화 상자의 "to" 상자에 표시 됩니다.

[!code-cpp[NVC_MFCDocView#185](../../mfc/codesnippet/cpp/cview-class_3.cpp)]

##  <a name="onprint"></a>  CView::OnPrint

인쇄 문서 페이지를 미리 보거나 프레임 워크에서 호출 됩니다.

```
virtual void OnPrint(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 디바이스 컨텍스트를 가리킵니다.

*pInfo*<br/>
가리키는 `CPrintInfo` 현재 인쇄 작업을 설명 하는 구조입니다.

### <a name="remarks"></a>설명

인쇄 하 고 각 페이지에 대 한 프레임 워크를 호출한 후 즉시이 함수를 호출 합니다 [OnPrepareDC](#onpreparedc) 멤버 함수입니다. 인쇄 페이지로 지정 됩니다 합니다 `m_nCurPage` 의 멤버는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체입니다 *pInfo* 가리킵니다. 기본 구현 호출 합니다 [OnDraw](#ondraw) 멤버 함수 프린터 장치 컨텍스트를 전달 합니다.

다음 이유 중 하나에 대 한이 함수를 재정의 합니다.

- 다중 페이지 문서 인쇄를 허용 합니다. 현재 인쇄 중인 페이지에 해당 하는 문서의 부분만을 렌더링 합니다. 사용 중인 경우 `OnDraw` 렌더링을 수행 하려면 조정할 수 있습니다 뷰포트 원본 문서의 적절 한 부분만 인쇄 되도록 합니다.

- 인쇄 된 이미지 (즉, 응용 프로그램이 없는 경우 WYSIWYG) 화면 이미지와 다르게 보일 수 있도록 합니다. 프린터 장치 컨텍스트를 전달 하는 대신 `OnDraw`, 화면에 표시 되지 않습니다 하는 특성을 사용 하 여 이미지를 렌더링 하 고 장치 컨텍스트를 사용 합니다.

   GDI 리소스 화면 표시가 사용 하지 않는 인쇄 해야 그리기 전에 장치 컨텍스트로 선택 하 고 나중에 선택 취소 합니다. 이러한 GDI 리소스에 할당 해야 [OnBeginPrinting](#onbeginprinting) 에 출시 하 고 [OnEndPrinting](#onendprinting)합니다.

- 머리글 또는 바닥글을 구현 합니다. 계속 사용할 수 있습니다 `OnDraw` 에 인쇄할 수 있는 영역을 제한 하 여 렌더링을 수행 합니다.

합니다 `m_rectDraw` 의 멤버는 *pInfo* 논리 단위에서 페이지의 인쇄 가능한 영역을 설명 하는 매개 변수입니다.

호출 하지 마세요 `OnPrepareDC` 의 재정의 `OnPrint`고 프레임 워크 호출 `OnPrepareDC` 호출 하기 전에 자동으로 `OnPrint`입니다.

### <a name="example"></a>예제

다음은 재정의 된에 대 한 기본 구조 `OnPrint` 함수:

[!code-cpp[NVC_MFCDocView#186](../../mfc/codesnippet/cpp/cview-class_4.cpp)]

다른 예제를 보려면 [CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect)합니다.

##  <a name="onscroll"></a>  CView::OnScroll

스크롤 여부를 확인 하기 위해 프레임 워크에서 호출 가능 합니다.

```
virtual BOOL OnScroll(
    UINT nScrollCode,
    UINT nPos,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>매개 변수

*nScrollCode*<br/>
사용자를 나타내는 스크롤 막대 코드를 요청을 스크롤의입니다. 이 매개 변수는 두 부분으로 구성 됩니다: 가로 스크롤 발생의 형식을 결정을 낮은 순서 바이트 및 세로로 스크롤 발생의 형식을 결정 하는 상위 바이트:

- 아래로 SB_BOTTOM 스크롤입니다.

- 한 줄 아래로 SB_LINEDOWN 스크롤합니다.

- 한 줄 위로 SB_LINEUP 스크롤합니다.

- 한 페이지 아래로 SB_PAGEDOWN 스크롤합니다.

- 한 페이지 위로 SB_PAGEUP 스크롤합니다.

- SB_THUMBTRACK 끌기 상자를 지정 된 위치로 스크롤합니다. 현재 위치에 지정 된 *nPos*합니다.

- 맨 위로 이동 SB_TOP 스크롤입니다.

*nPos*<br/>
스크롤 막대 코드가 SB_THUMBTRACK; 이면 현재 스크롤 상자 위치를 포함 합니다. 그렇지 않으면 사용 되지 않습니다. 초기 스크롤 범위에 따라 *nPos* 음수가 될 수 있습니다 및로 캐스팅 해야는 **int** 필요한 경우.

*bDoScroll*<br/>
지정 된 스크롤 작업을 실제로 수행 해야 하는지 여부를 결정 합니다. TRUE 이면 다음 스크롤 이루어져야; FALSE 이면 다음 스크롤 발생 하지 않습니다.

### <a name="return-value"></a>반환 값

하는 경우 *bDoScroll* 돌아와서이 고 그렇지 않으면 0이 아닌가 TRUE이 고 뷰를 스크롤한 실제로 0입니다. 하는 경우 *bDoScroll* FALSE를 반환 하는 경우 반환 값은 *bDoScroll* 스크롤 실제로 수행 하지 않는 경우에 TRUE 되었습니다.

### <a name="remarks"></a>설명

한 경우이 함수는 사용 하 여 프레임 워크에서 호출 됩니다 *bDoScroll* 뷰 스크롤 메시지를 받으면 TRUE로 설정 합니다. 이 경우 뷰를 실제로 스크롤하여 해야 있습니다. 다른 경우에서이 함수를 호출 *bDoScroll* 스크롤 실제로 수행 하기 전에 놓기 대상의 자동 스크롤 영역으로 처음 OLE 항목을 끌 때 FALSE로 설정 합니다. 이 경우 해야 하지 실제로 스크롤하면 보기.

##  <a name="onscrollby"></a>  CView::OnScrollBy

사용자 또는 보기의 현재 테두리에 대 한 OLE 항목을 끌어 세로 또는 가로 스크롤 막대를 조작 하 여 문서에 있는 보기를 넘는 영역을 볼 때 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnScrollBy(
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>매개 변수

*sizeScroll*<br/>
가로 및 세로로 스크롤의 픽셀 수입니다.

*bDoScroll*<br/>
뷰 스크롤 발생 하는지 여부를 결정 합니다. TRUE 이면 다음 스크롤 이루어집니다; FALSE 이면 다음 스크롤 발생 하지 않습니다.

### <a name="return-value"></a>반환 값

뷰; 스크롤할 수 있으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

파생된 클래스에서이 메서드는 보기를 요청 하 고 그런 다음 필요한 경우 새 영역을 업데이트 하는 사용자 방향으로 스크롤할 수 있는지 여부를 확인 합니다. 자동으로 호출 되는이 함수 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) 하 고 [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) 실제 스크롤 요청을 수행할 수 있습니다.

이 메서드의 기본 구현은 보기를 변경 되지 않지만 뷰에 호출 하지 않으면에서 움직이지 것입니다는 `CScrollView`-클래스를 파생 합니다.

문서 너비 또는 높이 픽셀 32767을 초과 하면 32767 스크롤할 못하여 `OnScrollBy` 잘못 된 라고 *sizeScroll* 인수입니다.

##  <a name="onupdate"></a>  CView::OnUpdate

보기의 문서가 수정 되었습니다; 후에 프레임 워크에서 호출 합니다. 이 함수는 호출한 [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) 하면 이러한 수정 내용을 반영 하도록 해당 디스플레이를 업데이트 하 고 있습니다.

```
virtual void OnUpdate(
    CView* pSender,
    LPARAM lHint,
    CObject* pHint);
```

### <a name="parameters"></a>매개 변수

*pSender*<br/>
문서를 수정 하는 뷰를 가리키는 모든 뷰는 업데이트할 경우 null입니다.

*lHint*<br/>
수정 작업에 대 한 정보를 포함합니다.

*pHint*<br/>
수정 작업에 대 한 정보를 저장 하는 개체를 가리킵니다.

### <a name="remarks"></a>설명

기본 구현에 의해 라고도 [OnInitialUpdate](#oninitialupdate)합니다. 기본 구현은 다음 WM_PAINT 메시지를 받을 때 그리기에 대 한 표시 하 고 전체 클라이언트 영역을 무효화 합니다. 문서의 수정된 부분에 매핑되는 지역만 업데이트 하려는 경우이 함수를 재정의 합니다. 이렇게 하려면 힌트 매개 변수를 사용 하 여 수정 작업에 대 한 정보를 전달 해야 합니다.

사용 하도록 *lHint*, 비트 마스크 또는 열거 형식, 특수 힌트 값을 정의 하 고 문서가 이러한 값 중 하나를 전달 합니다. 사용 하 *pHint*에서 힌트 클래스를 파생 [CObject](../../mfc/reference/cobject-class.md) 재정의 하는 경우 힌트 개체;에 대 한 포인터를 전달 하는 문서 및 `OnUpdate`를 사용 합니다 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) 힌트 개체의 런타임 형식을 확인 하려면 멤버 함수입니다.

일반적으로 수행 하지 말아야에서 직접 그리는 모든 `OnUpdate`합니다. 대신, 장치 좌표에서 업데이트; 필요한 영역을 설명 하는 사각형을 결정 하기 이 사각형에 전달 [CWnd::InvalidateRect](../../mfc/reference/cwnd-class.md#invalidaterect)합니다. 이렇게 하면 다음에 발생 하는 그리기를 [WM_PAINT](/windows/desktop/gdi/wm-paint) 메시지를 수신 합니다.

하는 경우 *lHint* 은 0 및 *pHint* 가 null 인 경우 문서 일반 업데이트 알림을 보냈습니다. 뷰를 일반 업데이트 알림을 수신 하는 경우, 힌트를 디코딩할 수 없는 경우 전체 클라이언트 영역을 무효화 해야 것입니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[CSplitterWnd 클래스](../../mfc/reference/csplitterwnd-class.md)<br/>
[CDC 클래스](../../mfc/reference/cdc-class.md)<br/>
[CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[CDocument 클래스](../../mfc/reference/cdocument-class.md)
