---
title: CD2DGeometry 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::Attach
- AFXRENDERTARGET/CD2DGeometry::CombineWithGeometry
- AFXRENDERTARGET/CD2DGeometry::CompareWithGeometry
- AFXRENDERTARGET/CD2DGeometry::ComputeArea
- AFXRENDERTARGET/CD2DGeometry::ComputeLength
- AFXRENDERTARGET/CD2DGeometry::ComputePointAtLength
- AFXRENDERTARGET/CD2DGeometry::Destroy
- AFXRENDERTARGET/CD2DGeometry::Detach
- AFXRENDERTARGET/CD2DGeometry::FillContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Get
- AFXRENDERTARGET/CD2DGeometry::GetBounds
- AFXRENDERTARGET/CD2DGeometry::GetWidenedBounds
- AFXRENDERTARGET/CD2DGeometry::IsValid
- AFXRENDERTARGET/CD2DGeometry::Outline
- AFXRENDERTARGET/CD2DGeometry::Simplify
- AFXRENDERTARGET/CD2DGeometry::StrokeContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Tessellate
- AFXRENDERTARGET/CD2DGeometry::Widen
- AFXRENDERTARGET/CD2DGeometry::m_pGeometry
helpviewer_keywords:
- CD2DGeometry [MFC], CD2DGeometry
- CD2DGeometry [MFC], Attach
- CD2DGeometry [MFC], CombineWithGeometry
- CD2DGeometry [MFC], CompareWithGeometry
- CD2DGeometry [MFC], ComputeArea
- CD2DGeometry [MFC], ComputeLength
- CD2DGeometry [MFC], ComputePointAtLength
- CD2DGeometry [MFC], Destroy
- CD2DGeometry [MFC], Detach
- CD2DGeometry [MFC], FillContainsPoint
- CD2DGeometry [MFC], Get
- CD2DGeometry [MFC], GetBounds
- CD2DGeometry [MFC], GetWidenedBounds
- CD2DGeometry [MFC], IsValid
- CD2DGeometry [MFC], Outline
- CD2DGeometry [MFC], Simplify
- CD2DGeometry [MFC], StrokeContainsPoint
- CD2DGeometry [MFC], Tessellate
- CD2DGeometry [MFC], Widen
- CD2DGeometry [MFC], m_pGeometry
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
ms.openlocfilehash: 4549b2e7981d5f8493ddf9f24477e75a94ddde8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405731"
---
# <a name="cd2dgeometry-class"></a>CD2DGeometry 클래스

