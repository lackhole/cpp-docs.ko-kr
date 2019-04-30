---
title: 서비스 맵 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
ms.openlocfilehash: ab130b2401dc9885f82fd5668a2d722a96dd289b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274566"
---
# <a name="service-map-macros"></a>서비스 맵 매크로

이러한 매크로 서비스 맵 및 항목을 정의 합니다.

|||
|-|-|
|[BEGIN_SERVICE_MAP](#begin_service_map)|ATL 서비스 맵의 시작을 표시 합니다.|
|[END_SERVICE_MAP](#end_service_map)|ATL 서비스 맵의 끝을 표시 합니다.|
|[SERVICE_ENTRY](#service_entry)|개체는 특정 서비스 ID를 지원함을 나타냅니다.|
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|지시 [IServiceProviderImpl::QueryService](#queryservice) 지정 된 개체는 체인으로 연결 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="begin_service_map"></a>  BEGIN_SERVICE_MAP

서비스 맵의 시작을 표시 합니다.

```
BEGIN_SERVICE_MAP(theClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
[in] 서비스 맵을 포함 하는 클래스를 지정 합니다.

### <a name="remarks"></a>설명

서비스 맵을 사용 하 여 COM 개체에서 서비스 공급자 기능을 구현 합니다. 클래스를 파생 해야 하는 먼저 [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)합니다. 항목에는 다음과 같은 두 종류가 있습니다.

- [SERVICE_ENTRY](#service_entry) ID (SID)를 지정 된 서비스에 대 한 지원을 나타냅니다.

- [SERVICE_ENTRY_CHAIN](#service_entry_chain) 하도록 [IServiceProviderImpl::QueryService](#queryservice) 다른 지정 된 개체에 대 한 체인을 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]

##  <a name="end_service_map"></a>  END_SERVICE_MAP

서비스 맵의 끝을 표시 합니다.

```
END_SERVICE_MAP()
```

### <a name="example"></a>예제

예를 참조 하세요 [BEGIN_SERVICE_MAP](#begin_service_map)합니다.

##  <a name="service_entry"></a>  SERVICE_ENTRY

개체에서 지정 된 서비스 id를 지원함을 나타냅니다 *SID*합니다.

```
SERVICE_ENTRY( SID )
```

### <a name="parameters"></a>매개 변수

*SID*<br/>
서비스 id입니다.

### <a name="example"></a>예제

예를 참조 하세요 [BEGIN_SERVICE_MAP](#begin_service_map)합니다.

##  <a name="service_entry_chain"></a>  SERVICE_ENTRY_CHAIN

지시 [IServiceProviderImpl::QueryService](#queryservice) 에서 지정한 개체에 연결할 *punk*합니다.

```
SERVICE_ENTRY_CHAIN( punk )
```

### <a name="parameters"></a>매개 변수

*punk*<br/>
에 대 한 포인터를 **IUnknown** 체인에는 인터페이스입니다.

### <a name="example"></a>예제

예를 참조 하세요 [BEGIN_SERVICE_MAP](#begin_service_map)합니다.

##  <a name="queryservice"></a>  IServiceProviderImpl::QueryService

만듭니다 또는 지정된 된 서비스에 액세스 하 고 지정된 된 인터페이스는 서비스에 대 한 인터페이스 포인터를 반환 합니다.

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*guidService*<br/>
[in] 서비스 식별자 (SID)에 대 한 포인터입니다.

*riid*<br/>
[in] 호출자가 액세스할 인터페이스의 식별자입니다.

*ppvObj*<br/>
[out] 요청된 된 인터페이스에 대 한 간접 포인터입니다.

### <a name="return-value"></a>반환 값

반환 된 HRESULT 값을 다음 중 하나입니다.

|반환 값|의미|
|------------------|-------------|
|S_OK|성공적으로 서비스를 만들거나 검색 됩니다.|
|E_INVALIDARG|하나 이상의 인수가 잘못된 경우|
|E_OUTOFMEMORY|서비스를 만들 충분 한 메모리가 없습니다.|
|E_UNEXPECTED|알 수 없는 오류가 발생했습니다.|
|E_NOINTERFACE|요청된 된 인터페이스가이 서비스의 일부가 아니거나 서비스 알 수 없는 합니다.|

### <a name="remarks"></a>설명

`QueryService` 지정된 된 서비스에서 요청된 된 인터페이스에 대 한 간접 포인터를 반환합니다. 호출자에 게는 더 이상 필요한 경우이 포인터를 해제 하는 일을 담당 합니다.

호출 하는 경우 `QueryService`을 두는 서비스 id를 전달 하면 (*guidService*) 및 인터페이스 식별자 (*riid*). *guidService* 액세스 하려는 서비스를 지정 하며 *riid* 서비스의 일부인 인터페이스를 식별 합니다. 반환 시 인터페이스에 대 한 간접 포인터를 받게 됩니다.

인터페이스를 구현 하는 개체는 다른 서비스의 일부인 인터페이스를 구현할 수도 있습니다. 다음을 살펴보세요.

- 이러한 인터페이스의 일부 선택 사항이 될 수 있습니다. 서비스 설명에 정의 된 모든 인터페이스 반환 된 모든 개체 또는 서비스의 모든 구현에서 반드시 변수가 있습니다.

- 에 대 한 호출 달리 `QueryInterface`, 다양 한 서비스 식별자를 전달 해도 반드시 다른 구성 요소 개체 모델 (COM) 개체를 반환 됩니다.

- 반환된 된 개체에는 서비스 정의의 일부분이 아닌 추가 인터페이스 있을 수 있습니다.

SID_SMyService SID_SYourService, 등 두 개의 서비스에 둘 다 지정할 수 동일한 인터페이스를 사용 하지만 인터페이스 구현의 두 서비스 간에 공통 전혀 없을 수 있습니다. 이 작동 하기 때문에 대 한 호출 `QueryService` (SID_SMyService, IID_IDispatch)는 다른 개체를 반환할 수 있습니다 `QueryService` (SID_SYourService, IID_IDispatch). 개체 id는 다양 한 서비스 식별자를 지정 하는 경우에 간주 되지 않습니다.

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)
