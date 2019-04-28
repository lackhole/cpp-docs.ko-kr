---
title: CConnectionPoint 클래스
ms.date: 11/04/2016
f1_keywords:
- CConnectionPoint
- AFXDISP/CConnectionPoint
- AFXDISP/CConnectionPoint::CConnectionPoint
- AFXDISP/CConnectionPoint::GetConnections
- AFXDISP/CConnectionPoint::GetContainer
- AFXDISP/CConnectionPoint::GetIID
- AFXDISP/CConnectionPoint::GetMaxConnections
- AFXDISP/CConnectionPoint::GetNextConnection
- AFXDISP/CConnectionPoint::GetStartPosition
- AFXDISP/CConnectionPoint::OnAdvise
- AFXDISP/CConnectionPoint::QuerySinkInterface
helpviewer_keywords:
- CConnectionPoint [MFC], CConnectionPoint
- CConnectionPoint [MFC], GetConnections
- CConnectionPoint [MFC], GetContainer
- CConnectionPoint [MFC], GetIID
- CConnectionPoint [MFC], GetMaxConnections
- CConnectionPoint [MFC], GetNextConnection
- CConnectionPoint [MFC], GetStartPosition
- CConnectionPoint [MFC], OnAdvise
- CConnectionPoint [MFC], QuerySinkInterface
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
ms.openlocfilehash: a75ce23cf55f26505c2584c3a021b654602a6a2b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182282"
---
# <a name="cconnectionpoint-class"></a>CConnectionPoint 클래스

"연결점"이라고 하는 다른 OLE 개체와 통신하는 데 사용하는 특별한 형식의 인터페이스를 정의합니다.

## <a name="syntax"></a>구문

```
class CConnectionPoint : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|`CConnectionPoint` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CConnectionPoint::GetConnections](#getconnections)|연결 맵의 연결 지점이 모두 검색합니다.|
|[CConnectionPoint::GetContainer](#getcontainer)|연결 맵을 소유 하는 컨트롤의 컨테이너를 검색 합니다.|
|[CConnectionPoint::GetIID](#getiid)|연결 지점의 인터페이스 ID를 검색합니다.|
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|컨트롤에서 지 원하는 연결 포인트의 최대 수를 검색 합니다.|
|[CConnectionPoint::GetNextConnection](#getnextconnection)|에 있는 연결 요소에 대 한 포인터를 검색 *pos*합니다.|
|[CConnectionPoint::GetStartPosition](#getstartposition)|맵 반복을 전달할 수 있는 위치 값을 반환 하 여 시작을 `GetNextConnection` 호출 합니다.|
|[CConnectionPoint::OnAdvise](#onadvise)|설정 하거나 연결을 중단 하는 경우 프레임 워크에서 호출 됩니다.|
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|요청 된 싱크 인터페이스에 대 한 포인터를 검색합니다.|

## <a name="remarks"></a>설명

일반 OLE 인터페이스를 구현 하 고 OLE 컨트롤의 기능을 노출 하는 달리 연결 지점 이벤트를 발생 시키고 같은 다른 개체에 대 한 작업을 시작 하 고 변경 알림을 수 있는 송신 인터페이스를 구현 합니다.

연결을 두 부분으로 구성 됩니다: "원본" 및 인터페이스를 구현 하는 개체를 호출 하는 인터페이스를 호출 하는 개체 "sink" 라는 연결 지점에서 노출 하 여 원본 자체에 대 한 연결을 설정 하는 싱크를 허용 합니다. 연결 지점 메커니즘을 통해 원본 개체는 멤버 함수 집합이 싱크 구현에 대 한 포인터를 가져옵니다. 예를 들어, 싱크에 의해 구현 된 이벤트를 발생 원본 싱크 구현의 적절 한 메서드를 호출할 수 있습니다.

기본적으로 `COleControl`-파생된 클래스에서 두 개의 연결 지점 구현: 이벤트에 대 한 하나 및 속성에 대 한 변경 알림. 이 연결을 사용, 각각 이벤트 발생 한 경우 (예를 들어, 컨트롤의 컨테이너) 싱크를 알리기 위한 속성 값이 변경 합니다. 추가 연결 지점을 구현할 OLE 컨트롤에 대 한 지원이 제공 됩니다. 컨트롤 클래스에서 구현 된 각 추가 연결 지점에 대해 "연결" 하는 파트를 연결 지점을 구현 선언 해야 합니다. 하나 이상의 연결점을 구현 하는 경우 단일 컨트롤 클래스의 "연결 맵을"를 선언 해야 하는 합니다.

다음 예제에서는 간단한 연결 맵 및에 대 한 연결 지점을 `Sample` OLE 컨트롤을 두 가지 코드 조각으로 이루어진: 첫 번째 부분은 선언 지점과 연결 맵을;이 맵과 지점 두 번째 구현 합니다. 첫 번째 조각에서 컨트롤 클래스 선언의에 삽입 되는 **보호** 섹션:

[!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]

BEGIN_CONNECTION_PART 및 END_CONNECTION_PART 매크로 포함 된 클래스를 선언 `XSampleConnPt` (에서 파생 된 `CConnectionPoint`)이 특정 연결 지점 구현 합니다. 재정의 하려는 경우 `CConnectionPoint` 멤버 함수 또는 자신만의 멤버 함수를 추가, 이러한 두 매크로 선언 합니다. 예를 들어 CONNECTION_IID 매크로 재정의 `CConnectionPoint::GetIID` 이러한 두 매크로 사이 배치 하는 경우 멤버 함수입니다.

두 번째 코드 조각 구현 파일에 삽입 됩니다 (합니다. CPP) 컨트롤 클래스입니다. 이 코드 구현 연결점 추가 포함 하는 연결 맵을 `SampleConnPt`:

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]

샘플 OLE 컨트롤에 대 한 연결 지점을 노출 코드 조각은 삽입 후의 `ISampleSink` 인터페이스입니다.

일반적으로 연결점 "멀티" 같은 인터페이스에 연결 하는 여러 싱크를 브로드캐스트하는 기능을 지원 합니다. 다음 코드 조각에는 연결 지점에서 각 싱크를 반복 하 여 멀티 캐스팅을 수행 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

이 예제에서 연결의 현재 집합을 검색 합니다 `SampleConnPt` 연결점에 대 한 호출을 사용 하 여 `CConnectionPoint::GetConnections`입니다. 다음 연결 및 호출을 반복 `ISampleSink::SinkFunc` 모든 활성 연결.

사용 하 여 대 한 자세한 내용은 `CConnectionPoint`, 문서를 참조 하세요 [연결점](../../mfc/connection-points.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CConnectionPoint`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

