---
title: COM 인터페이스 항목 매크로
ms.date: 03/28/2017
f1_keywords:
- atlcom/ATL::COM_INTERFACE_ENTRY
- atlcom/ATL::COM_INTERFACE_ENTRY_IID
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_BREAK
- atlcom/ATL::COM_INTERFACE_ENTRY_CACHED_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_CHAIN
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_NOINTERFACE
helpviewer_keywords:
- COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
ms.openlocfilehash: f8439e973c935108d645076bb7e2bfae7207e65d
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503338"
---
# <a name="cominterfaceentry-macros"></a>COM_INTERFACE_ENTRY 매크로

이러한 매크로를 쿼리하면 COM 맵을 개체의 인터페이스에서 액세스할 수 있도록 입력 `QueryInterface`합니다. COM 맵에 순서가 순서 인터페이스를 확인 하는 동안 일치 하는 IID `QueryInterface`합니다.

|||
|-|-|
|[COM_INTERFACE_ENTRY](#com_interface_entry)|COM 인터페이스 맵을에 인터페이스를 입력합니다.|
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|이 매크로 사용 하 여 상속의 두 분기를 구분 합니다.|
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|이 매크로 사용 하 여 COM 맵에 인터페이스를 입력 하 고 해당 IID를 지정 합니다.|
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|동일 [COM_INTERFACE_ENTRY2](#com_interface_entry2)을 제외 하 고 다른 IID를 지정할 수 있습니다.|
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|인터페이스에서 식별 하는 경우 *iid* 에 대 한 쿼리 `COM_INTERFACE_ENTRY_AGGREGATE` 전달 `punk`합니다.|
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)한다는 점을 제외 하는 쿼리를 전달 하면 모든 IID에 대 한 쿼리 *punk*합니다.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), 경우를 제외 하 고 *punk* 가 null 인 경우에서 설명 하는 집계를 자동으로 생성 합니다 *clsid*.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|동일 [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)한다는 점을 제외 하는 쿼리를 전달 하면 모든 IID에 대 한 쿼리 *punk*, 경우에 *punk* 가 null 인 경우 자동으로 만들기 에 설명 된 집계를 *clsid*합니다.|
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|프로그램이 호출 [DebugBreak](/windows/desktop/api/debugapi/nf-debugapi-debugbreak) 지정된 된 인터페이스에 대 한 쿼리 될 경우.|
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|모든 인스턴스에 대 한 인터페이스 관련 데이터를 저장합니다.|
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|분리 인터페이스를 노출합니다.|
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|처리 하는 COM 맵에이 항목에 도달할 때 기본 클래스의 COM 맵에 처리 합니다.|
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL의에 연결 하는 일반 메커니즘 `QueryInterface` 논리입니다.|
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|동일 [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)에 대 한 호출으로 인해 모든 IID에 대 한 쿼리는 점을 제외 하 고 *func*합니다.|
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|E_NOINTERFACE가 반환 하 고에 대 한 지정된 된 인터페이스를 쿼리하면 COM 맵을 처리를 종료 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="com_interface_entry"></a> COM_INTERFACE_ENTRY

COM 인터페이스 맵을에 인터페이스를 입력합니다.

### <a name="syntax"></a>구문

```
COM_INTERFACE_ENTRY( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 클래스 개체에서 직접 파생 인터페이스의 이름입니다.

### <a name="remarks"></a>설명

일반적으로 가장 자주 사용 하는 항목 형식입니다.

### <a name="example"></a>예제

```cpp
BEGIN_COM_MAP(CThisExample)
   COM_INTERFACE_ENTRY(IThisExample)
   COM_INTERFACE_ENTRY(IDispatch)
   COM_INTERFACE_ENTRY(ISupportErrorInfo)
END_COM_MAP()
```

### <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="com_interface_entry2"></a>  COM_INTERFACE_ENTRY2

이 매크로 사용 하 여 상속의 두 분기를 구분 합니다.

```
COM_INTERFACE_ENTRY2(x, x2)
```

### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 개체에서 노출 하려는 인터페이스의 이름입니다.

*x2*<br/>
[in] 상속 분기의 이름을 *x* 노출 됩니다.

### <a name="remarks"></a>설명

예를 들어 두 개의 이중 인터페이스에서 클래스 개체를 파생 하는 경우 노출 `IDispatch` COM_INTERFACE_ENTRY2 이후를 사용 하 여 `IDispatch` 인터페이스 중 하나에서 가져올 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]

##  <a name="com_interface_entry_iid"></a>  COM_INTERFACE_ENTRY_IID

이 매크로 사용 하 여 COM 맵에 인터페이스를 입력 하 고 해당 IID를 지정 합니다.

```
COM_INTERFACE_ENTRY_IID(iid, x)
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 노출 하는 인터페이스의 GUID입니다.

*x*<br/>
[in] 로 식별 되는 인터페이스와 해당 vtable 노출 될 클래스의 이름을 *iid*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]

