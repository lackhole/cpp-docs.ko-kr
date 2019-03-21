---
title: CRect 클래스
ms.date: 11/06/2018
f1_keywords:
- CRect
- ATLTYPES/ATL::CRect
- ATLTYPES/ATL::CRect::CRect
- ATLTYPES/ATL::CRect::BottomRight
- ATLTYPES/ATL::CRect::CenterPoint
- ATLTYPES/ATL::CRect::CopyRect
- ATLTYPES/ATL::CRect::DeflateRect
- ATLTYPES/ATL::CRect::EqualRect
- ATLTYPES/ATL::CRect::Height
- ATLTYPES/ATL::CRect::InflateRect
- ATLTYPES/ATL::CRect::IntersectRect
- ATLTYPES/ATL::CRect::IsRectEmpty
- ATLTYPES/ATL::CRect::IsRectNull
- ATLTYPES/ATL::CRect::MoveToX
- ATLTYPES/ATL::CRect::MoveToXY
- ATLTYPES/ATL::CRect::MoveToY
- ATLTYPES/ATL::CRect::NormalizeRect
- ATLTYPES/ATL::CRect::OffsetRect
- ATLTYPES/ATL::CRect::PtInRect
- ATLTYPES/ATL::CRect::SetRect
- ATLTYPES/ATL::CRect::SetRectEmpty
- ATLTYPES/ATL::CRect::Size
- ATLTYPES/ATL::CRect::SubtractRect
- ATLTYPES/ATL::CRect::TopLeft
- ATLTYPES/ATL::CRect::UnionRect
- ATLTYPES/ATL::CRect::Width
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
ms.openlocfilehash: fadb430d570e516d915d520f06e4c247b131c3db
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739434"
---
# <a name="crect-class"></a>CRect 클래스

Windows 비슷합니다 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조입니다.

## <a name="syntax"></a>구문

```
class CRect : public tagRECT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CRect::CRect](#crect)|`CRect` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CRect::BottomRight](#bottomright)|오른쪽 아래 점을 반환 `CRect`합니다.|
|[CRect::CenterPoint](#centerpoint)|중심점을 반환 합니다 `CRect`합니다.|
|[CRect::CopyRect](#copyrect)|소스 사각형의 크기를 복사 `CRect`합니다.|
|[CRect::DeflateRect](#deflaterect)|높이 너비 감소 `CRect`합니다.|
|[CRect::EqualRect](#equalrect)|확인 여부를 `CRect` 지정 된 사각형과 같은지를 합니다.|
|[CRect::Height](#height)|높이 계산 `CRect`합니다.|
|[CRect::InflateRect](#inflaterect)|너비 및 높이 늘리는 `CRect`합니다.|
|[CRect::IntersectRect](#intersectrect)|집합 `CRect` 두 사각형이 겹치는 부분 같음.|
|[CRect::IsRectEmpty](#isrectempty)|확인 여부를 `CRect` 비어 있습니다. `CRect` 너비 및/또는 높이 0에서 하는 경우 비어 있습니다.|
|[CRect::IsRectNull](#isrectnull)|결정 여부를 `top`, `bottom`, `left`, 및 `right` 멤버 변수는 모두 0으로 동등 합니다.|
|[CRect::MoveToX](#movetox)|이동 `CRect` 에 지정 된 x 좌표입니다.|
|[CRect::MoveToXY](#movetoxy)|이동 `CRect` 에 지정 된 x 및 y 좌표입니다.|
|[CRect::MoveToY](#movetoy)|이동 `CRect` 에서 지정 된 y-좌표입니다.|
|[CRect::NormalizeRect](#normalizerect)|너비와 높이 표준화 `CRect`합니다.|
|[CRect::OffsetRect](#offsetrect)|이동 `CRect` 지정한 오프셋에서.|
|[CRect::PtInRect](#ptinrect)|지정 된 위치 내에 있는지 여부를 확인 `CRect`합니다.|
|[CRect::SetRect](#setrect)|차원의 설정 `CRect`합니다.|
|[CRect::SetRectEmpty](#setrectempty)|집합 `CRect` (모든 좌표가 0과 같음) 빈 사각형을 합니다.|
|[CRect::Size](#size)|크기를 계산 `CRect`합니다.|
|[CRect::SubtractRect](#subtractrect)|다른 하나의 사각형만을 뺍니다.|
|[CRect::TopLeft](#topleft)|왼쪽 위 점을 반환 `CRect`합니다.|
|[CRect::UnionRect](#unionrect)|집합 `CRect` 같은 두 개의 사각형의 합집합입니다.|
|[CRect::Width](#width)|너비를 계산 `CRect`합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CRect::operator -](#operator_-)|지정 된 오프셋을 뺍니다 `CRect` 압축 또는 `CRect` 결과 반환 하 고 `CRect`입니다.|
|[CRect::operator LPCRECT](#operator_lpcrect)|`CRect`를 `LPCRECT`로 변환합니다.|
|[CRect::operator LPRECT](#operator_lprect)|`CRect`를 `LPRECT`로 변환합니다.|
|[CRect::operator !=](#operator_neq)|확인 여부를 `CRect` 사각형와 같지 않습니다.|
|[CRect::operator &amp;](#operator_amp)|교차 부분을 만듭니다 `CRect` 사각형 및 결과 반환 하 고 `CRect`입니다.|
|[CRect::operator &amp;=](#operator_amp_eq)|집합 `CRect` 의 교집합 같음 `CRect` 및 사각형입니다.|
|[CRect::operator&#124;](#operator_or)|합집합을 만듭니다 `CRect` 사각형 및 결과 반환 하 고 `CRect`입니다.|
|[CRect::operator &#124;=](#operator_or_eq)|집합 `CRect` 합한 같음 `CRect` 및 사각형입니다.|
|[CRect::operator +](#operator_add)|지정 된 오프셋을 추가 `CRect` 를 확장 하거나 `CRect` 결과 반환 합니다. `CRect`합니다.|
|[CRect::operator +=](#operator_add_eq)|지정한 오프셋을 추가 `CRect` 를 확장 또는 `CRect`합니다.|
|[CRect::operator =](#operator_eq)|사각형의 크기를 복사 `CRect`합니다.|
|[CRect::operator -=](#operator_-_eq)|지정 된 오프셋을 뺍니다 `CRect` 압축 또는 `CRect`합니다.|
|[CRect::operator ==](#operator_eq_eq)|결정 하는지 여부를 `CRect` 사각형에 같습니다.|

## <a name="remarks"></a>설명

`CRect` 또한 다음 조작 하는 멤버 함수 `CRect` 개체 및 Windows `RECT` 구조입니다.

`CRect` 개체를 함수 매개 변수로 전달할 수 있습니다 위치를 `RECT` 구조 `LPCRECT`, 또는 `LPRECT` 전달 될 수 있습니다.

> [!NOTE]
> 이 클래스에서 파생 되는 `tagRECT` 구조입니다. (이름을 `tagRECT` 이름인 덜 일반적으로 사용에 대 한는 `RECT` 구조입니다.) 즉, 데이터 멤버 (`left`, `top`를 `right`, 및 `bottom`)의 합니다 `RECT` 구조는 액세스할 수 있는 데이터 멤버의 `CRect`합니다.

`CRect` 사각형의 왼쪽 위 및 맨 아래 왼쪽 지점을 정의 하는 멤버 변수를 포함 합니다.

지정 하는 경우는 `CRect`, 정규화 됩니다 있도록 데 주의 해야-즉, 왼쪽된 좌표 값을 사용 하면 오른쪽 맨 위에 보다 작으면이 아래쪽 미만입니다. 예를 들어 top (10,10)의 왼쪽 (20,20)의 오른쪽 아래에 정사각형을 정의 하지만 top (20,20)의 왼쪽 및 (10,10)의 오른쪽 아래에서 정규화 되지 않은 사각형을 정의 합니다. 사각형은 정규화 되지 않으므로 많은 경우 `CRect` 멤버 함수는 잘못 된 결과 반환할 수 있습니다. (참조 [crect:: Normalizerect](#normalizerect) 이러한 함수의 목록은.) 정규화 되지 않은 사각형을 정규화 할 수 있습니다를 호출 하 여 정규화 된 사각형을 필요로 하는 함수를 호출 하기 전에 `NormalizeRect` 함수입니다.

조작 하는 경우 주의 해야는 `CRect` 사용 하 여 합니다 [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp) 및 [CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp) 멤버 함수입니다. Y-범위는 음수 이면 에서처럼 표시 컨텍스트 매핑 모드 인지 `MM_LOENGLISH`, 한 다음 `CDC::DPtoLP` 변환 됩니다는 `CRect` 맨 위쪽 보다 되도록 합니다. 와 같은 함수 `Height` 하 고 `Size` 그런 다음 변환 된 높이 대 한 음수 값을 반환 합니다 `CRect`, 정규화 되지 않은 사각형 됩니다.

사용 하 여이 오버 로드 `CRect` 연산자는 첫 번째 피연산자 이어야 합니다는 `CRect`; 두 일 수 있습니다를 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 `CRect` 개체.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagRECT`

