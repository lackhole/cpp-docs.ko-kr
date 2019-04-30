---
title: CRectTracker 클래스
ms.date: 11/19/2018
f1_keywords:
- CRectTracker
- AFXEXT/CRectTracker
- AFXEXT/CRectTracker::CRectTracker
- AFXEXT/CRectTracker::AdjustRect
- AFXEXT/CRectTracker::Draw
- AFXEXT/CRectTracker::DrawTrackerRect
- AFXEXT/CRectTracker::GetHandleMask
- AFXEXT/CRectTracker::GetTrueRect
- AFXEXT/CRectTracker::HitTest
- AFXEXT/CRectTracker::NormalizeHit
- AFXEXT/CRectTracker::OnChangedRect
- AFXEXT/CRectTracker::SetCursor
- AFXEXT/CRectTracker::Track
- AFXEXT/CRectTracker::TrackRubberBand
- AFXEXT/CRectTracker::m_nHandleSize
- AFXEXT/CRectTracker::m_nStyle
- AFXEXT/CRectTracker::m_rect
- AFXEXT/CRectTracker::m_sizeMin
helpviewer_keywords:
- CRectTracker [MFC], CRectTracker
- CRectTracker [MFC], AdjustRect
- CRectTracker [MFC], Draw
- CRectTracker [MFC], DrawTrackerRect
- CRectTracker [MFC], GetHandleMask
- CRectTracker [MFC], GetTrueRect
- CRectTracker [MFC], HitTest
- CRectTracker [MFC], NormalizeHit
- CRectTracker [MFC], OnChangedRect
- CRectTracker [MFC], SetCursor
- CRectTracker [MFC], Track
- CRectTracker [MFC], TrackRubberBand
- CRectTracker [MFC], m_nHandleSize
- CRectTracker [MFC], m_nStyle
- CRectTracker [MFC], m_rect
- CRectTracker [MFC], m_sizeMin
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
ms.openlocfilehash: 9c54cdfecfa6c4ff0eef7e16003ab2097553953d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372275"
---
# <a name="crecttracker-class"></a>CRectTracker 클래스

항목을을 표시, 이동 하 고 다른 방식에서 크기를 조정할 수 있습니다.

## <a name="syntax"></a>구문

```
class CRectTracker
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CRectTracker::CRectTracker](#crecttracker)|`CRectTracker` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CRectTracker::AdjustRect](#adjustrect)|사각형의 크기를 조정할 때 호출 됩니다.|
|[CRectTracker::Draw](#draw)|사각형을 렌더링합니다.|
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|테두리를 그릴 때 호출을 `CRectTracker` 개체입니다.|
|[CRectTracker::GetHandleMask](#gethandlemask)|마스크를 가져오기 위해 호출 된 `CRectTracker` 항목의 크기 조정 핸들입니다.|
|[CRectTracker::GetTrueRect](#gettruerect)|크기 조정 핸들을 포함 하 여 사각형의 너비와 높이 반환 합니다.|
|[CRectTracker::HitTest](#hittest)|와 관련 된 커서의 현재 위치를 반환 합니다 `CRectTracker` 개체입니다.|
|[CRectTracker::NormalizeHit](#normalizehit)|적중 테스트 코드를 정규화합니다.|
|[CRectTracker::OnChangedRect](#onchangedrect)|사각형 크기를 조정 되거나 이동 된 경우 호출 됩니다.|
|[CRectTracker::SetCursor](#setcursor)|사각형을 통해 해당 위치에 따라 커서를 설정합니다.|
|[CRectTracker::Track](#track)|사각형을 조작할 수 있습니다.|
|[CRectTracker::TrackRubberBand](#trackrubberband)|사용자 "고무 밴드"를 선택할 수 있습니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|크기 조정 핸들의 크기를 결정합니다.|
|[CRectTracker::m_nStyle](#m_nstyle)|추적기의 현재 style(s) 합니다.|
|[CRectTracker::m_rect](#m_rect)|현재 위치 (픽셀) 사각형의입니다.|
|[CRectTracker::m_sizeMin](#m_sizemin)|최소 너비와 높이 결정합니다.|

## <a name="remarks"></a>설명

`CRectTracker` 기본 클래스는 없습니다.

하지만 `CRectTracker` 클래스는 그래픽 인터페이스를 사용 하 여 OLE 항목을 사용 하 여 상호 작용할 수 있도록 설계 되었습니다, 용도 OLE 지원 응용 프로그램에 제한 되지 않습니다. 사용할 수 있습니다 이러한 사용자 인터페이스가 필요한 모든 곳에서 합니다.

`CRectTracker` 테두리 solid 수 또는 점선입니다. 항목을 빗금된 테두리가 지정 된 항목의 다른 상태를 나타낼 수 빗살 무늬로로 중첩 또는 볼 수 있습니다. 외부 또는 내부에서 8 개의 크기 조정 핸들을 배치할 수 있습니다 항목의 테두리입니다. (참조에 대 한 설명은 크기 조정 핸들 [GetHandleMask](#gethandlemask).) 마지막으로 `CRectTracker` 항목의 크기를 조정 하는 동안 방향을 변경할 수 있습니다.

사용 하도록 `CRectTracker`, 생성을 `CRectTracker` 개체 및 초기화 되는 표시 상태를 지정 합니다. 그런 다음 사용자에 게 시각적 피드백에 연결 된 OLE 항목의 현재 상태에 있도록이 인터페이스를 사용할 수 있습니다는 `CRectTracker` 개체입니다.

사용 하 여 대 한 자세한 내용은 `CRectTracker`, 문서를 참조 하세요 [추적기](../../mfc/trackers.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CRectTracker`

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