##  <a name="com_interface_entry2_iid"></a>  COM_INTERFACE_ENTRY2_IID

동일 [COM_INTERFACE_ENTRY2](#com_interface_entry2)을 제외 하 고 다른 IID를 지정할 수 있습니다.

```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 인터페이스를 지정 하는 GUID입니다.

*x*<br/>
[in] 클래스 개체에서 직접 파생 되는 인터페이스의 이름입니다.

*x2*<br/>
[in] 클래스 개체에서 직접 파생 되는 두 번째 인터페이스의 이름입니다.

##  <a name="com_interface_entry_aggregate"></a>  COM_INTERFACE_ENTRY_AGGREGATE

인터페이스를 구분 *iid* COM_INTERFACE_ENTRY_AGGREGATE 전달에 대 한 쿼리 *punk*합니다.

```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 에 대 한 쿼리 인터페이스의 GUID입니다.

*punk*<br/>
[in] 이름을 `IUnknown` 포인터입니다.

### <a name="remarks"></a>설명

합니다 *punk* 매개 변수를 가리키도록 NULL 또는 집계의 내부 알 수 없는 경우에서 항목은 무시 됩니다 것으로 간주 됩니다. 일반적으로 `CoCreate` 집계에 `FinalConstruct`입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]

##  <a name="com_interface_entry_aggregate_blind"></a>  COM_INTERFACE_ENTRY_AGGREGATE_BLIND

동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)한다는 점을 제외 하는 쿼리를 전달 하면 모든 IID에 대 한 쿼리 *punk*합니다.

```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```

### <a name="parameters"></a>매개 변수

*punk*<br/>
[in] 이름을 `IUnknown` 포인터입니다.

### <a name="remarks"></a>설명

인터페이스 쿼리는 실패 하는 경우의 COM 맵에 처리가 계속 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]

##  <a name="com_interface_entry_autoaggregate"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE

동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), 경우를 제외 하 고 *punk* 가 null 인 경우에서 설명 하는 집계를 자동으로 생성 합니다 *clsid*.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 에 대 한 쿼리 인터페이스의 GUID입니다.

*punk*<br/>
[in] 이름을 `IUnknown` 포인터입니다. COM 맵에 포함 하는 클래스의 멤버 여야 합니다.

*clsid*<br/>
[in] 만들어지는 경우 집계의 식별자 *punk* NULL입니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]

##  <a name="com_interface_entry_autoaggregate_blind"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND

동일 [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)한다는 점을 제외 하는 쿼리를 전달 하면 모든 IID에 대 한 쿼리 *punk*, 경우에 *punk* 가 null 인 경우 자동으로 만들기 에 설명 된 집계를 *clsid*합니다.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```

### <a name="parameters"></a>매개 변수

*punk*<br/>
[in] 이름을 `IUnknown` 포인터입니다. COM 맵에 포함 하는 클래스의 멤버 여야 합니다.

*clsid*<br/>
[in] 만들어지는 경우 집계의 식별자 *punk* NULL입니다.

### <a name="remarks"></a>설명

인터페이스 쿼리는 실패 하는 경우의 COM 맵에 처리가 계속 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]

##  <a name="com_interface_entry_break"></a>  COM_INTERFACE_ENTRY_BREAK

프로그램이 호출 [DebugBreak](/windows/desktop/api/debugapi/nf-debugapi-debugbreak) 지정된 된 인터페이스에 대 한 쿼리 될 경우.

```
COM_INTERFACE_ENTRY_BREAK(x)
```

### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 인터페이스 식별자를 생성 하는 데 사용 하는 텍스트입니다.

### <a name="remarks"></a>설명

인터페이스 IID를 추가 하 여 만들어집니다 *x* 에 `IID_`입니다. 예를 들어 경우 *x* 됩니다 `IPersistStorage`, IID 됩니다 `IID_IPersistStorage`합니다.

##  <a name="com_interface_entry_cached_tear_off"></a>  COM_INTERFACE_ENTRY_CACHED_TEAR_OFF

모든 인스턴스에 대 한 인터페이스 관련 데이터를 저장합니다.

```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 분리 인터페이스의 GUID입니다.

*x*<br/>
[in] 인터페이스를 구현 하는 클래스의 이름입니다.

*punk*<br/>
[in] 이름을 `IUnknown` 포인터입니다. COM 맵에 포함 하는 클래스의 멤버 여야 합니다. 클래스 개체의 생성자에서 NULL로 초기화 되어야 합니다.

### <a name="remarks"></a>설명

인터페이스를 사용 하지 않는 경우이 개체의 전체 인스턴스 크기를 줄입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]

##  <a name="com_interface_entry_tear_off"></a>  COM_INTERFACE_ENTRY_TEAR_OFF

분리 인터페이스를 노출합니다.