`CRect`

## <a name="requirements"></a>요구 사항

**헤더:** atltypes.h

##  <a name="bottomright"></a>  CRect::BottomRight

좌표에 대 한 참조로 반환 되는 [CPoint](cpoint-class.md) 개체에 포함 된 `CRect`합니다.

```
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```

### <a name="return-value"></a>반환 값

사각형의 오른쪽 아래 모퉁이의 좌표입니다.

### <a name="remarks"></a>설명

Get 또는 set 사각형의 오른쪽 아래 모서리에이 함수를 사용할 수 있습니다. 대입 연산자의 좌 변에 있는이 함수를 사용 하 여 모퉁이 설정 합니다.

### <a name="example"></a>예제

```cpp
// use BottomRight() to retrieve the bottom
// right POINT
CRect rect(210, 150, 350, 900);
CPoint ptDown;

ptDown = rect.BottomRight();

// ptDown is now set to (350, 900)
ASSERT(ptDown == CPoint(350, 900));

// or, use BottomRight() to set the bottom
// right POINT
CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);

CRect rect2(10, 10, 350, 350);
CPoint ptLow(180, 180);
rect2.BottomRight() = ptLow;

// rect2 is now (10, 10, 180, 180)
ASSERT(rect2 == CRect(10, 10, 180, 180));
```

##  <a name="centerpoint"></a>  CRect::CenterPoint

중심점 계산 `CRect` 왼쪽 및 오른쪽 값을 추가 하 고 2로 나눈, 위쪽 및 아래쪽 값을 추가 및 2로 나눈 여 합니다.

```
CPoint CenterPoint() const throw();
```

### <a name="return-value"></a>반환 값

A `CPoint` 개체의 중심점입니다 `CRect`합니다.

### <a name="example"></a>예제

```cpp
// Code from this OnPaint() implementation can be pasted into your own application
// to draw lines that would look like a letter "Y" within your dialog.
void CMyDlg::OnPaint()
{
    CPaintDC dc(this);

    // device context for painting

    // get the size and position of the client area of
    // your window

    CRect rect;
    GetClientRect(&rect);

    // Move the current pen to the top left of the window. We call the
    // TopLeft() member of CRect here and it returns a CPoint object we
    // pass to the override of CDC::MoveTo() that accepts a CPoint.

    dc.MoveTo(rect.TopLeft());

    // Draw a line from the top left to the center of the window.
    // CenterPoint() gives us the middle point of the window as a
    // CPoint, and since CDC::LineTo() has an override that accepts a
    // CPoint, we can just pass it along.

    dc.LineTo(rect.CenterPoint());

    // Now, draw a line to the top right of the window. There's no
    // CRect member which returns a CPoint for the top right of the
    // window, so we'll reference the CPoint members directly and call
    // the CDC::LineTo() override which takes two integers.

    dc.LineTo(rect.right, rect.top);

    // The top part of the "Y" is drawn. Now, we'll draw the stem. We
    // start from the center point.

    dc.MoveTo(rect.CenterPoint());

    // and then draw to the middle of the bottom edge of the window.
    // We'll get the x-coordinate from the x member of the CPOINT
    // returned by CenterPoint(), and the y value comes directly from
    // the rect.

    dc.LineTo(rect.CenterPoint().x, rect.bottom);
}
```

