---
title: CHtmlEditView 클래스
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
ms.openlocfilehash: 8267a5272d2d542c4679bf30aa9d3ad8b933d81d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767212"
---
# <a name="chtmleditview-class"></a>CHtmlEditView 클래스

MFC의 문서/뷰 아키텍처 컨텍스트 내에서 WebBrowser 편집 플랫폼의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|`CHtmlEditView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CHtmlEditView::Create](#create)|새 창 개체를 만듭니다.|
|[CHtmlEditView::GetDHtmlDocument](#getdhtmldocument)|반환 된 `IHTMLDocument2` 현재 문서에 대 한 인터페이스입니다.|
|[CHtmlEditView::GetStartDocument](#getstartdocument)|이 보기에 대 한 기본 문서의 이름을 검색합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CHtmlView](../../mfc/reference/chtmlview-class.md)

`CHtmlEditView`

## <a name="requirements"></a>요구 사항

**헤더:** afxhtml.h

##  <a name="chtmleditview"></a>  CHtmlEditView::CHtmlEditView

`CHtmlEditView` 개체를 생성합니다.

```
CHtmlEditView();
```

##  <a name="create"></a>  CHtmlEditView::Create

새 창 개체를 만듭니다.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>
Windows 클래스의 이름을 지정 하는 null로 끝나는 문자열을 가리킵니다. 클래스 이름을 사용 하 여 등록 된 모든 이름 수는 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 전역 함수 또는 `RegisterClass` Windows 함수입니다. NULL 인 경우 미리 정의 된 기본값을 사용 하 여 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 특성입니다.

*lpszWindowName*<br/>
창 이름을 나타내는 null로 끝나는 문자열을 가리킵니다.

*dwStyle*<br/>
창 스타일 특성을 지정합니다. WS_VISIBLE 및 WS_CHILD Windows 스타일은 기본적으로 설정 됩니다.

*rect*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조 크기와 창의 위치를 지정 합니다. 합니다 *rectDefault* 값 크기와 새 창의 위치를 지정 하는 Windows를 허용 합니다.

*pParentWnd*<br/>
컨트롤의 부모 창에 대 한 포인터입니다.

*nID*<br/>
뷰의 ID. 기본적으로 AFX_IDW_PANE_FIRST로 설정 합니다.

*pContext*<br/>
에 대 한 포인터를 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)합니다. 기본적으로 NULL입니다.

### <a name="remarks"></a>설명

이 메서드는 포함 된 WebBrowser를 호출할 수도 `Navigate` 기본 문서를 로드 하는 방법 (참조 [CHtmlEditView::GetStartDocument](#getstartdocument)).

##  <a name="getdhtmldocument"></a>  CHtmlEditView::GetDHtmlDocument

반환 된 `IHTMLDocument2` 현재 문서에 대 한 인터페이스입니다.

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>매개 변수

*ppDocument*<br/>
합니다 [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) 인터페이스입니다.

##  <a name="getstartdocument"></a>  CHtmlEditView::GetStartDocument

이 보기에 대 한 기본 문서의 이름을 검색합니다.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>참고자료

[HTMLEdit 샘플](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