##  <a name="adjustrect"></a>  CRectTracker::AdjustRect

추적 사각형 크기 조정 핸들을 사용 하 여 크기를 조정할 때 프레임 워크에서 호출 됩니다.

```
virtual void AdjustRect(
    int nHandle,
    LPRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*nHandle*<br/>
사용 되는 핸들의 인덱스입니다.

*lpRect*<br/>
사각형의 현재 크기에 대 한 포인터입니다. (사각형의 크기는 높이 너비도 지정 됩니다.)

### <a name="remarks"></a>설명

이 함수의 기본 동작은 허용 경우에만 변경 하려면 사각형의 방향을 `Track` 및 `TrackRubberBand` 허용 반전 사용 하 여 호출 됩니다.

끌기 작업 중 추적 사각형 조정 제어 하려면이 함수를 재정의 합니다. 으로 지정 된 좌표를 조정 하는 한 가지 방법은 것 *lpRect* 반환 하기 전에 합니다.

직접 지원 되지 않는 특수 기능 `CRectTracker`와 같은 눈금에 또는 유지-가로 세로 비율을이 함수를 재정의 하 여 구현할 수 있습니다.

##  <a name="crecttracker"></a>  CRectTracker::CRectTracker

만들고 초기화는 `CRectTracker` 개체입니다.

```
CRectTracker();