##  <a name="copyrect"></a>  CRect::CopyRect

복사 합니다 `lpSrcRect` 에 사각형 `CRect`합니다.

```
void CopyRect(LPCRECT lpSrcRect) throw();
```

### <a name="parameters"></a>매개 변수

*lpSrcRect*<br/>
가리키는 합니다 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 `CRect` 복사 하는 개체입니다.

### <a name="example"></a>예제

```cpp
CRect rectSource(35, 10, 125, 10);
CRect rectDest;

rectDest.CopyRect(&rectSource);

// rectDest is now set to (35, 10, 125, 10)

RECT rectSource2;
rectSource2.left = 0;
rectSource2.top = 0;
rectSource2.bottom = 480;
rectSource2.right = 640;

rectDest.CopyRect(&rectSource2);

// works against RECT structures, too!
// rectDest is now set to (0, 0, 640, 480)
```

##  <a name="crect"></a>  CRect::CRect

`CRect` 개체를 생성합니다.

```
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();
```

### <a name="parameters"></a>매개 변수

*l*<br/>
왼쪽된 위치를 지정 `CRect`합니다.

*t*<br/>
맨 위에 지정 `CRect`합니다.

*r*<br/>
올바른 위치를 지정 `CRect`합니다.

*b*<br/>
아래 지정 `CRect`합니다.

*srcRect*<br/>
참조 하는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 좌표를 사용 하 여 구조 `CRect`합니다.

*lpSrcRect*<br/>
가리키는 합니다 `RECT` 좌표를 사용 하 여 구조 `CRect`합니다.

*point*<br/>
생성 되는 사각형의 원점을 지정 합니다. 왼쪽 위 모퉁이에 해당합니다.

*size*<br/>
생성할 사각형의 오른쪽 아래 모퉁이를 왼쪽 위 모서리에서 치환을 지정 합니다.

*topLeft*<br/>
왼쪽 위 위치를 지정 `CRect`합니다.

*bottomRight*<br/>
오른쪽 아래 위치를 지정 `CRect`합니다.

### <a name="remarks"></a>설명

인수 없이 지정 된 경우 `left`, `top`를 `right`, 및 `bottom` 멤버 초기화 되지 않습니다.

합니다 `CRect`(`const RECT&`) 및 `CRect`(`LPCRECT`) 수행 하는 생성자를 [CopyRect](#copyrect)합니다. 다른 생성자는 직접 개체의 멤버 변수를 초기화 합니다.

### <a name="example"></a>예제

```cpp
// default constructor doesn't initialize!
CRect rectUnknown;

// four-integers are left, top, right, and bottom
CRect rect(0, 0, 100, 50);
ASSERT(rect.Width() == 100);
ASSERT(rect.Height() == 50);

// Initialize from RECT stucture
RECT sdkRect;
sdkRect.left = 0;
sdkRect.top = 0;
sdkRect.right = 100;
sdkRect.bottom = 50;

CRect rect2(sdkRect);
// by reference
CRect rect3(&sdkRect);

// by address
ASSERT(rect2 == rect);
ASSERT(rect3 == rect);

// from a point and a size
CPoint pt(0, 0);
CSize sz(100, 50);
CRect rect4(pt, sz);
ASSERT(rect4 == rect2);

// from two points
CPoint ptBottomRight(100, 50);
CRect rect5(pt, ptBottomRight);
ASSERT(rect5 == rect4);
```

##  <a name="deflaterect"></a>  CRect::DeflateRect

`DeflateRect` 압축 `CRect` 해당 면의 중심 쪽으로 이동 하 여 합니다.

```
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
오른쪽 및 왼쪽 deflate 단위 수가 지정 `CRect`합니다.

*y*<br/>
위쪽 및 아래쪽 deflate 단위의 수를 지정 `CRect`합니다.

*size*<br/>
A [크기](/windows/desktop/api/windef/ns-windef-tagsize) 하거나 [CSize](csize-class.md) deflate 단위의 수를 지정 하는 `CRect`합니다. 합니다 `cx` 왼쪽과 오른쪽 deflate 단위의 수를 지정 하는 값 및 `cy` 값 위쪽과 아래쪽 deflate 단위의 수를 지정 합니다.

*lpRect*<br/>
가리키는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 `CRect` 양쪽 deflate 단위의 수를 지정 하는 합니다.

*l*<br/>
좌 변의 deflate 단위의 수를 지정 `CRect`합니다.

*t*<br/>
맨 위에 deflate 단위의 수를 지정 `CRect`합니다.

*r*<br/>
오른쪽에 있는 deflate 단위의 수를 지정 `CRect`합니다.

*b*<br/>
아래쪽 deflate 단위의 수를 지정 `CRect`합니다.

### <a name="remarks"></a>설명

이렇게 하려면 `DeflateRect` 왼쪽, 위쪽 단위를 추가 하 고 오른쪽 아래에서 장치를 뺍니다. 매개 변수 `DeflateRect` 서명할지 값; deflate 양수 값 `CRect` 음수 값을 확장 하 고 있습니다.

처음 두 오버 로드는 두 쌍의 반대쪽의 deflate `CRect` 총 너비가 두 배 감소 되도록 *x* (또는 `cx`) 및 두 번의 전체 높이 감소 *y* ( 또는 `cy`). 다른 두 개의 오버 로드의 양쪽 deflate `CRect` 독립적입니다.

### <a name="example"></a>예제

```cpp
   CRect rect(10, 10, 50, 50);
   rect.DeflateRect(1, 2);
   ASSERT(rect.left == 11 && rect.right == 49);
   ASSERT(rect.top == 12 && rect.bottom == 48);

   CRect rect2(10, 10, 50, 50);
   CRect rectDeflate(1, 2, 3, 4);
   rect2.DeflateRect(&rectDeflate);
   ASSERT(rect2.left == 11 && rect2.right == 47);
   ASSERT(rect2.top == 12 && rect2.bottom == 46);
```

##  <a name="equalrect"></a>  CRect::EqualRect

확인 여부를 `CRect` 지정 된 사각형과 같은지를 합니다.

```
BOOL EqualRect(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>매개 변수

*lpRect*<br/>
가리키는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 `CRect` 사각형의 왼쪽 및 오른쪽 아래 모퉁이 좌표를 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

두 사각형이 동일한 위쪽, 왼쪽, 아래쪽 및 오른쪽 값 있으면 0이 아닌 값 그렇지 않으면 0입니다.

> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1.EqualRect(rect2));
ASSERT(!rect1.EqualRect(rect3));
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1.EqualRect(&test));
```

##  <a name="height"></a>  CRect::Height

높이 계산 `CRect` 아래쪽 값에서 상위 값을 빼서 합니다.

```
int Height() const throw();
```

### <a name="return-value"></a>반환 값

높이 `CRect`합니다.

### <a name="remarks"></a>설명

결과 값은 음수일 수 있습니다.

> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

// nHt is now 40
ASSERT(nHt == 40);
```

