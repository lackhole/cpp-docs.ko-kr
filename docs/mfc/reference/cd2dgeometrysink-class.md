---
title: CD2DGeometrySink 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::AddArc
- AFXRENDERTARGET/CD2DGeometrySink::AddBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddBeziers
- AFXRENDERTARGET/CD2DGeometrySink::AddLine
- AFXRENDERTARGET/CD2DGeometrySink::AddLines
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBeziers
- AFXRENDERTARGET/CD2DGeometrySink::BeginFigure
- AFXRENDERTARGET/CD2DGeometrySink::Close
- AFXRENDERTARGET/CD2DGeometrySink::EndFigure
- AFXRENDERTARGET/CD2DGeometrySink::Get
- AFXRENDERTARGET/CD2DGeometrySink::IsValid
- AFXRENDERTARGET/CD2DGeometrySink::SetFillMode
- AFXRENDERTARGET/CD2DGeometrySink::SetSegmentFlags
- AFXRENDERTARGET/CD2DGeometrySink::m_pSink
helpviewer_keywords:
- CD2DGeometrySink [MFC], CD2DGeometrySink
- CD2DGeometrySink [MFC], AddArc
- CD2DGeometrySink [MFC], AddBezier
- CD2DGeometrySink [MFC], AddBeziers
- CD2DGeometrySink [MFC], AddLine
- CD2DGeometrySink [MFC], AddLines
- CD2DGeometrySink [MFC], AddQuadraticBezier
- CD2DGeometrySink [MFC], AddQuadraticBeziers
- CD2DGeometrySink [MFC], BeginFigure
- CD2DGeometrySink [MFC], Close
- CD2DGeometrySink [MFC], EndFigure
- CD2DGeometrySink [MFC], Get
- CD2DGeometrySink [MFC], IsValid
- CD2DGeometrySink [MFC], SetFillMode
- CD2DGeometrySink [MFC], SetSegmentFlags
- CD2DGeometrySink [MFC], m_pSink
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
ms.openlocfilehash: 48c88f0b837b2e49e4c87f07a9aa28c16a66c1e3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391259"
---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink 클래스

