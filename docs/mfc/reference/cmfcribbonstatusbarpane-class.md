---
title: CMFCRibbonStatusBarPane 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
helpviewer_keywords:
- CMFCRibbonStatusBarPane [MFC], CMFCRibbonStatusBarPane
- CMFCRibbonStatusBarPane [MFC], GetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], GetTextAlign
- CMFCRibbonStatusBarPane [MFC], IsAnimation
- CMFCRibbonStatusBarPane [MFC], IsExtended
- CMFCRibbonStatusBarPane [MFC], OnDrawBorder
- CMFCRibbonStatusBarPane [MFC], OnFillBackground
- CMFCRibbonStatusBarPane [MFC], SetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], SetAnimationList
- CMFCRibbonStatusBarPane [MFC], SetTextAlign
- CMFCRibbonStatusBarPane [MFC], StartAnimation
- CMFCRibbonStatusBarPane [MFC], StopAnimation
- CMFCRibbonStatusBarPane [MFC], OnFinishAnimation
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
ms.openlocfilehash: 9911672ec139ab1598db8005e9b7b909e85dd33d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410078"
---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane 클래스

`CMFCRibbonStatusBarPane` 리본 상태 표시줄에 추가할 수 있는 리본 요소를 구현 하는 클래스입니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonStatusBarPane : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|`CMFCRibbonStatusBarPane` 개체를 생성하고 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|잘림 없이 창에 표시 될 수 있는 가장 긴 텍스트 문자열을 정의 하는 문자열을 반환 합니다.|
|[CMFCRibbonStatusBarPane::GetTextAlign](#gettextalign)|텍스트 맞춤의 현재 설정을 반환합니다.|
|[CMFCRibbonStatusBarPane::IsAnimation](#isanimation)|애니메이션 진행에서 중인지 여부를 결정 합니다.|
|[CMFCRibbonStatusBarPane::IsExtended](#isextended)|창의 리본 메뉴 상태 표시줄의 확장된 된 영역에 있는지 여부를 결정 합니다.|
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(재정의 [CMFCRibbonButton::OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(재정의 [CMFCRibbonButton::OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|잘림 없이 창에 표시 될 수 있는 가장 긴 텍스트 문자열을 정의 합니다.|
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|애니메이션에 사용할 수 있는 이미지 목록 창에 할당 합니다.|
|[CMFCRibbonStatusBarPane::SetTextAlign](#settextalign)|텍스트 맞춤을 설정합니다.|
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|창에 할당 되는 애니메이션을 시작 합니다.|
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|창에 할당 되는 애니메이션을 중지 합니다. .|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|창에 할당 되는 애니메이션을 중지 하는 경우 프레임 워크에서 호출 됩니다.|

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonStatusBarPane` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 생성 하는 방법을 보여는 `CMFCRibbonStatusBarPane` 개체, 상태 표시줄 창의 레이블 텍스트 맞춤을 설정, 잘림 없이 상태 표시줄 창에 표시할 수 있습니다, 상태 표시줄 창에 사용할 수 있는 이미지 목록을 연결 하는 가장 긴 텍스트를 정의 nimation, 및 애니메이션을 시작 합니다.

[!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribbonstatusbarpane.h

##  <a name="cmfcribbonstatusbarpane"></a>  CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane

상태 표시줄에 창 개체를 생성 합니다.

```
CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    BOOL bIsStatic=FALSE,
    HICON hIcon=NULL,
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);
```

### <a name="parameters"></a>매개 변수

*nCmdID*<br/>
[in] 창의 명령 ID를 지정합니다.

*lpszText*<br/>
[in] 창에 표시할 텍스트 문자열을 지정 합니다.

*bIsStatic*<br/>
[in] True 이면 상태 창에 강조 표시 하거나 클릭 하 여 선택한 수 없습니다.

*hIcon*<br/>
[in] 창에 표시할 아이콘에 대 한 핸들을 지정 합니다.

*lpszAlmostLargeText*<br/>
[in] 창에 표시 될 수 있는 가장 긴 텍스트 문자열을 지정 합니다.

*hBmpAnimationList*<br/>
[in] 애니메이션에 사용 되는 이미지 목록에 대 한 핸들을 지정 합니다.

*cxAnimation*<br/>
[in] 애니메이션에 사용 되는 이미지 목록에서 아이콘의 픽셀에서 너비를 지정 합니다.

*clrTrnsp*<br/>
[in] 애니메이션에 사용 되는 이미지 목록의 이미지의 투명색을 지정 합니다.

*uiAnimationListResID*<br/>
[in] 애니메이션에 사용 되는 이미지 목록 리소스 ID를 지정 합니다.

##  <a name="getalmostlargetext"></a>  CMFCRibbonStatusBarPane::GetAlmostLargeText

상태 표시줄 창을 표시할 수 있는 가장 긴 텍스트 문자열을 가져옵니다.

```
LPCTSTR GetAlmostLargeText() const;
```

### <a name="return-value"></a>반환 값

상태 표시줄 창을 표시할 수 있는 가장 긴 텍스트 문자열입니다.

##  <a name="gettextalign"></a>  CMFCRibbonStatusBarPane::GetTextAlign

상태 표시줄 창의 레이블 텍스트 맞춤의 현재 설정을 가져옵니다.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>반환 값

현재 텍스트 맞춤을 다음 중 하나일 수 있습니다.

- TA_LEFT

- TA_CENTER

- TA_RIGHT 합니다.

##  <a name="isanimation"></a>  CMFCRibbonStatusBarPane::IsAnimation

애니메이션 진행에서 중인지 여부를 결정 합니다.

```
BOOL IsAnimation() const;
```

### <a name="return-value"></a>반환 값

애니메이션이 진행에서 하는 경우 TRUE입니다. FALSE이 고, 그렇지 합니다.

##  <a name="isextended"></a>  CMFCRibbonStatusBarPane::IsExtended

창의 리본 메뉴 상태 표시줄의 확장된 된 영역에 있는지 여부를 결정 합니다.

```
BOOL IsExtended() const;
```

### <a name="return-value"></a>반환 값

창 상태 표시줄 확장 된 영역에 있으면 TRUE입니다. FALSE이 고, 그렇지 합니다.

##  <a name="ondrawborder"></a>  CMFCRibbonStatusBarPane::OnDrawBorder

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

```
virtual void OnDrawBorder(CDC*);
```

### <a name="parameters"></a>매개 변수

[in] *CDC&#42;*<br/>

### <a name="remarks"></a>설명

##  <a name="onfillbackground"></a>  CMFCRibbonStatusBarPane::OnFillBackground

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

```
virtual COLORREF OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

[in] *pDC*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="onfinishanimation"></a>  CMFCRibbonStatusBarPane::OnFinishAnimation

프레임 워크는 창에 할당 되는 애니메이션이 종료 될 때이 메서드를 호출 합니다.

```
virtual void OnFinishAnimation();
```

### <a name="remarks"></a>설명

`StopAnimation` 메서드 호출을 `OnFinishAnimation` 메서드를 사용 하면 애니메이션이 종료 될 때 데이터를 정리할 수 있습니다.

##  <a name="setalmostlargetext"></a>  CMFCRibbonStatusBarPane::SetAlmostLargeText

잘림 없이 상태 표시줄 창에 표시 될 수 있는 가장 긴 텍스트를 정의 합니다.

```
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```

### <a name="parameters"></a>매개 변수

*lpszAlmostLargeText*<br/>
[in] 잘림 없이 상태 표시줄 창에 표시 될 수 있는 가장 긴 문자열을 지정 합니다.

### <a name="remarks"></a>설명

텍스트의 크기를 계산 하는 라이브러리는 *lpszAlmostLargeText* 지정 하 고 그에 따라 창 크기를 조정 합니다. 이 여전히 맞지 않는 경우 창에서 텍스트가 잘립니다.

##  <a name="setanimationlist"></a>  CMFCRibbonStatusBarPane::SetAnimationList

상태 표시줄 창을 애니메이션에 사용할 수 있는 이미지 목록을 연결 합니다.

```
void SetAnimationList(
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```

### <a name="parameters"></a>매개 변수

*hBmpAnimationList*<br/>
[in] 이미지 목록에 대 한 핸들을 지정합니다.

*cxAnimation*<br/>
[in] 이미지 목록에서 프레임의 픽셀에서 너비를 지정 합니다.

*clrTransp*<br/>
[in] 이미지 목록의 투명 한 색을 지정합니다.

*uiAnimationListResID*<br/>
[in] 이미지 목록의 리소스 ID를 지정합니다.

### <a name="return-value"></a>반환 값

이미지 목록 상태 표시줄 창을;에 성공적으로 연결 되어 있으면 TRUE입니다. FALSE이 고, 그렇지 합니다.

##  <a name="settextalign"></a>  CMFCRibbonStatusBarPane::SetTextAlign

상태 표시줄 창의 레이블 텍스트 맞춤을 설정합니다.

```
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>매개 변수

*nAlign*<br/>
[in] 텍스트 맞춤을 지정합니다.

### <a name="remarks"></a>설명

*nAlign* 다음 값 중 하나일 수 있습니다.

- TA_LEFT: 왼쪽된 맞춤

- TA_CENTER: 가운데 맞춤

- TA_RIGHT: 오른쪽 맞춤

##  <a name="startanimation"></a>  CMFCRibbonStatusBarPane::StartAnimation

창에 할당 하는 애니메이션을 시작 합니다.

```
void StartAnimation(
    UINT nFrameDelay=500,
    UINT nDuration=-1);
```

### <a name="parameters"></a>매개 변수

*nFrameDelay*<br/>
[in] 애니메이션 프레임 속도 밀리초 단위로 지정합니다.

*nDuration*<br/>
[in] 시간 (밀리초)에 애니메이션을 재생 하는 데 시간을 지정 합니다. 무한 루프에 대 한-1 사용 합니다.

### <a name="remarks"></a>설명

호출 하기 전에 이미지 목록에 대 한 핸들을 지정 해야 합니다 `StartAnimation` 를 사용 하 여 `SetAnimationList`입니다.

##  <a name="stopanimation"></a>  CMFCRibbonStatusBarPane::StopAnimation

상태 표시줄 창에 할당 하는 애니메이션을 중지 합니다.

```
void StopAnimation();
```

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton 클래스](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonStatusBar 클래스](../../mfc/reference/cmfcribbonstatusbar-class.md)
