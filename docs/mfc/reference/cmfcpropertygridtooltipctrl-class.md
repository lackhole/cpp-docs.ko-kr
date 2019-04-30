---
title: CMFCPropertyGridToolTipCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Create
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Deactivate
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::GetLastRect
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Hide
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::SetTextMargin
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Track
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl [MFC], CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl [MFC], Create
- CMFCPropertyGridToolTipCtrl [MFC], Deactivate
- CMFCPropertyGridToolTipCtrl [MFC], GetLastRect
- CMFCPropertyGridToolTipCtrl [MFC], Hide
- CMFCPropertyGridToolTipCtrl [MFC], SetTextMargin
- CMFCPropertyGridToolTipCtrl [MFC], Track
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
ms.openlocfilehash: 6c14ed1f11a7a414332b34566a314459d76b911b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310476"
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl 클래스

설명을 구현 하는 컨트롤을 합니다 [CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md) 사용 하 여 도구 설명을 표시 합니다.

## <a name="syntax"></a>구문

```
class CMFCPropertyGridToolTipCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|이름|설명|
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|`CMFCPropertyGridToolTipCtrl` 개체를 생성합니다.|
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|[CMFCPropertyGridToolTipCtrl::Create](#create)|도구 설명 컨트롤에 대 한 창을 만듭니다.|
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|비활성화 하 고 도구 설명 컨트롤을 숨깁니다.|
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|도구 설명 컨트롤의 마지막 위치 좌표를 반환합니다.|
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|도구 설명 컨트롤을 숨깁니다.|
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|창 메시지가 [TranslateMessage](../../mfc/reference/cwinapp-class.md) 및 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) Windows 함수로 디스패치되기 전에 [CWinApp](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) 클래스가 이 메시지를 해석하는 데 사용됩니다. ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 재정의합니다.)|
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|도구 설명 텍스트를 도구 설명 창의 테두리 사이의 간격을 설정합니다.|
|[CMFCPropertyGridToolTipCtrl::Track](#track)|도구 설명 컨트롤을 표시합니다.|

## <a name="remarks"></a>설명

속성 이름에는 포인터를 놓으면 도구 설명이 표시 됩니다. 합니다 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) 클래스는 사용자가 쉽게 읽을 수 있는 것을 도구 설명이 표시 됩니다. 일반적으로 도구 설명의 위치는 포인터의 위치에 따라 결정 됩니다. 이 클래스를 사용 하 여 도구 설명 속성 이름을 표시 되며 속성 이름을 완전히 표시 되도록 자연 스러운 속성 확장 비슷합니다.

MFC 자동으로이 컨트롤을 만들고에서 사용 하 여 [CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md)합니다.

## <a name="example"></a>예제

다음 예제에서는의 개체를 생성 하는 방법에 설명 합니다 `CMFCPropertyGridToolTipCtrl` 클래스 및 도구 설명 컨트롤을 표시 하는 방법입니다.

[!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpropertygridtooltipctrl.h

##  <a name="cmfcpropertygridtooltipctrl"></a>  CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl

`CMFCPropertyGridToolTipCtrl` 개체를 생성합니다.

```
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```

##  <a name="create"></a>  CMFCPropertyGridToolTipCtrl::Create

도구 설명 컨트롤에 대 한 창을 만듭니다.

```
BOOL Create(CWnd* pWndParent);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
[in] 부모 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

창 성공적으로 만들어진 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="deactivate"></a>  CMFCPropertyGridToolTipCtrl::Deactivate

비활성화 하 고 도구 설명 컨트롤을 숨깁니다.

```
void Deactivate();
```

### <a name="remarks"></a>설명

이 메서드를 설정 마지막 위치 및 텍스트를 빈 값을 나중에 호출 되도록 [CMFCPropertyGridToolTipCtrl::Track](#track) 도구 설명을 표시 합니다.

##  <a name="getlastrect"></a>  CMFCPropertyGridToolTipCtrl::GetLastRect

도구 설명 컨트롤의 마지막 위치 좌표를 반환합니다.

```
void GetLastRect(CRect& rect) const;
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[out] 도구 설명 컨트롤의 마지막 위치를 포함합니다.

##  <a name="hide"></a>  CMFCPropertyGridToolTipCtrl::Hide

도구 설명 컨트롤을 숨깁니다.

```
void Hide();
```

##  <a name="settextmargin"></a>  CMFCPropertyGridToolTipCtrl::SetTextMargin

도구 설명 텍스트를 도구 설명 창의 테두리 사이의 간격을 설정합니다.

```
void SetTextMargin(int nTextMargin);
```

### <a name="parameters"></a>매개 변수

*nTextMargin*<br/>
[in] 도구 설명 컨트롤 텍스트를 도구 설명 창의 테두리 사이의 간격을 지정합니다. 기본값은 10 픽셀입니다.

##  <a name="track"></a>  CMFCPropertyGridToolTipCtrl::Track

도구 설명 컨트롤을 표시합니다.

```
void Track(
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[in] 도구 설명 컨트롤의 크기와 위치를 지정합니다.

*strText*<br/>
[in] 도구 설명에 표시할 텍스트를 지정 합니다.

### <a name="remarks"></a>설명

이 메서드는 지정 된 크기와 위치에 도구 설명 컨트롤을 표시 *rect*합니다. 마지막으로이 메서드를 호출한 후 위치, 크기 및 텍스트 변경 되지 않은 경우이 메서드는 영향을 주지 않습니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