CRectTracker(
    LPCRECT lpSrcRect,
    UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*lpSrcRect*<br/>
사각형 개체의 좌표를 지정 합니다.

*nStyle*<br/>
스타일을 지정 합니다 `CRectTracker` 개체입니다. 지원되는 스타일은 다음과 같습니다.

- `CRectTracker::solidLine` 사각형 테두리에 실선이 표시를 사용 합니다.

- `CRectTracker::dottedLine` 점선 사각형 테두리에 대 한 사용 합니다.

- `CRectTracker::hatchedBorder` 사각형 테두리에 대 한 교차 무늬 패턴을 사용 합니다.

- `CRectTracker::resizeInside` 사각형 내에 있는 핸들의 크기를 조정 합니다.

- `CRectTracker::resizeOutside` 사각형 외부에 있는 핸들의 크기를 조정 합니다.

- `CRectTracker::hatchInside` 패턴에서는 전체 사각형을 무늬입니다.

### <a name="remarks"></a>설명

기본 생성자는 초기화를 `CRectTracker` 개체의 값으로 *lpSrcRect* 다른 크기 시스템 기본값으로 초기화 합니다. 매개 변수 없이 개체를 만들 경우 합니다 `m_rect` 및 `m_nStyle` 데이터 멤버가 초기화 되지 않았습니다.

##  <a name="draw"></a>  CRectTracker::Draw

사각형의 외부 선과 내부 영역을 그리는이 함수를 호출 합니다.

```
void Draw(CDC* pDC) const;
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
그릴 장치 컨텍스트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

추적기의 스타일 그리기 수행 되는 방법 결정 합니다. 에 대 한 생성자를 참조 하세요. `CRectTracker` 사용할 수 있는 스타일에 대 한 자세한 내용은 합니다.

##  <a name="drawtrackerrect"></a>  CRectTracker::DrawTrackerRect

추적기의 위치가 변경 될 때마다 프레임 워크에서 호출 내에서 하는 동안 합니다 `Track` 또는 `TrackRubberBand` 멤버 함수입니다.

```
virtual void DrawTrackerRect(
    LPCRECT lpRect,
    CWnd* pWndClipTo,
    CDC* pDC,
    CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*lpRect*<br/>
에 대 한 포인터를 `RECT` 그릴 사각형을 포함 하는 합니다.

*pWndClipTo*<br/>
클리핑 사각형에서 사용 하는 창에 대 한 포인터입니다.

*pDC*<br/>
그릴 장치 컨텍스트에 대 한 포인터입니다.

*pWnd*<br/>
그리기는 발생 하는 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

기본 구현에 대 한 호출에서는 `CDC::DrawFocusRect`는 점으로 구분 된 사각형을 그립니다.

작업을 추적 하는 동안 다양 한 피드백을 제공 하려면이 함수를 재정의 합니다.

##  <a name="gethandlemask"></a>  CRectTracker::GetHandleMask

프레임 워크는 사각형의 크기 조정 핸들에 대 한 마스크를 검색 하려면이 멤버 함수를 호출 합니다.

```
virtual UINT GetHandleMask() const;
```

### <a name="return-value"></a>반환 값

마스크를 `CRectTracker` 항목의 크기 조정 핸들입니다.

### <a name="remarks"></a>설명

크기 조정 핸들 양쪽에 사각형의 모퉁이 나타나고 사용자가 모양과 사각형의 크기를 제어 하도록 허용 합니다.

사각형의 8 크기 조정 핸들 번호 0-7입니다. 각 크기 조정 핸들이 나타내는 비트 마스크; 해당 비트의 값은 2 ^ *n*, 여기서 *n* 크기 조정 핸들입니다. 시계 방향으로 이동 왼쪽 위에서 시작 하 여 모퉁이 크기 조정 핸들을 해당 비트 0-3입니다. 시계 방향으로 위쪽에서 시작 하는 핸들의 크기를 조정 하는 비트 4-7 쪽에 해당 합니다. 다음 그림에서는 사각형의 크기 조정 핸들 및 핸들 번호 및 값의 크기를 조정 해당 보여 줍니다.

![크기 조정 핸들 번호](../../mfc/reference/media/vc35dp1.gif "크기 조정 핸들 번호")

기본 구현을 `GetHandleMask` 크기 조정 핸들이 표시 되도록 비트 마스크를 반환 합니다. 단일 비트에 있으면 해당 크기 조정 핸들을 그립니다.

숨기 거 나 표시 된 크기 조정 핸들을 표시 하려면이 멤버 함수를 재정의 합니다.

##  <a name="gettruerect"></a>  CRectTracker::GetTrueRect

사각형의 좌표를 검색 하려면이 함수를 호출 합니다.

```
void GetTrueRect(LPRECT lpTrueRect) const;
```

### <a name="parameters"></a>매개 변수

*lpTrueRect*<br/>
에 대 한 포인터를 `RECT` 장치를 포함 하는 구조체의 좌표를 `CRectTracker` 개체입니다.

### <a name="remarks"></a>설명

사각형의 크기에는 외부 테두리에 있는 모든 크기 조정 핸들의 너비와 높이가 포함 됩니다. 돌아가면 *lpTrueRect* 항상 장치 좌표에서 정규화 된 사각형입니다.

##  <a name="hittest"></a>  CRectTracker::HitTest

사용자에 대 한 크기 조정 핸들을 주워 여부를 확인 하려면이 함수를 호출 합니다.

```
int HitTest(CPoint point) const;
```

### <a name="parameters"></a>매개 변수

*point*<br/>
테스트 장치 좌표 지점입니다.

### <a name="return-value"></a>반환 값

반환 되는 값은 열거 유형을 기반 `CRectTracker::TrackerHit` 다음 값 중 하나일 수 있습니다.

- `CRectTracker::hitNothing` -1

- `CRectTracker::hitTopLeft` 0

- `CRectTracker::hitTopRight` 1

- `CRectTracker::hitBottomRight` 2

- `CRectTracker::hitBottomLeft` 3

- `CRectTracker::hitTop` 4

- `CRectTracker::hitRight` 5

- `CRectTracker::hitBottom` 6

- `CRectTracker::hitLeft` 7

- `CRectTracker::hitMiddle` 8

##  <a name="m_nhandlesize"></a>  CRectTracker::m_nHandleSize

픽셀에서 크기의는 `CRectTracker` 핸들의 크기를 조정 합니다.

```
int m_nHandleSize;
```

### <a name="remarks"></a>설명

시스템 기본값을 사용 하 여 초기화 합니다.

##  <a name="m_rect"></a>  CRectTracker::m_rect

사각형의 현재 위치를 클라이언트 좌표 (픽셀)입니다.

```
CRect m_rect;
```

##  <a name="m_sizemin"></a>  CRectTracker::m_sizeMin

사각형의 최소 크기입니다.

```
CSize m_sizeMin;
```

### <a name="remarks"></a>설명

모두 기본값 `cx` 고 `cy`, 테두리 너비에 대 한 기본 시스템 값에서 계산 됩니다. 이 데이터 멤버 에서만 사용 되는 `AdjustRect` 멤버 함수입니다.

##  <a name="m_nstyle"></a>  CRectTracker::m_nStyle

사각형의 현재 스타일입니다.

```
UINT m_nStyle;
```

### <a name="remarks"></a>설명

참조 [CRectTracker::CRectTracker](#crecttracker) 가능한 스타일의 목록은 합니다.

##  <a name="normalizehit"></a>  CRectTracker::NormalizeHit

잠재적으로 반전 된 핸들을 변환 하려면이 함수를 호출 합니다.

```
int NormalizeHit(int nHandle) const;
```

### <a name="parameters"></a>매개 변수

*nHandle*<br/>
사용자가 선택한 핸들입니다.

### <a name="return-value"></a>반환 값

정규화 된 핸들의 인덱스입니다.

### <a name="remarks"></a>설명

때 `CRectTracker::Track` 또는 `CRectTracker::TrackRubberBand` 라고 허용 반전를 사용 하 여 x 축, y 축에서 반전 사각형에 대 한 가능한 것입니다. 이 경우 `HitTest` 사각형을 기준으로 반전 수도 있는 핸들을 반환 합니다. 이 피드백은 사각형 데이터 구조를 수정 하는 부분 사각형의 화면 위치에 따라 달라 지므로 그리기 커서 피드백에 대 한 적합 하지 않습니다.

##  <a name="onchangedrect"></a>  CRectTracker::OnChangedRect

추적기 사각형을 호출 하는 동안 변경 될 때마다 프레임 워크에서 호출 `Track`합니다.

```
virtual void OnChangedRect(const CRect& rectOld);
```

### <a name="parameters"></a>매개 변수

*rectOld*<br/>
이전 장치 좌표가 포함 된 `CRectTracker` 개체입니다.

### <a name="remarks"></a>설명

시간에이 함수가 호출 될 모든 피드백을 사용 하 여 그린 `DrawTrackerRect` 제거 되었습니다. 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다.

사각형의 크기가 조정 된 후 모든 작업을 수행 하려는 경우이 함수를 재정의 합니다.

##  <a name="setcursor"></a>  CRectTracker::SetCursor

위에 있는 동안 커서 모양을 변경 하려면이 함수를 호출 합니다 `CRectTracker` 개체의 영역입니다.

```
BOOL SetCursor(
    CWnd* pWnd,
    UINT nHitTest) const;
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
커서를 현재 포함 된 창 가리킵니다.

*nHitTest*<br/>
WM_SETCURSOR 메시지에서 이전 적중 횟수 테스트의 결과입니다.

### <a name="return-value"></a>반환 값

이전 적중 추적기 사각형; 위에서 되었으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

창의 WM_SETCURSOR 메시지를 처리 하는 함수 내에서이 함수 호출 (일반적으로 `OnSetCursor`).

##  <a name="track"></a>  CRectTracker::Track

사각형의 크기를 조정 하는 것에 대 한 사용자 인터페이스를 표시 하려면이 함수를 호출 합니다.

```
BOOL Track(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = FALSE,
    CWnd* pWndClipTo = NULL);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
사각형을 포함 하는 창 개체입니다.

*point*<br/>
장치 좌표 클라이언트 영역을 기준으로 마우스의 현재 위치입니다.

*bAllowInvert*<br/>
TRUE 인 경우 x 축 또는 y 축; 사각형을 반전 시킬 수 있습니다. 그렇지 않으면 FALSE입니다.

*pWndClipTo*<br/>
창으로 잘린 그리기 작업입니다. NULL 인 경우 *pWnd* 클리핑 사각형으로 사용 됩니다.

### <a name="return-value"></a>반환 값

ESC 키를 누르는 경우 추적 프로세스는 중지, 추적기에서 저장 되는 사각형 변경 되지 않습니다 및 0이 반환 됩니다. 변경 내용을 커밋할 경우 마우스를 이동 및 마우스 왼쪽된 단추에서 손을 떼기, 크기 및/또는 새 위치에에서 기록 됩니다 추적기의 사각형 하 고 0이 아닌 값이 반환 됩니다.

### <a name="remarks"></a>설명

이 일반적으로 호출에서 처리 하는 응용 프로그램의 함수 내에서 `WM_LBUTTONDOWN` 메시지 (일반적으로 `OnLButtonDown`).

이 함수는 사용자가 왼쪽된 마우스 단추를 놓을, ESC 키를 누르거나 오른쪽 마우스 단추를 누를 때까지 마우스를 캡처합니다. 마우스 커서를 이동 하는 사용자, 피드백을 호출 하 여 업데이트 됩니다 `DrawTrackerRect` 고 `OnChangedRect`입니다.

하는 경우 *bAllowInvert* 가 TRUE 이면 추적 사각형 x 축 또는 y 축에서 반전 시킬 수 있습니다.

##  <a name="trackrubberband"></a>  CRectTracker::TrackRubberBand

고무 밴드 선택 하려면이 함수를 호출 합니다.

```
BOOL TrackRubberBand(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = TRUE);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
사각형을 포함 하는 창 개체입니다.

*point*<br/>
장치 좌표 클라이언트 영역을 기준으로 마우스의 현재 위치입니다.

*bAllowInvert*<br/>
TRUE 인 경우 x 축 또는 y 축; 사각형을 반전 시킬 수 있습니다. 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

마우스를 이동 하 고 사각형 비어 있지 않으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

일반적으로 WM_LBUTTONDOWN 메시지를 처리 하는 응용 프로그램의 함수 내에서 호출 됩니다 (일반적으로 `OnLButtonDown`).

이 함수는 사용자가 왼쪽된 마우스 단추를 놓을, ESC 키를 누르거나 오른쪽 마우스 단추를 누를 때까지 마우스를 캡처합니다. 마우스 커서를 이동 하는 사용자, 피드백을 호출 하 여 업데이트 됩니다 `DrawTrackerRect` 고 `OnChangedRect`입니다.

추적 된 오른쪽 아래 핸들에서 고무 밴드 형식 선택 하 여 수행 됩니다. 반전 허용 되는 경우 사각형 크기를 조정할 수 중 하나를 왼쪽 또는 아래쪽 및 오른쪽을 끌어서 합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 추적기](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleResizeBar 클래스](../../mfc/reference/coleresizebar-class.md)<br/>
[CRect 클래스](../../atl-mfc-shared/reference/crect-class.md)
