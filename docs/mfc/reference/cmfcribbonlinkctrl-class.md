---
title: CMFCRibbonLinkCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CopyFrom
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetCompactSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetRegularSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetToolTipText
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::IsDrawTooltipImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDraw
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDrawMenuImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnMouseMove
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnSetIcon
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OpenLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::SetLink
helpviewer_keywords:
- CMFCRibbonLinkCtrl [MFC], CMFCRibbonLinkCtrl
- CMFCRibbonLinkCtrl [MFC], CopyFrom
- CMFCRibbonLinkCtrl [MFC], GetCompactSize
- CMFCRibbonLinkCtrl [MFC], GetLink
- CMFCRibbonLinkCtrl [MFC], GetRegularSize
- CMFCRibbonLinkCtrl [MFC], GetToolTipText
- CMFCRibbonLinkCtrl [MFC], IsDrawTooltipImage
- CMFCRibbonLinkCtrl [MFC], OnDraw
- CMFCRibbonLinkCtrl [MFC], OnDrawMenuImage
- CMFCRibbonLinkCtrl [MFC], OnMouseMove
- CMFCRibbonLinkCtrl [MFC], OnSetIcon
- CMFCRibbonLinkCtrl [MFC], OpenLink
- CMFCRibbonLinkCtrl [MFC], SetLink
ms.assetid: 77ae1941-e0ab-4a9d-911e-1752d34c079b
ms.openlocfilehash: bc13cf29fd9fed9f91221f00d4b605b3d9c3506f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772399"
---
# <a name="cmfcribbonlinkctrl-class"></a>CMFCRibbonLinkCtrl 클래스

리본에 배치되는 하이퍼링크를 구현합니다. 하이퍼링크를 클릭하면 웹 페이지가 열립니다.
더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

## <a name="syntax"></a>구문

```
class CMFCRibbonLinkCtrl : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl](#cmfcribbonlinkctrl)|`CMFCRibbonLinkCtrl` 개체를 생성하고 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCRibbonLinkCtrl::CopyFrom](#copyfrom)|( `CMFCRibbonButton::CopyFrom`을 재정의합니다.)|
|[CMFCRibbonLinkCtrl::GetCompactSize](#getcompactsize)|(재정의 [cmfcribbonbutton:: Getcompactsize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|
|[CMFCRibbonLinkCtrl::GetLink](#getlink)|하이퍼링크의 값을 반환합니다.|
|[CMFCRibbonLinkCtrl::GetRegularSize](#getregularsize)|(재정의 [cmfcribbonbutton:: Getregularsize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|
|[CMFCRibbonLinkCtrl::GetToolTipText](#gettooltiptext)|(재정의 [cmfcribbonbutton:: Gettooltiptext](../../mfc/reference/cmfcribbonbutton-class.md#gettooltiptext).)|
|[CMFCRibbonLinkCtrl::IsDrawTooltipImage](#isdrawtooltipimage)|( `CMFCRibbonButton::IsDrawTooltipImage`을 재정의합니다.)|
|[CMFCRibbonLinkCtrl::OnDraw](#ondraw)|(재정의 [cmfcribbonbutton:: Ondraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|
|[CMFCRibbonLinkCtrl::OnDrawMenuImage](#ondrawmenuimage)|(재정의 [cmfcribbonbaseelement:: Ondrawmenuimage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|
|[CMFCRibbonLinkCtrl::OnMouseMove](#onmousemove)|( `CMFCRibbonButton::OnMouseMove`을 재정의합니다.)|
|[CMFCRibbonLinkCtrl::OnSetIcon](#onseticon)||
|[CMFCRibbonLinkCtrl::OpenLink](#openlink)|하이퍼링크에 지정된 웹 페이지를 엽니다.|
|[CMFCRibbonLinkCtrl::SetLink](#setlink)|하이퍼링크의 값을 설정합니다.|

## <a name="remarks"></a>설명

하이퍼링크를 만든 후 추가 패널에 호출한 [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md) [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md) [CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonLinkCtrl.h

##  <a name="cmfcribbonlinkctrl"></a>  CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl

생성 하 고 초기화 된 [CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md) 개체입니다.

```
CMFCRibbonLinkCtrl(
    UINT nID,
    LPCTSTR lpszText,
    LPCTSTR lpszLink);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
[in] 링크 컨트롤을 클릭할 때 실행 되는 명령의 명령 ID를 지정 합니다.

*lpszText*<br/>
[in] 링크 컨트롤에 표시할 레이블을 지정 합니다.

*lpszLink*<br/>
[in] 링크 컨트롤을 사용 하 여 관련 된 하이퍼링크를 지정 합니다.

### <a name="example"></a>예제

다음 예제에서는의 생성자를 사용 하는 방법에 설명 합니다 `CMFCRibbonLinkCtrl` 클래스입니다. 이 코드 조각은의 일부인 합니다 [리본 가젯 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_RibbonGadgets#1](../../mfc/reference/codesnippet/cpp/cmfcribbonlinkctrl-class_1.cpp)]

##  <a name="copyfrom"></a>  CMFCRibbonLinkCtrl::CopyFrom

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>매개 변수

[in] *src*<br/>

### <a name="remarks"></a>설명

##  <a name="getcompactsize"></a>  CMFCRibbonLinkCtrl::GetCompactSize

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

[in] *pDC*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getlink"></a>  CMFCRibbonLinkCtrl::GetLink

하이퍼링크의 값을 반환합니다.

```
LPCTSTR GetLink() const;
```

### <a name="return-value"></a>반환 값

하이퍼링크의 현재 값입니다.

### <a name="remarks"></a>설명

##  <a name="getregularsize"></a>  CMFCRibbonLinkCtrl::GetRegularSize

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

[in] *pDC*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="gettooltiptext"></a>  CMFCRibbonLinkCtrl::GetToolTipText

```
virtual CString GetToolTipText() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="ondrawmenuimage"></a>  CMFCRibbonLinkCtrl::OnDrawMenuImage

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>매개 변수

[in] *CDC&#42;*<br/>
[in] *CRect*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="isdrawtooltipimage"></a>  CMFCRibbonLinkCtrl::IsDrawTooltipImage

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="ondraw"></a>  CMFCRibbonLinkCtrl::OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

[in] *pDC*<br/>

### <a name="remarks"></a>설명

##  <a name="onmousemove"></a>  CMFCRibbonLinkCtrl::OnMouseMove

```
virtual void OnMouseMove(CPoint point);
```

### <a name="parameters"></a>매개 변수

[in] *point*<br/>

### <a name="remarks"></a>설명

##  <a name="onseticon"></a>  CMFCRibbonLinkCtrl::OnSetIcon

```
virtual void OnSetIcon();
```

### <a name="remarks"></a>설명

##  <a name="openlink"></a>  CMFCRibbonLinkCtrl::OpenLink

하이퍼링크에 지정된 웹 페이지를 엽니다.

```
BOOL OpenLink();
```

### <a name="return-value"></a>반환 값

연결 된 웹 페이지를 성공적으로 열린 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

연결 된 하이퍼링크를 사용 하 여 웹 페이지를 엽니다는 `CMFCRibbonLinkCtrl` 개체입니다.

##  <a name="setlink"></a>  CMFCRibbonLinkCtrl::SetLink

하이퍼링크의 값을 설정합니다.

```
void SetLink(LPCTSTR lpszLink);
```

### <a name="parameters"></a>매개 변수

*lpszLink*<br/>
[in] 하이퍼링크 텍스트를 지정합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton 클래스](../../mfc/reference/cmfcribbonbutton-class.md)