##  <a name="inflaterect"></a>  CRect::InflateRect

`InflateRect` 확장 `CRect` 중심에서의 측면을 이동 하 여 합니다.

```
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
오른쪽 및 왼쪽 확장 단위의 수를 지정 `CRect`합니다.

*y*<br/>
위쪽 및 아래쪽 확장 단위의 수를 지정 `CRect`합니다.

*size*<br/>
A [크기](/windows/desktop/api/windef/ns-windef-tagsize) 하거나 [CSize](csize-class.md) 확장 단위의 수를 지정 하는 `CRect`합니다. 합니다 `cx` 왼쪽과 오른쪽 확장 단위의 수를 지정 하는 값 및 `cy` 값 위쪽과 아래쪽 확장 단위의 수를 지정 합니다.

*lpRect*<br/>
가리키는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 `CRect` 양쪽 확장 단위의 수를 지정 하는 합니다.

*l*<br/>
왼쪽된에 있는 확장 단위의 수를 지정 `CRect`합니다.

*t*<br/>
맨 위에 확장 단위의 수를 지정 `CRect`합니다.

*r*<br/>
오른쪽에 있는 확장 단위의 수를 지정 `CRect`합니다.

*b*<br/>
아래쪽 확장 단위의 수를 지정 `CRect`합니다.

### <a name="remarks"></a>설명

이렇게 하려면 `InflateRect` 단위 왼쪽 및 위쪽에서 빼고 오른쪽 아래에 단위를 추가 합니다. 매개 변수 `InflateRect` 서명 된 값입니다; 양수 값 확장 `CRect` 및 음수 값 deflate 것입니다.

처음 두 오버 로드는 두 쌍의 반대쪽의 확장 `CRect` 총 너비가 두 배로 증가 되도록 *x* (또는 `cx`) 및 총 높이 만큼 두 배 증분됩니다 *y* ( 또는 `cy`). 다른 두 개의 오버 로드가 확장의 각 면 `CRect` 독립적입니다.

### <a name="example"></a>예제

```cpp
CRect rect(0, 0, 300, 300);
rect.InflateRect(50, 200);

// rect is now (-50, -200, 350, 500)
ASSERT(rect == CRect(-50, -200, 350, 500));
```

##  <a name="intersectrect"></a>  CRect::IntersectRect

`CRect` 두 기존 사각형이 겹치는 부분 같음.

```
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>매개 변수

*lpRect1*<br/>
가리키는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 `CRect` 소스 사각형을 포함 하는 개체입니다.

*lpRect2*<br/>
가리키는 `RECT` 구조 또는 `CRect` 소스 사각형을 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

교집합이 비어 있지 않으면 0이 아닌 교집합이 비어 있는 경우 0입니다.

### <a name="remarks"></a>설명

교집합 모두 기존 사각형에 포함 된 가장 큰 사각형입니다.

> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
CRect rectOne(125, 0, 150, 200);
CRect rectTwo(0, 75, 350,  95);
CRect rectInter;
```cpp
   CRect rectOne(125,  0, 150, 200);
   CRect rectTwo(0, 75, 350, 95);
   CRect rectInter;

   rectInter.IntersectRect(rectOne, rectTwo);
ASSERT(rectInter == CRect(125, 75, 150, 95));
// operator &= can do the same task:

CRect rectInter2 = rectOne;
rectInter2 &= rectTwo;
ASSERT(rectInter2 == CRect(125, 75, 150, 95));
```

##  <a name="isrectempty"></a>  CRect::IsRectEmpty

확인 여부를 `CRect` 비어 있습니다.

```
BOOL IsRectEmpty() const throw();
```

### <a name="return-value"></a>반환 값

0이 아닌 경우 `CRect` 빈 되었으면 0 경우 `CRect` 비어 있지 않습니다.

### <a name="remarks"></a>설명

사각형의 너비 및/또는 높이 0에서 하는 경우에 비어 있거나 음수 경우 다른 `IsRectNull`, 영역의 모든 좌표는 0이 있는지 여부를 결정 합니다.

> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
```cpp
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
   ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
   ASSERT(rectEmpty.IsRectEmpty());
```

##  <a name="isrectnull"></a>  CRect::IsRectNull

여부를 위쪽, 왼쪽, 아래쪽, 확인 및의 값을 오른쪽 `CRect` 은 모두 0입니다.

```
BOOL IsRectNull() const throw();
```

### <a name="return-value"></a>반환 값

