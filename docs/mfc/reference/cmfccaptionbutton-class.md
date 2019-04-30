---
title: CMFCCaptionButton 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
ms.openlocfilehash: 2020f6cb2f0feec28996f69791899c648600b600
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403817"
---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton 클래스

`CMFCCaptionButton` 도킹 창 또는 미니 프레임 창의 캡션 표시줄에 표시 되는 단추를 구현 하는 클래스입니다. 일반적으로 프레임워크는 캡션 단추를 자동으로 만듭니다.

## <a name="syntax"></a>구문

```
class CMFCCaptionButton : public CObject
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|이름|설명|
|----------|-----------------|
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|CMFCCaptionButton 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCCaptionButton::GetHit](#gethit)|명령 단추를 나타내는 반환 합니다.|
|[CMFCCaptionButton::GetIconID](#geticonid)|단추와 연결 된 이미지 ID를 반환 합니다.|
|[CMFCCaptionButton::GetRect](#getrect)|단추에서 차지 하는 사각형을 반환 합니다.|
|[CMFCCaptionButton::GetSize](#getsize)|단추의 높이 너비를 반환합니다.|
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|제목 막대 높이 미니 크기로 설정 되었는지 여부를 나타냅니다.|
|[CMFCCaptionButton::Move](#move)|창의 표시 상태와 단추 그리기 위치를 설정합니다.|
|[CMFCCaptionButton::OnDraw](#ondraw)|캡션 단추를 그립니다.|
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|제목 표시줄의 최소 크기를 설정합니다.|

## <a name="remarks"></a>설명

클래스를 파생 시킬 수 있습니다 [CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md) 보호 된 메서드를 사용 하 여 `AddButton`미니 프레임 창에 캡션 단추를 추가 합니다.

CPaneFrameWnd.h 두 가지 유형의 캡션 단추에 대 한 명령 Id를 정의합니다.

- AFX_CAPTION_BTN_PIN 도킹 창 자동 숨기기 모드를 지 원하는 경우 핀 단추를 표시 합니다.

- AFX_CAPTION_BTN_CLOSE 표시를 **닫기** 단추 창 종료 하거나 숨길 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 생성 하는 방법에 설명 된 `CMFCCaptionButton` 개체 및 제목 표시줄의 최소 크기를 설정 합니다.

[!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxcaptionbutton.h

##  <a name="cmfccaptionbutton"></a>  CMFCCaptionButton::CMFCCaptionButton

`CMFCCaptionButton` 개체를 생성합니다.

```
CMFCCaptionButton();

CMFCCaptionButton(
    UINT nHit,
    BOOL bLeftAlign = FALSE);
```

### <a name="parameters"></a>매개 변수

*nHit*<br/>
[in] 단추와 연결 된 명령입니다.

*bLeftAlign*<br/>
[in] 단추를 왼쪽에 정렬 되는지 여부를 지정 합니다.

다음 표에 대 한 가능한 값은 *nHit* 매개 변수입니다.

|값|명령|
|-----------|-------------|
|AFX_HTCLOSE|닫기 단추입니다.|
|HTMINBUTTON|단추를 최소화 합니다.|
|HTMAXBUTTON|최대화 단추입니다.|
|AFX_HTLEFTBUTTON|왼쪽된 화살표 단추입니다.|
|AFX_HTRIGHTBUTTON|오른쪽 화살표 단추입니다.|
|AFX_HTMENU|아래쪽 화살표 메뉴 단추입니다.|
|HTNOWHERE|기본값입니다. 없는 명령을 나타냅니다.|

### <a name="remarks"></a>설명

기본적으로 캡션 단추 명령과 사용 하 여 연결 되지 않습니다.

캡션 단추 중 하나를 오른쪽 이나 왼쪽에 맞춰집니다.

##  <a name="gethit"></a>  CMFCCaptionButton::GetHit

명령 단추를 나타내는 반환 합니다.

```
UINT GetHit() const;
```

### <a name="return-value"></a>반환 값

단추를 나타내는 명령입니다.

다음 표에서 가능한 반환 값을 나열합니다.

|값|명령|
|-----------|-------------|
|AFX_HTCLOSE|닫기 단추입니다.|
|HTMINBUTTON|단추를 최소화 합니다.|
|HTMAXBUTTON|최대화 단추입니다.|
|AFX_HTLEFTBUTTON|왼쪽된 화살표 단추입니다.|
|AFX_HTRIGHTBUTTON|오른쪽 화살표 단추입니다.|
|AFX_HTMENU|아래쪽 화살표 메뉴 단추입니다.|
|HTNOWHERE|기본값입니다. 없는 명령을 나타냅니다.|

##  <a name="geticonid"></a>  CMFCCaptionButton::GetIconID

단추와 연결 된 이미지 ID를 반환 합니다.

```
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,
    BOOL bMaximized = FALSE) const;
