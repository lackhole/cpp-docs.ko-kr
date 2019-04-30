---
title: CCtrlView 클래스
ms.date: 11/04/2016
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
helpviewer_keywords:
- CCtrlView [MFC], CCtrlView
- CCtrlView [MFC], OnDraw
- CCtrlView [MFC], PreCreateWindow
- CCtrlView [MFC], m_dwDefaultStyle
- CCtrlView [MFC], m_strClass
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
ms.openlocfilehash: 5cb68ab46e2cac8b2f1dcc13989077e32480a2c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262608"
---
# <a name="cctrlview-class"></a>CCtrlView 클래스

문서 뷰 아키텍처를 Windows 98 및 Windows NT 버전 3.51 이상에서 지원하는 공통의 컨트롤에 맞게 변경합니다.

## <a name="syntax"></a>구문

```
class CCtrlView : public CView
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CCtrlView::CCtrlView](#cctrlview)|`CCtrlView` 개체를 생성합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CCtrlView::OnDraw](#ondraw)|지정 된 디바이스 컨텍스트를 사용 하 여 그리기 위해 프레임 워크에서 호출 됩니다.|
|[CCtrlView::PreCreateWindow](#precreatewindow)|이 `CCtrlView` 개체에 연결된 Windows 창을 만들기 전에 호출됩니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|뷰 클래스에 대 한 기본 스타일을 포함합니다.|
|[CCtrlView::m_strClass](#m_strclass)|뷰 클래스에 대 한 Windows 클래스 이름을 포함합니다.|

## <a name="remarks"></a>설명

클래스 `CCtrlView` 및 해당 파생 항목 [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), 및 [CRichEditView](../../mfc/reference/cricheditview-class.md)를 조정 합니다 새 공용 컨트롤을 문서 뷰 아키텍처 지원 Windows 95/98 및 Windows NT 버전 3.51 이상. 문서-뷰 아키텍처에 대 한 자세한 내용은 참조 하세요. [문서/뷰 아키텍처](../../mfc/document-view-architecture.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CCtrlView`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cctrlview"></a>  CCtrlView::CCtrlView

`CCtrlView` 개체를 생성합니다.

```
CCtrlView(
    LPCTSTR lpszClass,
    DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*lpszClass*<br/>
Windows 뷰 클래스의 클래스 이름입니다.

*dwStyle*<br/>
뷰 클래스의 스타일입니다.

### <a name="remarks"></a>설명

새 프레임 창 개체를 만들거나 창을 분할 하는 경우 생성자를 호출 하는 프레임 워크. 재정의 [cview:: Oninitialupdate](../../mfc/reference/cview-class.md#oninitialupdate) 문서를 연결한 후에 뷰를 초기화할 수 있습니다. 호출 [CWnd::Create](../../mfc/reference/cwnd-class.md#create) 하거나 [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) Windows 개체를 만듭니다.

##  <a name="m_strclass"></a>  CCtrlView::m_strClass

뷰 클래스에 대 한 Windows 클래스 이름을 포함합니다.

```
CString m_strClass;
```

##  <a name="m_dwdefaultstyle"></a>  CCtrlView::m_dwDefaultStyle

뷰 클래스에 대 한 기본 스타일을 포함합니다.

```
DWORD m_dwDefaultStyle;
```

### <a name="remarks"></a>설명

이 스타일을 창을 만들 때 적용 됩니다.

##  <a name="ondraw"></a>  CCtrlView::OnDraw

콘텐츠를 그리기 위해 프레임 워크에서 호출 된 `CCtrlView` 지정 된 디바이스 컨텍스트를 사용 하 여 개체입니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
그리기 발생 하는 장치 컨텍스트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`OnDraw` 지정 된 화면 장치 컨텍스트를 전달 되는 화면 표시를 위해 일반적으로 라고 *pDC*합니다.

##  <a name="precreatewindow"></a>  CCtrlView::PreCreateWindow

이 `CWnd` 개체에 연결된 Windows 창을 만들기 전에 호출됩니다.

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>매개 변수

*cs*<br/>
A [CREATESTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcreatestructa) 구조입니다.

### <a name="return-value"></a>반환 값

창 만들기를 계속 해야 하는 경우 0이 아닌 값 만들기 실패를 나타내는 0입니다.

### <a name="remarks"></a>설명

이 함수를 직접 호출 하지 않습니다.

이 함수의 기본 구현은 NULL 창 클래스 이름을 확인 하 고 적절 한 기본값을 대체 합니다. 수정 하려면이 멤버 함수를 재정의 합니다 `CREATESTRUCT` 창이 생성 되기 전에 구조체입니다.

각 클래스에서 파생 `CCtrlView` 해당 재정의에 고유한 기능을 추가 `PreCreateWindow`합니다. 기본적으로의 이러한 파생 `PreCreateWindow` 설명 하지 않습니다. 각 클래스 및 스타일 간 상호 종속성에 적절 한 스타일을 확인 하려면 응용 프로그램의 기본 클래스에 대 한 MFC 소스 코드를 검사할 수 있습니다. 재정의 하려는 경우 `PreCreateWindow`, 응용 프로그램의 기본 클래스에서 사용 된 스타일 MFC 소스 코드에서 수집 된 정보를 사용 하 여 필요한 기능을 제공 하는지 여부를 확인할 수 있습니다.

창 스타일 변경에 대 한 자세한 내용은 참조는 [MFC에서 만든 창 스타일 변경](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md)합니다.

## <a name="see-also"></a>참고자료

[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CTreeView 클래스](../../mfc/reference/ctreeview-class.md)<br/>
[CListView 클래스](../../mfc/reference/clistview-class.md)<br/>
[CRichEditView 클래스](../../mfc/reference/cricheditview-class.md)