0이 아닌 경우 `CRect`의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값은 모두 0이 고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

다른 `IsRectEmpty`, 사각형이 비어 있는지 여부를 결정 합니다.

### <a name="example"></a>예제

```cpp
CRect rectNone(0, 0, 0, 0);
CRect rectSome(35, 50, 135, 150);
```cpp
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
   ASSERT(!rectSome.IsRectNull());
// note that null means _all_ zeros

CRect rectNotNull(0, 0, 35, 50);
ASSERT(!rectNotNull.IsRectNull());
```

##  <a name="movetox"></a>  CRect::MoveToX

절대 x 좌표를 지정 된 사각형을 이동 하려면이 함수를 호출 *x*합니다.

```
void MoveToX(int x) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
사각형의 왼쪽 위 모퉁이 대 한 절대 x 좌표입니다.

### <a name="example"></a>예제

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToX(10);
```cpp
   CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

   // rect is now (10, 0, 110, 100);
   ASSERT(rect == CRect(10, 0, 110, 100));
```

##  <a name="movetoxy"></a>  CRect::MoveToXY

에 절대 x 좌표와 y-지정 된 사각형을 이동 하려면이 함수를 호출 합니다.

```
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
사각형의 왼쪽 위 모퉁이 대 한 절대 x 좌표입니다.

*y*<br/>
사각형의 왼쪽 위 모퉁이 대 한 절대 y 좌표입니다.

*point*<br/>
`POINT` 구조 사각형의 절대 왼쪽 위 모퉁이 지정 합니다.

### <a name="example"></a>예제

```cpp
CRect rect(0, 0, 100, 100);
rect.MoveToXY(10, 10);
```cpp
   CRect rect(0, 0, 100, 100);
   rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
   ASSERT(rect == CRect(10, 10, 110, 110));
```

##  <a name="movetoy"></a>  CRect::MoveToY

절대 y 좌표를 지정 된 사각형을 이동 하려면이 함수를 호출 *y*합니다.

```
void MoveToY(int y) throw();
```

### <a name="parameters"></a>매개 변수

*y*<br/>
사각형의 왼쪽 위 모퉁이 대 한 절대 y 좌표입니다.

### <a name="example"></a>예제

```cpp
   CRect rect(0, 0, 100, 100);
   rect.MoveToY(10);
   // rect is now (0, 10, 100, 110);
   ASSERT(rect == CRect(0, 10, 100, 110));
```

##  <a name="normalizerect"></a>  CRect::NormalizeRect

정규화 `CRect` 높이 너비는 양의 수 있도록 합니다.

```
void NormalizeRect() throw();
```

### <a name="remarks"></a>설명

사각형 네 번째 구성 요소 위치 지정에 대 한 정규화 된 좌표에 대 한 일반적으로 Windows를 사용 합니다. `NormalizeRect` 위쪽 및 아래쪽 값을 비교 하 고 맨 아래 보다 큰 경우이 바꿉니다. 마찬가지로 왼쪽 오른쪽 보다 크면 왼쪽 및 오른쪽 값을 바꿉니다. 이 함수는 서로 다른 매핑 모드를 사용 하 여 처리 하는 경우에 유용 및 사각형을 반전 합니다.

