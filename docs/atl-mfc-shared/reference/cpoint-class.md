---
title: CPoint 클래스
ms.date: 11/04/2016
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
ms.openlocfilehash: 85e469e1f52a22917580ce8616aaba5ff57d08ed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252621"
---
# <a name="cpoint-class"></a>CPoint 클래스

Windows `POINT` 구조체와 유사합니다.

## <a name="syntax"></a>구문

```
class CPoint : public tagPOINT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CPoint::CPoint](#cpoint)|`CPoint`를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPoint::Offset](#offset)|에 값을 추가 합니다 `x` 및 `y` 의 멤버는 `CPoint`합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CPoint::operator -](#operator_-)|차를 반환을 `CPoint` 및 크기를 또는 지점 또는 두 지점 또는 음수 크기에 따라 오프셋 사이의 크기 차이의 부정입니다.|
|[CPoint::operator !=](#operator_neq)|두 점 사이의 같지 않은지 확인 합니다.|
|[CPoint::operator +](#operator_add)|합계를 반환 합니다는 `CPoint` 및 크기 또는 지점 또는 `CRect` 크기 만큼 오프셋 합니다.|
|[CPoint::operator + =](#operator_add_eq)|오프셋 `CPoint` 크기나 지점을 추가 하 여 합니다.|
|[CPoint::operator -=](#operator_-_eq)|오프셋 `CPoint` 크기 또는 포인트를 뺀 값으로.|
|[CPoint::operator ==](#operator_eq_eq)|두 점 사이의 같은지 확인 합니다.|

## <a name="remarks"></a>설명

또한 조작 하는 멤버 함수 `CPoint` 하 고 [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조입니다.

A `CPoint` 개체 수 아무 곳에 나 사용을 `POINT` 구조를 사용 합니다. 이 클래스의 "크기"를 사용 하 여 상호 작용 하는 연산자를 허용 하거나 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체 또는 [크기](/windows/desktop/api/windef/ns-windef-tagsize) 구조를 두는 서로 바꿔 사용할 수 있습니다.

> [!NOTE]
>  이 클래스에서 파생 되는 `tagPOINT` 구조입니다. (이름을 `tagPOINT` 자주 사용 되는 이름입니다는 `POINT` 구조입니다.) 즉, 데이터 멤버를 `POINT` 구조 `x` 및 `y`, 액세스할 수 있는 데이터 멤버는 `CPoint`합니다.

> [!NOTE]
>  공유 유틸리티 클래스에 대 한 자세한 (같은 `CPoint`)를 참조 하세요 [공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagPOINT`

`CPoint`

## <a name="requirements"></a>요구 사항

**헤더:** atltypes.h

##  <a name="cpoint"></a>  CPoint::CPoint

`CPoint` 개체를 생성합니다.

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>매개 변수

*initX*<br/>
`x`의 `CPoint` 멤버 값을 지정합니다.

*initY*<br/>
`y`의 `CPoint` 멤버 값을 지정합니다.