ID2D1GeometrySink에 대 한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DGeometrySink;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|CD2DPathGeometry 개체에서 CD2DGeometrySink 개체를 생성합니다.|
|[CD2DGeometrySink::~CD2DGeometrySink](#_dtorcd2dgeometrysink)|소멸자입니다. D2D geometry 싱크 개체가 소멸 될 때 호출 됩니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CD2DGeometrySink::AddArc](#addarc)|경로 기 하 도형에 단일 arc 추가|
|[CD2DGeometrySink::AddBezier](#addbezier)|현재 점과 지정된 끝점 간에 입방형 3차원 곡선을 만듭니다.|
|[CD2DGeometrySink::AddBeziers](#addbeziers)|입방 형 3 차원 곡선 시퀀스로 만들고 기 하 도형 싱크로 추가 합니다.|
|[CD2DGeometrySink::AddLine](#addline)|현재 점과 지정 된 끝점 간에 직선 세그먼트를 만들고 기 하 도형 싱크로 추가 합니다.|
|[CD2DGeometrySink::AddLines](#addlines)|일련의 지정된 된 요소를 사용 하 여 선 만들고 기 하 도형 싱크로 추가 합니다.|
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|현재 점과 지정된 끝점 간에 정방형 3차원 곡선을 만듭니다.|
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|단일 호출에서 배열로 정방형 3 차원 곡선 세그먼트의 시퀀스를 추가 합니다.|
|[CD2DGeometrySink::BeginFigure](#beginfigure)|지정된 된 지점에 새 그림을 시작 합니다.|
|[CD2DGeometrySink::Close](#close)|기 하 도형 싱크를 닫습니다.|
|[CD2DGeometrySink::EndFigure](#endfigure)|현재 그림; 종료 필요에 따라이 닫습니다.|
|[CD2DGeometrySink::Get](#get)|반환 ID2D1GeometrySink 인터페이스|
|[CD2DGeometrySink::IsValid](#isvalid)|기 하 도형 싱크 유효성을 검사|
|[CD2DGeometrySink::SetFillMode](#setfillmode)|어떤 지를 결정 사항은이 기 하 도형 싱크에서 설명 하는 기 하 도형 내에서 외부 요소는 데 사용할 메서드를 지정 합니다.|
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|기 하 도형 싱크로 추가 된 새 세그먼트에 적용할 스트로크 및 조인 옵션을 지정 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CD2DGeometrySink::operator ID2D1GeometrySink*](#operator_id2d1geometrysink_star)|반환 ID2D1GeometrySink 인터페이스|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CD2DGeometrySink::m_pSink](#m_psink)|ID2D1GeometrySink 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CD2DGeometrySink`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

##  <a name="_dtorcd2dgeometrysink"></a>  CD2DGeometrySink::~CD2DGeometrySink

소멸자입니다. D2D geometry 싱크 개체가 소멸 될 때 호출 됩니다.

```
virtual ~CD2DGeometrySink();
```

##  <a name="addarc"></a>  CD2DGeometrySink::AddArc

경로 기 하 도형에 단일 arc 추가

```
void AddArc(const D2D1_ARC_SEGMENT& arc);
```

### <a name="parameters"></a>매개 변수

*arc*<br/>
원호 세그먼트를 그림 추가입니다.

##  <a name="addbezier"></a>  CD2DGeometrySink::AddBezier

현재 점과 지정된 끝점 간에 입방형 3차원 곡선을 만듭니다.

```
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>매개 변수

*bezier*<br/>
제어점과 추가할 베 지 어 곡선의 끝점을 설명 하는 구조체입니다.

##  <a name="addbeziers"></a>  CD2DGeometrySink::AddBeziers

입방 형 3 차원 곡선 시퀀스로 만들고 기 하 도형 싱크로 추가 합니다.

```
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,
    D2D1_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>매개 변수

*beziers*<br/>
만들려는 베 지 어 곡선을 설명 하는 3 차원 곡선 세그먼트의 배열입니다. 곡선을 기 하 도형 싱크의 현재 지점 (BeginFigure로 지정 된 위치 또는 마지막으로 그린 세그먼트의 끝점)에서 배열에 첫 번째 베 지 어 세그먼트의 끝점으로 그려집니다. 추가 3 차원 곡선 세그먼트를 포함 하는 경우 각 후속 베 지 어 세그먼트는 시작 지점으로 위의 3 차원 곡선 세그먼트의 끝점을 사용 합니다.

##  <a name="addline"></a>  CD2DGeometrySink::AddLine

현재 점과 지정 된 끝점 간에 직선 세그먼트를 만들고 기 하 도형 싱크로 추가 합니다.

```
void AddLine(CD2DPointF point);
```

### <a name="parameters"></a>매개 변수

*point*<br/>
그릴 선의 끝점입니다.

##  <a name="addlines"></a>  CD2DGeometrySink::AddLines

일련의 지정된 된 요소를 사용 하 여 선 만들고 기 하 도형 싱크로 추가 합니다.

```
void AddLines(
    const CArray<CD2DPointF,
    CD2DPointF>& points);
```

### <a name="parameters"></a>매개 변수

*points*<br/>
그릴 선을 설명 하는 하나 이상의 지점 배열입니다. 배열에서 첫 번째 요소에 기 하 도형 싱크의 현재 지점 (BeginFigure로 지정 된 위치 또는 마지막으로 그린 세그먼트의 끝점)에서 선이 그려집니다. 배열에 요소가 추가 하 고 세 번째 데이터 요소, 두 번째 지점에서 배열의 두 번째 지점에 첫 번째 요소에서 선이 그려집니다. 배열 그릴 선의 시작점과 끝점의 시퀀스입니다.

##  <a name="addquadraticbezier"></a>  CD2DGeometrySink::AddQuadraticBezier

현재 점과 지정된 끝점 간에 정방형 3차원 곡선을 만듭니다.

```
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>매개 변수

*bezier*<br/>
제어점 및 추가할 정방형 베 지 어 곡선의 끝점을 설명 하는 구조체입니다.

##  <a name="addquadraticbeziers"></a>  CD2DGeometrySink::AddQuadraticBeziers

단일 호출에서 배열로 정방형 3 차원 곡선 세그먼트의 시퀀스를 추가 합니다.

```
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>매개 변수

*beziers*<br/>
배열 정방형 3 차원 곡선 세그먼트의 시퀀스입니다.

##  <a name="beginfigure"></a>  CD2DGeometrySink::BeginFigure

지정된 된 지점에 새 그림을 시작 합니다.

```
void BeginFigure(
    CD2DPointF startPoint,
    D2D1_FIGURE_BEGIN figureBegin);
```

### <a name="parameters"></a>매개 변수

*startPoint*<br/>
새 그림을 시작 하는 지점입니다.

*figureBegin*<br/>
여부 속이 빈 또는 채워진 새 그림 이어야 합니다.

##  <a name="cd2dgeometrysink"></a>  CD2DGeometrySink::CD2DGeometrySink

CD2DPathGeometry 개체에서 CD2DGeometrySink 개체를 생성합니다.

```
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```

### <a name="parameters"></a>매개 변수

*pathGeometry*<br/>
기존 CD2DPathGeometry 개체입니다.

##  <a name="close"></a>  CD2DGeometrySink::Close

기 하 도형 싱크를 닫습니다.

```
BOOL Close();
```

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 그렇지 않으면 FALSE입니다.

##  <a name="endfigure"></a>  CD2DGeometrySink::EndFigure

현재 그림; 종료 필요에 따라이 닫습니다.

```
void EndFigure(D2D1_FIGURE_END figureEnd);
```

### <a name="parameters"></a>매개 변수

*figureEnd*<br/>
현재 그림 닫혀 있는지 여부를 나타내는 값입니다. 그림 닫혀 있는 경우 현재 지점 사이의 BeginFigure로 지정 된 시작점 선이 그려집니다.

##  <a name="get"></a>  CD2DGeometrySink::Get

반환 ID2D1GeometrySink 인터페이스

```
ID2D1GeometrySink* Get();
```

### <a name="return-value"></a>반환 값

ID2D1GeometrySink 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="isvalid"></a>  CD2DGeometrySink::IsValid

기 하 도형 싱크 유효성을 검사

```
BOOL IsValid() const;
```

### <a name="return-value"></a>반환 값

기 하 도형 싱크; 유효한 경우 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="m_psink"></a>  CD2DGeometrySink::m_pSink

ID2D1GeometrySink 포인터입니다.

```
ID2D1GeometrySink* m_pSink;
```

##  <a name="operator_id2d1geometrysink_star"></a>  CD2DGeometrySink::operator ID2D1GeometrySink*

반환 ID2D1GeometrySink 인터페이스

```
operator ID2D1GeometrySink*();
```

### <a name="return-value"></a>반환 값

ID2D1GeometrySink 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="setfillmode"></a>  CD2DGeometrySink::SetFillMode

어떤 지를 결정 사항은이 기 하 도형 싱크에서 설명 하는 기 하 도형 내에서 외부 요소는 데 사용할 메서드를 지정 합니다.

```
void SetFillMode(D2D1_FILL_MODE fillMode);
```

### <a name="parameters"></a>매개 변수

*fillMode*<br/>
지정 된 기 하 도형의 일부 인지 여부를 확인 하는 데 사용 된 메서드.

##  <a name="setsegmentflags"></a>  CD2DGeometrySink::SetSegmentFlags

기 하 도형 싱크로 추가 된 새 세그먼트에 적용할 스트로크 및 조인 옵션을 지정 합니다.

```
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```

### <a name="parameters"></a>매개 변수

*vertexFlags*<br/>
기 하 도형에 추가 된 새 세그먼트에 적용할 스트로크 및 조인 옵션 싱크입니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