```

### <a name="parameters"></a>매개 변수

*bHorz*<br/>
[in] 왼쪽 또는 오른쪽 화살표 이미지 Id;에 대해 TRUE FALSE에 대 한 위로 또는 아래로 화살표 이미지 Id입니다.

*bMaximized*<br/>
[in] 최대화 이미지 ID;에 대해 TRUE FALSE 최소화 이미지 id

### <a name="return-value"></a>반환 값

이미지 id입니다.

### <a name="remarks"></a>설명

매개 변수를 최소화에 대 한 이미지 Id를 지정 하거나 캡션 단추를 최대화 합니다.

##  <a name="getrect"></a>  CMFCCaptionButton::GetRect

단추에서 차지 하는 사각형을 반환 합니다.

```
virtual CRect GetRect() const;
```

### <a name="return-value"></a>반환 값

단추 위치를 나타내는 사각형입니다.

### <a name="remarks"></a>설명

단추를 볼 수 없는 경우 반환 된 크기는 0입니다.

##  <a name="getsize"></a>  CMFCCaptionButton::GetSize

단추의 높이 너비를 반환합니다.

```
static CSize GetSize();
```

### <a name="return-value"></a>반환 값

외부 크기 단추입니다.

### <a name="remarks"></a>설명

반환 되는 크기 단추 여백 및 테두리를 포함 합니다.

##  <a name="isminiframebutton"></a>  CMFCCaptionButton::IsMiniFrameButton

제목 막대 높이 미니 크기로 설정 되었는지 여부를 나타냅니다.

```
BOOL IsMiniFrameButton() const;
```

### <a name="return-value"></a>반환 값

캡션을 미니 크기;로 설정 된 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="move"></a>  CMFCCaptionButton::Move

창의 표시 상태와 단추 그리기 위치를 설정합니다.

```
void Move(
    const CPoint& ptTo,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>매개 변수

*ptTo*<br/>
[in] 새 위치입니다.

*bHide*<br/>
[in] [] 단추의 표시 여부를 나타냅니다.

##  <a name="ondraw"></a>  CMFCCaptionButton::OnDraw

캡션 단추를 그립니다.

```
virtual void OnDraw(
    CDC* pDC,
    BOOL bActive,
    BOOL bHorz = TRUE,
    BOOL bMaximized = TRUE,
    BOOL bDisabled = FALSE);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 단추에 대해 장치 컨텍스트에 대 한 포인터입니다.

*bActive*<br/>
[in] 활성 단추 이미지를 그릴 것인지 지정 합니다.

*bHorz*<br/>
[in] 파생된 클래스에서 사용 하기 위해 예약 되어 있습니다.

*bMaximized*<br/>
[in] 최대화 단추 이미지를 그릴 것인지 지정 합니다.

*bDisabled*<br/>
[in] 사용된 단추 이미지를 그릴 것인지 지정 합니다.

### <a name="remarks"></a>설명

합니다 *bMaximized* 매개 변수 단추를 최대화 없을 때 사용 됩니다 또는 최소화 단추입니다.

##  <a name="setminiframebutton"></a>  CMFCCaptionButton::SetMiniFrameButton

제목 표시줄의 최소 크기를 설정합니다.

```
void SetMiniFramebutton(BOOL bSet = TRUE);
```

### <a name="parameters"></a>매개 변수

*bSet*<br/>
[in] 미니 제목 막대 높이;에 대해 TRUE 기본 제목 막대 높이 대 한 FALSE입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)