*initPt*<br/>
[지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 나 `CPoint` 초기화 하는 데 사용 하는 값을 지정 하는 `CPoint`합니다.

*initSize*<br/>
[크기](/windows/desktop/api/windef/ns-windef-tagsize) 구조 나 [CSize](../../atl-mfc-shared/reference/csize-class.md) 초기화 하는 데 사용 하는 값을 지정 하는 `CPoint`합니다.

*dwPoint*<br/>
집합의 `x` 멤버의 하위 단어를 *dwPoint* 하며 `y` 멤버의 상위 단어를 *dwPoint*합니다.

### <a name="remarks"></a>설명

인수가 지정되지 않으면 `x` 및 `y` 멤버가 0으로 설정됩니다.

### <a name="example"></a>예제

```cpp
CPoint   ptTopLeft(0, 0);
// works from a POINT, too

POINT   ptHere;
ptHere.x = 35;
ptHere.y = 95;

CPoint   ptMFCHere(ptHere);

// works from a SIZE
SIZE   sHowBig;
sHowBig.cx = 300;
sHowBig.cy = 10;

CPoint ptMFCBig(sHowBig);
// or from a DWORD

DWORD   dwSize;
dwSize = MAKELONG(35, 95);

CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```

##  <a name="offset"></a>  CPoint::Offset

에 값을 추가 합니다 `x` 및 `y` 의 멤버는 `CPoint`합니다.

```
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>매개 변수

*xOffset*<br/>
오프셋할 크기를 지정 합니다 `x` 의 멤버는 `CPoint`합니다.

*yOffset*<br/>
오프셋할 크기를 지정 합니다 `y` 의 멤버는 `CPoint`합니다.

*point*<br/>
크기를 지정 합니다 ( [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 또는 `CPoint`) 오프셋을 `CPoint`입니다.

*size*<br/>
크기를 지정 합니다 ( [크기](/windows/desktop/api/windef/ns-windef-tagsize) 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md)) 오프셋을 `CPoint`입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

##  <a name="operator_eq_eq"></a>  CPoint::operator ==

두 점 사이의 같은지 확인 합니다.

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
포함 된 [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 또는 `CPoint` 개체입니다.

### <a name="return-value"></a>반환 값

점을 같으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

##  <a name="operator_neq"></a>  CPoint::operator !=

두 점 사이의 같지 않은지 확인 합니다.

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
포함 된 [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 또는 `CPoint` 개체입니다.

### <a name="return-value"></a>반환 값

요소를 서로 같지 않으면 0이 아닌 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

##  <a name="operator_add_eq"></a>  CPoint::operator +=

크기를 추가 하는 첫 번째 오버 로드는 `CPoint`합니다.

```
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>매개 변수

*size*<br/>
포함 된 [크기](/windows/desktop/api/windef/ns-windef-tagsize) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.

*point*<br/>
포함 된 [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.

### <a name="remarks"></a>설명

에 점을 추가 하는 두 번째 오버 로드는 `CPoint`합니다.

두 경우 모두에서 추가 추가 하 여 수행 됩니다는 `x` (또는 `cx`)는 오른쪽 피연산자의 멤버는 `x` 의 멤버를 `CPoint` 추가 `y` (또는 `cy`)는 오른쪽 피연산자의 멤버를 `y` 의 멤버는 `CPoint`합니다.

예를 들어, 추가 `CPoint(5, -7)` 포함 된 변수로 `CPoint(30, 40)` 변수를 변경 `CPoint(35, 33)`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

##  <a name="operator_-_eq"></a>  CPoint::operator -=

첫 번째 오버 로드에서 크기를 뺍니다는 `CPoint`합니다.

```
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>매개 변수

*size*<br/>
포함 된 [크기](/windows/desktop/api/windef/ns-windef-tagsize) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.

*point*<br/>
포함 된 [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.

### <a name="remarks"></a>설명

두 번째 오버 로드를 빼는 지점은 `CPoint`합니다.

두 경우 모두에서 빼기를 빼는 방식으로 수행 됩니다는 `x` (또는 `cx`)에서 오른쪽 피연산자의 멤버는 `x` 의 멤버를 `CPoint` 을 빼는 방법 합니다 `y` (또는 `cy`) 오른쪽의 멤버 피연산자는 `y` 의 멤버는 `CPoint`합니다.

예를 들어 뺀 `CPoint(5, -7)` 포함 된 변수에서 `CPoint(30, 40)` 변수를 변경 `CPoint(25, 47)`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

##  <a name="operator_add"></a>  CPoint::operator +

이 연산자를 사용 하 여 오프셋 `CPoint` 하 여는 `CPoint` 또는 `CSize` 개체 또는 오프셋을 `CRect` 하 여를 `CPoint`합니다.

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>매개 변수

*size*<br/>
포함 된 [크기](/windows/desktop/api/windef/ns-windef-tagsize) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.

*point*<br/>
포함 된 [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.

*lpRect*<br/>
에 대 한 포인터를 포함 한 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

A `CPoint` 크기에서 오프셋 된를 `CPoint` 는 지점에서 오프셋 된 또는 `CRect` 지점에서 오프셋입니다.

### <a name="remarks"></a>설명

예를 들어,를 사용 하 여 처음 두 오버 로드 중 지정 된 점을 오프셋할 `CPoint(25, -19)` 지점으로 `CPoint(15, 5)` 크기나 `CSize(15, 5)` 값을 반환 합니다 `CPoint(40, -14)`합니다.

오프셋 되 후 사각형을 반환 지점으로 사각형을 추가 합니다 `x` 및 `y` 지점에서 지정 된 값입니다. 예를 들어 마지막 오버 로드를 사용 하 여 사각형을 오프셋할 `CRect(125, 219, 325, 419)` 지점 `CPoint(25, -19)` 반환 `CRect(150, 200, 350, 400)`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

##  <a name="operator_-"></a>  CPoint::operator -

뺄 처음 두 오버 로드 중 하나를 사용 하는 `CPoint` 또는 `CSize` 에서 개체 `CPoint`합니다.

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>매개 변수

*point*<br/>
A [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 구조 나 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.

*size*<br/>
A [크기](/windows/desktop/api/windef/ns-windef-tagsize) 구조 나 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.

*lpRect*<br/>
에 대 한 포인터를 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

A `CSize` 두 점 사이의 차이 나타내는 `CPoint` 크기의 부정 만큼 오프셋 된를 `CRect` 지점의 부정 만큼 오프셋 된 또는 `CPoint` 요소의 부정입니다.

### <a name="remarks"></a>설명

세 번째 오프셋 오버 로드는 `CRect` 의 부정 만큼 `CPoint`입니다. 마지막으로, 부정할 단항 연산자를 사용 하 여 `CPoint`입니다.

예를 들어, 첫 번째 오버 로드를 사용 하 여 두 점 사이의 차이 확인 하려면 `CPoint(25, -19)` 하 고 `CPoint(15, 5)` 반환 `CSize(10, -24)`합니다.

빼기를 `CSize` 에서 `CPoint` 위와 동일한 계산을 반환 하지만 `CPoint` 개체가 아니라는 `CSize` 개체. 예를 들어, 두 번째 오버 로드를 사용 하 여 지점 간의 차이점을 찾으려고 `CPoint(25, -19)` 및 크기 `CSize(15, 5)` 반환 `CPoint(10, -24)`합니다.

지점에서 사각형을 뺀의 부정 하 여 사각형 오프셋을 반환 합니다 `x` 및 `y` 지점에서 지정 된 값입니다. 예를 들어 마지막 오버 로드를 사용 하 여 사각형을 오프셋할 `CRect(125, 200, 325, 400)` 지점 `CPoint(25, -19)` 반환 `CRect(100, 219, 300, 419)`합니다.

지점 부정할 단항 연산자를 사용 합니다. 예를 들어, 단항 연산자를 사용 하 여 지점과 `CPoint(25, -19)` 반환 `CPoint(-25, 19)`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[POINT 구조체](/windows/desktop/api/windef/ns-windef-tagpoint)<br/>
[CRect 클래스](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CSize 클래스](../../atl-mfc-shared/reference/csize-class.md)