##  <a name="cconnectionpoint"></a>  CConnectionPoint::CConnectionPoint

`CConnectionPoint` 개체를 생성합니다.

```
CConnectionPoint();
```

##  <a name="getconnections"></a>  CConnectionPoint::GetConnections

연결 지점에 대 한 모든 활성 연결을 검색 하려면이 함수를 호출 합니다.

```
const CPtrArray* GetConnections();
```

### <a name="return-value"></a>반환 값

활성 연결 (싱크)의 배열에 대 한 포인터입니다. 배열에서 포인터의 일부는 NULL 일 수 있습니다. 이 배열의 각 NULL이 아닌 포인터 캐스트 연산자를 사용 하 여 싱크 인터페이스에 대 한 포인터를 안전 하 게 변환할 수 있습니다.

##  <a name="getcontainer"></a>  CConnectionPoint::GetContainer

검색 하기 위해 프레임 워크에서 호출 된 `IConnectionPointContainer` 연결점에 대 한 합니다.

```
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```

### <a name="return-value"></a>반환 값

성공 하면 컨테이너;에 대 한 포인터 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 BEGIN_CONNECTION_PART 매크로로 구현 됩니다.

##  <a name="getiid"></a>  CConnectionPoint::GetIID

연결 지점의 인터페이스 ID를 검색 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual REFIID GetIID() = 0;
```

### <a name="return-value"></a>반환 값

연결 지점의 인터페이스 id입니다.에 대 한 참조

### <a name="remarks"></a>설명

이 연결점에 대 한 인터페이스 ID를 반환 하려면이 함수를 재정의 합니다.

##  <a name="getmaxconnections"></a>  CConnectionPoint::GetMaxConnections

연결 지점에서 지원 되는 연결의 최대 개수를 검색 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual int GetMaxConnections();
```

### <a name="return-value"></a>반환 값

경우 제한이 컨트롤 또는-1에서 지원 되는 연결의 최대 수입니다.

### <a name="remarks"></a>설명

기본 구현은 제한이 없음을 나타내는-1을 반환 합니다.

컨트롤에 연결할 수 있는 싱크의 수를 제한 하려는 경우이 함수를 재정의 합니다.

##  <a name="getnextconnection"></a>  CConnectionPoint::GetNextConnection

에 있는 연결 요소에 대 한 포인터를 검색 *pos*합니다.

```
LPUNKNOWN GetNextConnection(POSITION& pos) const;
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
이전 반환한 위치 값에 대 한 참조를 지정 `GetNextConnection` 나 [GetStartPosition](#getstartposition) 호출 합니다.

### <a name="return-value"></a>반환 값

지정 하는 연결 요소에 대 한 포인터 *pos*, 또는 NULL입니다.

### <a name="remarks"></a>설명

이 함수는 연결 map의 모든 요소를 반복 하는 데 가장 유용 합니다. 을 반복 하는 경우이 함수에서 반환 된 모든 null 값을 건너뜁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

##  <a name="getstartposition"></a>  CConnectionPoint::GetStartPosition

맵 반복을 전달할 수 있는 위치 값을 반환 하 여 시작 된 [GetNextConnection](#getnextconnection) 호출 합니다.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>반환 값

가 맵을 반복 시작 위치를 지정 하는 위치 값 또는 맵이 비어 있으면 NULL입니다.

### <a name="remarks"></a>설명

반복 시퀀스 예측 가능한; 아닙니다. 따라서 "첫 번째 요소를 맵" 특별 한 의미가 없습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CConnectionPoint::GetNextConnection](#getnextconnection)합니다.

##  <a name="onadvise"></a>  CConnectionPoint::OnAdvise

연결이 설정 되거나 끊어지면가 연결 될 때 프레임 워크에서 호출 합니다.

```
virtual void OnAdvise(BOOL bAdvise);
```

### <a name="parameters"></a>매개 변수

*bAdvise*<br/>
연결 중인; 경우 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행하지 않습니다.

싱크를 연결 하거나 연결 지점에서 연결을 끊을 때 알림을 원하는 경우이 함수를 재정의 합니다.

##  <a name="querysinkinterface"></a>  CConnectionPoint::QuerySinkInterface

요청 된 싱크 인터페이스에 대 한 포인터를 검색합니다.

```
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,
    void** ppInterface);
```

### <a name="parameters"></a>매개 변수

*pUnkSink*<br/>
요청 되는 싱크 인터페이스의 식별자입니다.

*ppInterface*<br/>
로 식별 되는 인터페이스 포인터에 대 한 포인터 *pUnkSink*합니다. 개체는이 인터페이스를 지원 하지 않는 경우 \* *ppInterface* NULL로 설정 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

## <a name="see-also"></a>참고자료

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