> [!NOTE]
> 다음 `CRect` 멤버 함수는 정규화 된 사각형 제대로 작동 하려면 필요 합니다. [높이](#height), [너비](#width)를 [크기](#size)를 [IsRectEmpty](#isrectempty)를 [PtInRect](#ptinrect)를 [EqualRect](#equalrect), [UnionRect](#unionrect), [IntersectRect](#intersectrect)합니다 [SubtractRect](#subtractrect)를 [연산자 = =](#operator_eq_eq), [연산자! =](#operator_neq), [연산자 &#124; ](#operator_or)를 [연산자 &#124;=](#operator_or_eq)합니다 [연산자 &](#operator_amp), 및 [연산자 & =](#operator_amp_eq).

### <a name="example"></a>예제

```cpp
   CRect rect1(110, 100, 250, 310);
   CRect rect2(250, 310, 110, 100);
   rect1.NormalizeRect();
   rect2.NormalizeRect();
   ASSERT(rect1 == rect2);
```

##  <a name="offsetrect"></a>  CRect::OffsetRect

이동 `CRect` 지정한 오프셋에서.

```
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();
```

### <a name="parameters"></a>매개 변수

*x*<br/>
오른쪽 또는 왼쪽으로 이동 하는 크기를 지정 합니다. 왼쪽으로 이동 하려면 음수 여야 합니다.

*y*<br/>
위로 또는 아래로 이동할 크기를 지정 합니다. 위로 이동 하려면 음수 여야 합니다.

*point*<br/>
포함 된 [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 또는 [CPoint](cpoint-class.md) 이동 하는 두 크기 모두를 지정 하는 개체입니다.

*size*<br/>
포함 된 [크기](/windows/desktop/api/windef/ns-windef-tagsize) 구조 또는 [CSize](csize-class.md) 이동 하는 두 크기 모두를 지정 하는 개체입니다.

### <a name="remarks"></a>설명

이동 `CRect` *x* 축의 단위 및 *y* 축의 단위입니다. 합니다 *x* 하 고 *y* 매개 변수는 부호 있는 값 이므로 `CRect` 왼쪽 이동 하거나 오른쪽 및 위나 아래로 합니다.

### <a name="example"></a>예제

```cpp
   CRect rect(0, 0, 35, 35);
   rect.OffsetRect(230, 230);

   // rect is now (230, 230, 265, 265)
   ASSERT(rect == CRect(230, 230, 265, 265));
```

##  <a name="operator_lpcrect"></a>  CRect::operator LPCRECT 변환 된 `CRect` 에 [LPCRECT](../../mfc/reference/data-types-mfc.md)합니다.

```
operator LPCRECT() const throw();
```

### <a name="remarks"></a>설명

주소 않아도이 함수를 사용 하는 경우 (**&**) 연산자. 전달 하는 경우이 연산자 자동으로 사용을 `CRect` 필요로 하는 함수 개체는 `LPCRECT`합니다.

##  <a name="operator_lprect"></a>  CRect::operator LPRECT

변환 된 `CRect` 에 [LPRECT](../../mfc/reference/data-types-mfc.md).

```
operator LPRECT() throw();
```

### <a name="remarks"></a>설명

주소 않아도이 함수를 사용 하는 경우 (**&**) 연산자. 전달 하는 경우이 연산자 자동으로 사용을 `CRect` 필요로 하는 함수 개체는 `LPRECT`합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CRect::operator LPCRECT](#operator_lpcrect)합니다.

##  <a name="operator_eq"></a>  CRect::operator =

할당 *srcRect* 에 `CRect`입니다.

```
void operator=(const RECT& srcRect) throw();
```

### <a name="parameters"></a>매개 변수

*srcRect*<br/>
소스 사각형을 가리킵니다. 수는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 또는 `CRect`합니다.

### <a name="example"></a>예제

```cpp
   CRect rect(0, 0, 127, 168);
   CRect rect2;

   rect2 = rect;
   ASSERT(rect2 == CRect(0, 0, 127, 168));
```

##  <a name="operator_eq_eq"></a>  CRect::operator ==

결정 여부 `rect` 같은지를 `CRect` 해당 왼쪽 및 오른쪽 아래 모퉁이의 좌표를 비교 하 여 합니다.

```
BOOL operator==(const RECT& rect) const throw();
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
소스 사각형을 가리킵니다. 수는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 또는 `CRect`합니다.

### <a name="return-value"></a>반환 값

개체가 동일 하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999, 6, 3);
ASSERT(rect1 == rect2);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect1 == test);
```

##  <a name="operator_neq"></a>  CRect::operator !=

결정 여부 *rect* 같지 않은 `CRect` 해당 왼쪽 및 오른쪽 아래 모퉁이의 좌표를 비교 하 여.

```
BOOL operator!=(const RECT& rect) const throw();
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
소스 사각형을 가리킵니다. 수는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 또는 `CRect`합니다.

### <a name="return-value"></a>반환 값

같지 않음; 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
CRect rect1(35, 150, 10, 25);
CRect rect2(35, 150, 10, 25);
CRect rect3(98, 999,  6,  3);
ASSERT(rect1 != rect3);
// works just fine against RECTs, as well

RECT test;
test.left = 35;
test.top = 150;
test.right = 10;
test.bottom = 25;

ASSERT(rect3 != test);
```

##  <a name="operator_add_eq"></a>  CRect::operator +=

처음 두 오버 로드를 이동 `CRect` 지정한 오프셋에서.

```
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
A [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 나 [CPoint](cpoint-class.md) 사각형을 이동할 단위의 수를 지정 하는 개체입니다.

*size*<br/>
A [크기](/windows/desktop/api/windef/ns-windef-tagsize) 구조 나 [CSize](csize-class.md) 사각형을 이동할 단위의 수를 지정 하는 개체입니다.

*lpRect*<br/>
가리키는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 `CRect` 양쪽 확장 단위의 수를 포함 하는 개체 `CRect`합니다.

### <a name="remarks"></a>설명

매개 변수의 *x* 하 고 *y* (또는 `cx` 하 고 `cy`) 값에 추가 됩니다 `CRect`합니다.

세 번째 오버 로드를 확장 `CRect` 매개 변수의 각 멤버에 지정 된 단위 수입니다.

### <a name="example"></a>예제

```cpp
   CRect   rect1(100, 235, 200, 335);
   CPoint  pt(35, 65);
   CRect   rect2(135, 300, 235, 400);

   rect1 += pt;
   ASSERT(rect1 == rect2);
```

##  <a name="operator_-_eq"></a>  CRect::operator -=

처음 두 오버 로드를 이동 `CRect` 지정한 오프셋에서.

```
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
A [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 나 [CPoint](cpoint-class.md) 사각형을 이동할 단위의 수를 지정 하는 개체입니다.

*size*<br/>
A [크기](/windows/desktop/api/windef/ns-windef-tagsize) 구조 나 [CSize](csize-class.md) 사각형을 이동할 단위의 수를 지정 하는 개체입니다.

*lpRect*<br/>
가리키는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 `CRect` 양쪽 deflate 단위의 수를 포함 하는 개체 `CRect`합니다.

### <a name="remarks"></a>설명

매개 변수의 *x* 하 고 *y* (또는 `cx` 하 고 `cy`) 값에서 뺀 `CRect`합니다.

세 번째 오버 로드를 압축 `CRect` 매개 변수의 각 멤버에 지정 된 단위 수입니다. 이 오버 로드와 같은 함수는 [DeflateRect](#deflaterect)합니다.

### <a name="example"></a>예제

```cpp
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);

   rect1 -= pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect1 == rectResult);
```

##  <a name="operator_amp_eq"></a>  CRect::operator &amp;=

집합 `CRect` 의 교집합 같음 `CRect` 고 `rect`입니다.

```
void operator&=(const RECT& rect) throw();
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
포함 된 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 또는 `CRect`합니다.

### <a name="remarks"></a>설명

교집합에는 두 사각형에 포함 된 가장 큰 사각형입니다.

> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CRect::IntersectRect](#intersectrect)합니다.

##  <a name="operator_or_eq"></a>  CRect::operator &#124;=

집합 `CRect` 합한 같음 `CRect` 고 `rect`입니다.

```
void operator|=(const RECT& rect) throw();
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
포함 된 `CRect` 또는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect)합니다.

### <a name="remarks"></a>설명

공용 구조체는 두 원본 사각형이 포함 된 가장 작은 사각형입니다.

> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);

   rect1 |= rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect1);
```

##  <a name="operator_add"></a>  CRect::operator +

처음 두 오버 로드를 반환을 `CRect` 개체와 같음 `CRect` 지정한 오프셋에 의해 치환입니다.

```
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
A [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 나 [CPoint](cpoint-class.md) 반환 값을 이동할 단위의 수를 지정 하는 개체입니다.

*size*<br/>
A [크기](/windows/desktop/api/windef/ns-windef-tagsize) 구조 나 [CSize](csize-class.md) 반환 값을 이동할 단위의 수를 지정 하는 개체입니다.

*lpRect*<br/>
가리키는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 `CRect` 반환 값의 각 측면을 확장 하는 단위 수를 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

합니다 `CRect` 이동 또는 값에서 결과 `CRect` 매개 변수에 지정 된 단위 수로 합니다.

### <a name="remarks"></a>설명

매개 변수의 *x* 하 고 *y* (또는 `cx` 및 `cy`) 매개 변수가 추가 됩니다 `CRect`의 위치입니다.

세 번째 오버 로드는 새 반환 `CRect` 와 같은 `CRect` 매개 변수의 각 멤버에 지정 된 단위 수로 확장 합니다.

### <a name="example"></a>예제

```cpp
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 + pt;
   CRect   rectResult(135, 300, 235, 400);
   ASSERT(rectResult == rect2);
```

##  <a name="operator_-"></a>  CRect::operator -

처음 두 오버 로드를 반환을 `CRect` 개체와 같음 `CRect` 지정한 오프셋에 의해 치환입니다.

```
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
A [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 또는 `CPoint` 반환 값을 이동할 단위의 수를 지정 하는 개체입니다.

*size*<br/>
A [크기](/windows/desktop/api/windef/ns-windef-tagsize) 구조 또는 `CSize` 반환 값을 이동할 단위의 수를 지정 하는 개체입니다.

*lpRect*<br/>
가리키는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 `CRect` 반환 값의 각 면 deflate 단위의 수를 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

합니다 `CRect` 이동 또는 deflating 결과 `CRect` 매개 변수에 지정 된 단위 수로 합니다.

### <a name="remarks"></a>설명

매개 변수의 *x* 하 고 *y* (또는 `cx` 및 `cy`) 매개 변수에서 공제 `CRect`의 위치입니다.

세 번째 오버 로드는 새 반환 `CRect` 와 같은 `CRect` 매개 변수의 각 멤버에 지정 된 단위 수로 축소 됩니다. 이 오버 로드와 같은 함수는 [DeflateRect](#deflaterect)가 아닌 [SubtractRect](#subtractrect)합니다.

### <a name="example"></a>예제

```cpp
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 - pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect2 == rectResult);
```

##  <a name="operator_amp"></a>  CRect::operator &amp;

반환 된 `CRect` 의 교집합입니다 `CRect` 및 *rect2*합니다.

```
CRect operator&(const RECT& rect2) const throw();
```

### <a name="parameters"></a>매개 변수

*rect2*<br/>
포함 된 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 또는 `CRect`합니다.

### <a name="return-value"></a>반환 값

A `CRect` 의 교집합입니다 `CRect` 하 고 *rect2*합니다.

### <a name="remarks"></a>설명

교집합에는 두 사각형에 포함 된 가장 큰 사각형입니다.

> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 & rect2;
   CRect   rectResult(100, 100, 200, 200);
   ASSERT(rectResult == rect3);
```

##  <a name="operator_or"></a>  CRect::operator &#124;

반환 된 `CRect` 의 합집합입니다 `CRect` 하 고 *rect2*.

```
CRect operator|(const RECT&
rect2) const throw();
```

### <a name="parameters"></a>매개 변수

*rect2*<br/>
포함 된 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 또는 `CRect`합니다.

### <a name="return-value"></a>반환 값

A `CRect` 의 합집합입니다 `CRect` 하 고 *rect2*합니다.

### <a name="remarks"></a>설명

공용 구조체는 두 사각형을 포함 하는 가장 작은 사각형입니다.

> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 | rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);
```

##  <a name="ptinrect"></a>  CRect::PtInRect

지정 된 위치 내에 있는지 여부를 확인 `CRect`합니다.

```
BOOL PtInRect(POINT point) const throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
포함 된 [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 또는 [CPoint](cpoint-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

지점 내에 0이 아닌 `CRect`그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

안에 점이 `CRect` 왼쪽 가장자리나 위쪽 쪽에서 네 면 모두 내 여부. 오른쪽 또는 아래쪽 면에 점이 외부 `CRect`합니다.

> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
CRect rect(5, 5, 100, 100);
CPoint pt1(35, 50);
CPoint pt2(125, 298);

// this is true, because pt1 is inside the rectangle
ASSERT(rect.PtInRect(pt1));

// this is NOT true, because pt2 is outside the rectangle
ASSERT(!rect.PtInRect(pt2));

// note that the right and the bottom aren't inside
ASSERT(!rect.PtInRect(CPoint(35, 100)));
ASSERT(!rect.PtInRect(CPoint(100, 98)));

// but the top and the left are inside
ASSERT(rect.PtInRect(CPoint(5, 65)));
ASSERT(rect.PtInRect(CPoint(88, 5)));

// and that PtInRect() works against a POINT, too
POINT pt;
pt.x = 35;
pt.y = 50;
ASSERT(rect.PtInRect(pt));
```

##  <a name="setrect"></a>  CRect::SetRect

차원의 설정 `CRect` 지정된 된 좌표에 있습니다.

```
void SetRect(int x1, int y1, int x2, int y2) throw();
```

### <a name="parameters"></a>매개 변수

*x1*<br/>
왼쪽 위 모퉁이의 x 좌표를 지정합니다.

*y1*<br/>
왼쪽 위 모퉁이의 y 좌표를 지정합니다.

*x2*<br/>
오른쪽 아래 모퉁이의 x 좌표를 지정합니다.

*y2*<br/>
오른쪽 아래 모퉁이의 y 좌표를 지정합니다.

### <a name="example"></a>예제

```cpp
   CRect rect;
   rect.SetRect(256, 256, 512, 512);
   ASSERT(rect == CRect(256, 256, 512, 512));
```

##  <a name="setrectempty"></a>  CRect::SetRectEmpty

`CRect` 모든 좌표가 0으로 설정 하 여 null 사각형입니다.

```
void SetRectEmpty() throw();
```

### <a name="example"></a>예제

```cpp
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());
```

##  <a name="size"></a>  CRect::SIZE

합니다 `cx` 하 고 `cy` 멤버의 반환 값의 너비와 높이가 포함 `CRect`합니다.

```
CSize Size() const throw();
```

### <a name="return-value"></a>반환 값

A [CSize](csize-class.md) 개체의 크기를 포함 하는 `CRect`합니다.

### <a name="remarks"></a>설명

너비 또는 높이 음수일 수 있습니다.

> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
CRect rect(10, 10, 50, 50);
CSize sz = rect.Size();
ASSERT(sz.cx == 40 && sz.cy == 40);
```

##  <a name="subtractrect"></a>  CRect::SubtractRect

크기를 사용 하면 합니다 `CRect` 빼기를 같음 `lpRectSrc2` 에서 `lpRectSrc1`합니다.

```
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```

### <a name="parameters"></a>매개 변수

*lpRectSrc1*<br/>
가리키는 합니다 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 `CRect` 사각형 뺄 개체입니다.

*lpRectSrc2*<br/>
가리키는 합니다 `RECT` 구조 또는 `CRect` 가리키는 사각형에서 뺄에 있는 개체를 *lpRectSrc1* 매개 변수입니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

빼기가 모든 점을 포함 하는 가장 작은 사각형 *lpRectScr1* 의 교집합에 없는 *lpRectScr1* 하 고 *lpRectScr2*합니다.

지정 된 사각형 *lpRectSrc1* 변경할 수 없습니다 하 여 지정 된 사각형이 *lpRectSrc2* 지정 된 영역을 완전히 겹치지 *lpRectSrc1*이상의 x-또는 y-지시 합니다.

예를 들어 경우 *lpRectSrc1* 되었습니다 (10,10, 100100) 및 *lpRectSrc2* 되었습니다 (50,50, 150,150) 가리키는 사각형 *lpRectSrc1* 그대로는 함수를 반환 합니다. 그러나 하는 경우 *lpRectSrc1* 되었습니다 (10,10, 100100) 및 *lpRectSrc2* 되었습니다 (50,10, 150,150) 사각형 가리키는 *lpRectSrc1* (10,10, 좌표를 포함 하는 50,100) 함수에서 반환 하는 경우입니다.

`SubtractRect` 동일 아닙니다 [연산자](#operator_-) 도 [-= 연산자](#operator_-_eq)합니다. 이러한 연산자 하나도 적이 호출 `SubtractRect`합니다.

> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
   RECT   rectOne;
   RECT   rectTwo;

   rectOne.left = 10;
   rectOne.top = 10;
   rectOne.bottom = 100;
   rectOne.right = 100;

   rectTwo.left = 50;
   rectTwo.top = 10;
   rectTwo.bottom = 150;
   rectTwo.right = 150;

   CRect   rectDiff;

   rectDiff.SubtractRect(&rectOne, &rectTwo);
CRect   rectResult(10, 10, 50, 100);

   ASSERT(rectDiff == rectResult);

   // works for CRect, too, since there is
   // implicit CRect -> LPCRECT conversion

   CRect rect1(10, 10, 100, 100);
   CRect rect2(50, 10, 150, 150);
   CRect rectOut;

   rectOut.SubtractRect(rect1, rect2);
   ASSERT(rectResult == rectOut);
```

##  <a name="topleft"></a>  CRect::TopLeft

좌표에 대 한 참조로 반환 되는 [CPoint](cpoint-class.md) 개체에 포함 된 `CRect`합니다.

```
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw();
```

### <a name="return-value"></a>반환 값

사각형의 왼쪽 위 모퉁이의 좌표입니다.

### <a name="remarks"></a>설명

Get 또는 set 사각형의 왼쪽 위 모퉁이에이 함수를 사용할 수 있습니다. 대입 연산자의 좌 변에 있는이 함수를 사용 하 여 모퉁이 설정 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CRect::CenterPoint](#centerpoint)합니다.

##  <a name="unionrect"></a>  CRect::UnionRect

크기를 사용 하면 `CRect` 두 소스 사각형의 합집합 같음.

```
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```

### <a name="parameters"></a>매개 변수

*lpRect1*<br/>
가리키는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 또는 `CRect` 소스 사각형을 포함 하는 합니다.

*lpRect2*<br/>
가리키는 `RECT` 또는 `CRect` 소스 사각형을 포함 하는 합니다.

### <a name="return-value"></a>반환 값

합집합 비어 있지 않으면 0이 아닌 값 공용 구조체는 비어 있는 경우 0입니다.

### <a name="remarks"></a>설명

공용 구조체는 두 원본 사각형이 포함 된 가장 작은 사각형입니다.

Windows; 빈 사각형의 크기를 무시합니다. 없는 높이 또는 너비 없음에 사각형, 합니다.

> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3.UnionRect(&rect1, &rect2);
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);
```

##  <a name="width"></a>  CRect::Width

너비를 계산 `CRect` 값을 오른쪽에서 왼쪽된 값을 빼서 합니다.

```
int Width() const throw();
```

### <a name="return-value"></a>반환 값

너비 `CRect`합니다.

### <a name="remarks"></a>설명

너비는 음수일 수 있습니다.

> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 이 함수를 호출 하기 전에 사각형을 정규화 합니다.

### <a name="example"></a>예제

```cpp
   CRect rect(20, 30, 80, 70);
   int nWid = rect.Width();
   // nWid is now 60
   ASSERT(nWid == 60);
```

## <a name="see-also"></a>참고자료

[CPoint 클래스](cpoint-class.md)<br/>
[CSize 클래스](csize-class.md)<br/>
[RECT](/windows/desktop/api/windef/ns-windef-tagrect)