ID2D1Geometry에 대 한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DGeometry : public CD2DResource;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|CD2DGeometry 개체를 생성합니다.|
|[CD2DGeometry::~CD2DGeometry](#_dtorcd2dgeometry)|소멸자입니다. D2D 기 하 도형 개체가 소멸 될 때 호출 됩니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CD2DGeometry::Attach](#attach)|기존 개체에 대 한 리소스 인터페이스를 연결.|
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|지정한 기를 사용 하 여이 기 하이 도형을 결합 하 고 결과 ID2D1SimplifiedGeometrySink에 저장 합니다.|
|[CD2DGeometry::CompareWithGeometry](#comparewithgeometry)|이 기 하 도형과 지정한 기 하 도형의 교차를 설명 합니다. 지정 된 flattening 허용 오차를 사용 하 여 비교를 수행 합니다.|
|[CD2DGeometry::ComputeArea](#computearea)|였 기 하 도형의 면적을 계산 하 여 지정 된 매트릭스를 변환 하 고 지정 된 허용 오차를 사용 하 여 결합 합니다.|
|[CD2DGeometry::ComputeLength](#computelength)|가 각 세그먼트에는 롤백된 것 처럼 geometry의 길이 계산 합니다.|
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|였 기 하 도형에 따라 지정된 된 거리에 지점 및 탄젠트 벡터를 계산 하 여 지정 된 매트릭스를 변환 하 고 지정 된 허용 오차를 사용 하 여 결합 합니다.|
|[CD2DGeometry::Destroy](#destroy)|CD2DGeometry 개체를 제거합니다. (재정의 [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DGeometry::Detach](#detach)|개체에서 리소스 인터페이스를 분리합니다.|
|[CD2DGeometry::FillContainsPoint](#fillcontainspoint)|기 하 여 채운 영역 지정된 flattening 허용 오차를 지정 하는 지정된 된 지점에 포함 됩니다 있는지 여부를 나타냅니다.|
|[CD2DGeometry::Get](#get)|반환 ID2D1Geometry 인터페이스|
|[CD2DGeometry::GetBounds](#getbounds)||
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|지정한 스트로크 너비 및 스타일에 의해 확장 된 및 지정 된 행렬으로 변환 된 후에 기 하 도형의 경계를 가져옵니다.|
|[CD2DGeometry::IsValid](#isvalid)|리소스 유효성을 검사 (재정의 [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DGeometry::Outline](#outline)|기 하 도형의 윤곽선을 계산 하 고 결과 ID2D1SimplifiedGeometrySink를 작성 합니다.|
|[CD2DGeometry::Simplify](#simplify)|포함 선 및 (선택 사항) 입방 형 3 차원 곡선을 ID2D1SimplifiedGeometrySink를 결과 기록 하는 기 하 도형의 단순화 된 버전을 만듭니다.|
|[CD2DGeometry::StrokeContainsPoint](#strokecontainspoint)|기 하 도형의 스트로크에 지정한 스트로크 두께, 스타일 및 변환 주어진 지정된 된 점이 포함 되는지 여부를 결정 합니다.|
|[CD2DGeometry::Tessellate](#tessellate)|지정된 된 매트릭스를 사용 하 여 변환 된 기 하 도형을 포함 하 고 지정 된 허용 오차를 사용 하 여 평면화 하는 시계 방향으로 돌아가는 삼각형 집합을 만듭니다.|
|[CD2DGeometry::Widen](#widen)|기 하 도형을 지정에 따라 확장 하 고 받은 후 결과 ID2D1SimplifiedGeometrySink 쓸 지정된 행렬으로 변환 하 고 지정 된 허용 오차를 사용 하 여 결합 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CD2DGeometry::operator ID2D1Geometry *](#operator_id2d1geometry_star)|반환 ID2D1Geometry 인터페이스|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CD2DGeometry::m_pGeometry](#m_pgeometry)|ID2D1Geometry 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DGeometry`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

##  <a name="_dtorcd2dgeometry"></a>  CD2DGeometry::~CD2DGeometry

소멸자입니다. D2D 기 하 도형 개체가 소멸 될 때 호출 됩니다.

```
virtual ~CD2DGeometry();
```

##  <a name="attach"></a>  CD2DGeometry::Attach

기존 개체에 대 한 리소스 인터페이스를 연결.

```
void Attach(ID2D1Geometry* pResource);
```

### <a name="parameters"></a>매개 변수

*pResource*<br/>
기존 리소스 인터페이스입니다. NULL 일 수 없습니다.

##  <a name="cd2dgeometry"></a>  CD2DGeometry::CD2DGeometry

CD2DGeometry 개체를 생성합니다.

```
CD2DGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*pParentTarget*<br/>
렌더링 대상에 대 한 포인터입니다.

*bAutoDestroy*<br/>
개체 소유자 (pParentTarget)에 의해 소멸 되는 것을 나타냅니다.

##  <a name="combinewithgeometry"></a>  CD2DGeometry::CombineWithGeometry

지정한 기를 사용 하 여이 기 하이 도형을 결합 하 고 결과 ID2D1SimplifiedGeometrySink에 저장 합니다.

```
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,
    D2D1_COMBINE_MODE combineMode,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*inputGeometry*<br/>
이 인스턴스와 결합 기하학입니다.

*combineMode*<br/>
수행할 결합 작업의 형식입니다.

*inputGeometryTransform*<br/>
결합 하기 전의 inputGeometry에 적용할 변환입니다.

*geometrySink*<br/>
결합 작업의 결과입니다.

*flatteningTolerance*<br/>
기 하 도형의 다각형 근사에서 각 점 사이의 거리에 최대 범위입니다. 값이 작을수록 결과가 정확해 하지만 실행 속도 느려집니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="comparewithgeometry"></a>  CD2DGeometry::CompareWithGeometry

이 기 하 도형과 지정한 기 하 도형의 교차를 설명 합니다. 지정 된 flattening 허용 오차를 사용 하 여 비교를 수행 합니다.

```
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*inputGeometry*<br/>
테스트할 기 하 도형입니다.

*inputGeometryTransform*<br/>
InputGeometry에 적용할 변환입니다.

*flatteningTolerance*<br/>
기 하 도형의 다각형 근사에서 각 점 사이의 거리에 최대 범위입니다. 값이 작을수록 결과가 정확해 하지만 실행 속도 느려집니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="computearea"></a>  CD2DGeometry::ComputeArea

였 기 하 도형의 면적을 계산 하 여 지정 된 매트릭스를 변환 하 고 지정 된 허용 오차를 사용 하 여 결합 합니다.

```
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& area,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*worldTransform*<br/>
면적을 계산 하기 전에이 기 하이 도형에 적용할 변환입니다.

*area*<br/>
이 메서드는 반환 될 때이 기 하 도형의 결합된의 변환 된 버전의 영역에 대 한 포인터를 포함 합니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

*flatteningTolerance*<br/>
기 하 도형의 다각형 근사 점 사이의 거리에 최대 범위입니다. 값이 작을수록 결과가 정확해 하지만 실행 속도 느려집니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="computelength"></a>  CD2DGeometry::ComputeLength

가 각 세그먼트에는 롤백된 것 처럼 geometry의 길이 계산 합니다.

```
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& length,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*worldTransform*<br/>
해당 길이 계산 하기 전에 기 하 도형에 적용할 변환입니다.

*length*<br/>
이 메서드가 반환 하는 경우 기 하 도형의 길이에 대 한 포인터를 포함 합니다. 길이 닫힌된 기 하 도형에 대 한 암시적 닫는 세그먼트를 포함합니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

*flatteningTolerance*<br/>
기 하 도형의 다각형 근사 점 사이의 거리에 최대 범위입니다. 값이 작을수록 결과가 정확해 하지만 실행 속도 느려집니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="computepointatlength"></a>  CD2DGeometry::ComputePointAtLength

였 기 하 도형에 따라 지정된 된 거리에 지점 및 탄젠트 벡터를 계산 하 여 지정 된 매트릭스를 변환 하 고 지정 된 허용 오차를 사용 하 여 결합 합니다.

```
BOOL ComputePointAtLength(
    FLOAT length,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DPointF& point,
    CD2DPointF& unitTangentVector,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*length*<br/>
지점 및 찾을 탄젠트 기 하 도형 따라 거리입니다. 이 간격 0 미만인 경우이 메서드는 첫 번째 기 하 도형 지점을 계산 합니다. 이 거리는 geometry의 길이 보다 클 경우이 메서드는 마지막 기 하 도형 점을 계산 합니다.

*worldTransform*<br/>
지정 된 지점 및 탄젠트를 계산 하기 전에 기 하 도형에 적용할 변환입니다.

*point*<br/>
기 하 도형에 따라 지정 된 거리에 위치 합니다. 기 하 도형 비어 있는 경우이 여기서 포함 NaN x 및 y 값입니다.

*unitTangentVector*<br/>
이 메서드는 반환 될 때 탄젠트 벡터 기 하 도형에 따라 지정된 된 거리에 대 한 포인터를 포함 합니다. 기 하 도형 비어 있으면이 벡터 포함 NaN x 및 y 값입니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

*flatteningTolerance*<br/>
기 하 도형의 다각형 근사 점 사이의 거리에 최대 범위입니다. 값이 작을수록 결과가 정확해 하지만 실행 속도 느려집니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="destroy"></a>  CD2DGeometry::Destroy

CD2DGeometry 개체를 제거합니다.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DGeometry::Detach

개체에서 리소스 인터페이스를 분리합니다.

```
ID2D1Geometry* Detach();
```

### <a name="return-value"></a>반환 값

분리 된 리소스 인터페이스에 대 한 포인터입니다.

##  <a name="fillcontainspoint"></a>  CD2DGeometry::FillContainsPoint

기 하 여 채운 영역 지정된 flattening 허용 오차를 지정 하는 지정된 된 지점에 포함 됩니다 있는지 여부를 나타냅니다.

```
BOOL FillContainsPoint(
    CD2DPointF point,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*point*<br/>
테스트할 점입니다.

*worldTransform*<br/>
포함을 테스트 하기 전에 기 하 도형에 적용할 변환입니다.

*contains*<br/>
이 메서드는 반환 될 때이 TRUE 이면 기 하 여 채운 영역; 요소는 bool 값을 포함 합니다. 그렇지 않으면 FALSE입니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

*flatteningTolerance*<br/>
숫자 정확도는 정확 하 게 기하학적 경로 및 경로 교차 계산 됩니다. 채우기가 허용 오차 보다 작은 없는 지점 내에서 여전히 간주 됩니다. 값이 작을수록 결과가 정확해 하지만 실행 속도 느려집니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="get"></a>  CD2DGeometry::Get

반환 ID2D1Geometry 인터페이스

```
ID2D1Geometry* Get();
```

### <a name="return-value"></a>반환 값

ID2D1Geometry 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="getbounds"></a>  CD2DGeometry::GetBounds

```
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,
CD2DRectF& bounds) const;
```

### <a name="parameters"></a>매개 변수

*worldTransform*<br/>
*bounds*

### <a name="return-value"></a>반환 값

##  <a name="getwidenedbounds"></a>  CD2DGeometry::GetWidenedBounds

지정한 스트로크 너비 및 스타일에 의해 확장 된 및 지정 된 행렬으로 변환 된 후에 기 하 도형의 경계를 가져옵니다.

```
BOOL GetWidenedBounds(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DRectF& bounds,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*strokeWidth*<br/>
기 하 도형 윤곽선을 스트로크 하 여 확장에 사용 되는 양입니다.

*strokeStyle*<br/>
기 하 도형 확대 되는 선의 스타일입니다.

*worldTransform*<br/>
기 하 도형 변환 되 고 기 하 도형에 스트로크 후 기 하 도형에 적용할 변환입니다.

*bounds*<br/>
이 메서드는 반환 될 때 확장 된 기의 범위를 포함 합니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

*flatteningTolerance*<br/>
기 하 도형의 다각형 근사에서 각 점 사이의 거리에 최대 범위입니다. 값이 작을수록 결과가 정확해 하지만 실행 속도 느려집니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="isvalid"></a>  CD2DGeometry::IsValid

리소스 유효성 검사

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>반환 값

리소스 유효 하면 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="m_pgeometry"></a>  CD2DGeometry::m_pGeometry

ID2D1Geometry 포인터입니다.

```
ID2D1Geometry* m_pGeometry;
```

##  <a name="operator_id2d1geometry_star"></a>  CD2DGeometry::operator ID2D1Geometry*

반환 ID2D1Geometry 인터페이스

```
operator ID2D1Geometry*();
```

### <a name="return-value"></a>반환 값

ID2D1Geometry 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="outline"></a>  CD2DGeometry::Outline

기 하 도형의 윤곽선을 계산 하 고 결과 ID2D1SimplifiedGeometrySink를 작성 합니다.

```
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*worldTransform*<br/>
기 하 도형 윤곽선에 적용할 변환입니다.

*geometrySink*<br/>
기 하 도형 변환 개요 ID2D1SimplifiedGeometrySink 추가 됩니다.

*flatteningTolerance*<br/>
기 하 도형의 다각형 근사 점 사이의 거리에 최대 범위입니다. 값이 작을수록 결과가 정확해 하지만 실행 속도 느려집니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="simplify"></a>  CD2DGeometry::Simplify

포함 선 및 (선택 사항) 입방 형 3 차원 곡선을 ID2D1SimplifiedGeometrySink를 결과 기록 하는 기 하 도형의 단순화 된 버전을 만듭니다.

```
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*simplificationOption*<br/>
간소화 된 기 하 도형 곡선을 포함 해야 하는지 여부를 지정 하는 값입니다.

*worldTransform*<br/>
간소화 된 기 하 도형에 적용할 변환입니다.

*geometrySink*<br/>
ID2D1SimplifiedGeometrySink는 단순한 기 하 도형이 추가 됩니다.

*flatteningTolerance*<br/>
기 하 도형의 다각형 근사 점 사이의 거리에 최대 범위입니다. 값이 작을수록 결과가 정확해 하지만 실행 속도 느려집니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="strokecontainspoint"></a>  CD2DGeometry::StrokeContainsPoint

기 하 도형의 스트로크에 지정한 스트로크 두께, 스타일 및 변환 주어진 지정된 된 점이 포함 되는지 여부를 결정 합니다.

```
BOOL StrokeContainsPoint(
    CD2DPointF point,
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*point*<br/>
포함 여부를 테스트할 점입니다.

*strokeWidth*<br/>
적용할 스트로크의 두께입니다.

*strokeStyle*<br/>
적용할 선의 스타일입니다.

*worldTransform*<br/>
스트로크 기 하 도형에 적용할 변환입니다.

*contains*<br/>
이 메서드가 반환 하는 경우 기 하 도형의 스트로크에 지정된 된 지점이 포함 된 경우 TRUE로 설정 하는 부울 값을 포함 합니다. 그렇지 않으면 FALSE입니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

*flatteningTolerance*<br/>
숫자 정확도는 정확 하 게 기하학적 경로 및 경로 교차 계산 됩니다. 허용 오차 보다 작은 스트로크가 없는 지점 내에서 여전히 간주 됩니다. 값이 작을수록 결과가 정확해 하지만 실행 속도 느려집니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="tessellate"></a>  CD2DGeometry::Tessellate

지정된 된 매트릭스를 사용 하 여 변환 된 기 하 도형을 포함 하 고 지정 된 허용 오차를 사용 하 여 평면화 하는 시계 방향으로 돌아가는 삼각형 집합을 만듭니다.

```
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1TessellationSink* tessellationSink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*worldTransform*<br/>
이 기 하 도형 또는 NULL로 적용할 변환입니다.

*tessellationSink*<br/>
ID2D1TessellationSink는 없을 추가 됩니다.

*flatteningTolerance*<br/>
기 하 도형의 다각형 근사 점 사이의 거리에 최대 범위입니다. 값이 작을수록 결과가 정확해 하지만 실행 속도 느려집니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

##  <a name="widen"></a>  CD2DGeometry::Widen

기 하 도형을 지정에 따라 확장 하 고 받은 후 결과 ID2D1SimplifiedGeometrySink 쓸 지정된 행렬으로 변환 하 고 지정 된 허용 오차를 사용 하 여 결합 합니다.

```
BOOL Widen(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>매개 변수

*strokeWidth*<br/>
기 하 도형 확대 변환에 사용 되는 양입니다.

*strokeStyle*<br/>
기 하 도형 또는 NULL로 적용할 선의 스타일입니다.

*worldTransform*<br/>
이 클래스는 확대 후 기 하 도형에 적용할 변환입니다.

*geometrySink*<br/>
ID2D1SimplifiedGeometrySink는 확장 된 기 추가 됩니다.

*flatteningTolerance*<br/>
기 하 도형의 다각형 근사 점 사이의 거리에 최대 범위입니다. 값이 작을수록 결과가 정확해 하지만 실행 속도 느려집니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