```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 분리 인터페이스의 GUID입니다.

*x*<br/>
[in] 인터페이스를 구현 하는 클래스의 이름입니다.

### <a name="remarks"></a>설명

분리 인터페이스를 나타내는 인터페이스 때마다 인스턴스화되는 별도 개체를 쿼리 하는 대로 구현 됩니다. 일반적으로 인터페이스는 거의 사용 되므로이 주요 개체의 모든 인스턴스에 vtable 대 한 포인터를 저장 하는 경우는 분리로 인터페이스에 빌드합니다. 참조 횟수가 0 인 경우는 분리 삭제 됩니다. 분리 막대가 구현 하는 클래스에서 파생 되는 `CComTearOffObjectBase` 있고 고유한 COM 맵.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

##  <a name="com_interface_entry_chain"></a>  COM_INTERFACE_ENTRY_CHAIN

처리 하는 COM 맵에이 항목에 도달할 때 기본 클래스의 COM 맵에 처리 합니다.

```
COM_INTERFACE_ENTRY_CHAIN(classname)
```

### <a name="parameters"></a>매개 변수

*classname*<br/>
[in] 현재 개체의 기본 클래스입니다.

### <a name="remarks"></a>설명

예를 들어, 다음 코드에서

[!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]

COM에서 첫 번째 항목에 매핑하는 COM 맵이 포함 된 개체의 인터페이스 여야 합니다. 다른 지점에서 검색할 개체의 COM 맵에 COM_INTERFACE_ENTRY_CHAIN를 사용 하 여 COM 맵 항목을 시작할 수 없습니다 따라서 여기서 **COM_INTERFACE_ENTRY_CHAIN (** `COtherObject` **)** 개체의 COM 맵에 표시 됩니다. 다른 개체의 COM 맵에 먼저 검색 하려는 경우에 대 한 인터페이스 항목을 추가 합니다. `IUnknown` COM 맵에, 그런 다음 다른 개체의 COM 맵에 연결 합니다. 예를 들어:

[!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]

##  <a name="com_interface_entry_func"></a>  COM_INTERFACE_ENTRY_FUNC

ATL의에 연결 하는 일반 메커니즘 `QueryInterface` 논리입니다.

```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 노출 하는 인터페이스의 GUID입니다.

*dw*<br/>
[in] 매개 변수를 전달 합니다 *func*합니다.

*func*<br/>
[in] 반환 하는 함수 포인터 *iid*합니다.

### <a name="remarks"></a>설명

하는 경우 *iid* 에 지정 된 함수를 쿼리 하는 인터페이스의 IID와 일치 *func* 라고 합니다. 함수 선언 해야 합니다.

`HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`

함수를 호출 하면 `pv` 클래스 개체를 가리킵니다. 합니다 *riid* 매개 변수를 쿼리 하는 인터페이스를 참조 `ppv` 함수를 인터페이스에 대 한 포인터를 저장 해야 하는 위치에 대 한 포인터 및 *dw* 매개 변수 수 항목에 지정 합니다. 함수를 설정 해야 \* `ppv` NULL 반환 E_NOINTERFACE 또는 S_FALSE를 인터페이스를 반환 하지 않도록 선택 하는 경우. E_NOINTERFACE를 사용 하 여 COM 맵 처리를 종료합니다. S_FALSE를 사용 하 여 COM 맵 처리는 계속 인터페이스 포인터가 반환 된 경우에 합니다. 함수 인터페이스 포인터를 반환 하는 경우 s_ok이 고, 반환 됩니다.

##  <a name="com_interface_entry_func_blind"></a>  COM_INTERFACE_ENTRY_FUNC_BLIND

동일 [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)에 대 한 호출으로 인해 모든 IID에 대 한 쿼리는 점을 제외 하 고 *func*합니다.

```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```

### <a name="parameters"></a>매개 변수

*dw*<br/>
[in] 매개 변수를 전달 합니다 *func*합니다.

*func*<br/>
[in] 이 항목의 COM 맵에 처리 될 때 호출 되는 함수입니다.

### <a name="remarks"></a>설명

오류 처리를 COM 맵에 계속 발생 합니다. 함수 인터페이스 포인터를 반환 하는 경우 s_ok이 고, 반환 됩니다.

##  <a name="com_interface_entry_nointerface"></a>  COM_INTERFACE_ENTRY_NOINTERFACE

E_NOINTERFACE가 반환 하 고에 대 한 지정된 된 인터페이스를 쿼리하면 COM 맵을 처리를 종료 합니다.

```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```

### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 인터페이스 식별자를 생성 하는 데 사용 하는 텍스트입니다.

### <a name="remarks"></a>설명

특정 사례에서 사용 되는 인터페이스를 방지 하기 위해이 매크로 사용할 수 있습니다. 예를 들어 인터페이스에 대 한 쿼리를 알 수 없는 내부 집계의 전달 하지 못하도록 COM_INTERFACE_ENTRY_AGGREGATE_BLIND 직전에 COM 맵에이 매크로 삽입할 수 있습니다.

인터페이스 IID를 추가 하 여 만들어집니다 *x* 에 `IID_`입니다. 예를 들어 경우 *x* 됩니다 `IPersistStorage`, IID 됩니다 `IID_IPersistStorage`합니다.
