---
title: 집계 및 클래스 팩터리 매크로
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_AGGREGATABLE
- atlcom/ATL::DECLARE_CLASSFACTORY
- atlcom/ATL::DECLARE_CLASSFACTORY_EX
- atlcom/ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- atlcom/ATL::DECLARE_CLASSFACTORY_SINGLETON
- atlcom/ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- atlcom/ATL::DECLARE_NOT_AGGREGATABLE
- atlcom/ATL::DECLARE_ONLY_AGGREGATABLE
- atlcom/ATL::DECLARE_POLY_AGGREGATABLE
- atlcom/ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- atlcom/ATL::DECLARE_VIEW_STATUS
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
ms.openlocfilehash: 889ed4bbfc21209a64cfd9e4fee4b2335ce62010
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62249075"
---
# <a name="aggregation-and-class-factory-macros"></a>집계 및 클래스 팩터리 매크로

이러한 매크로의 집계를 제어 하 고 클래스 팩터리를 선언 하는 방법을 제공 합니다.

|||
|-|-|
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|개체 수 있음을 선언 (기본값)를 집계 합니다.|
|[DECLARE_CLASSFACTORY](#declare_classfactory)|선언 되도록 클래스 팩터리 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), ATL 기본 클래스 팩터리입니다.|
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|클래스 팩터리를 클래스 팩터리 개체를 선언 합니다.|
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|선언 [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) 클래스 팩터리 되도록 합니다.|
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|선언 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리 되도록 합니다.|
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|선언 [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) 클래스 팩터리 되도록 합니다.|
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|가상 선언 `GetControllingUnknown` 함수입니다.|
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|개체를 집계할 수 없는 선언 합니다.|
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|개체를 집계 해야 합니다는 선언 합니다.|
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|알 수 없는 외부의 값을 확인 하 고 집계할 수 또는 집계할 수 없는, 해당 개체를 선언 합니다.|
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|외부 개체는 내부 개체를 생성 하는 동안 삭제 되지 않도록 보호합니다.|
|[DECLARE_VIEW_STATUS](#declare_view_status)|컨테이너에 VIEWSTATUS 플래그를 지정합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="declare_aggregatable"></a>  DECLARE_AGGREGATABLE

개체를 집계할 수 있도록 지정 합니다.

```
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 집계할 수로 정의 하는 클래스의 이름입니다.

### <a name="remarks"></a>설명

[CComCoClass](../../atl/reference/ccomcoclass-class.md) 기본 집계 모델을 지정 하려면이 매크로 포함 합니다. 이 기본값을 재정의 하려면 하나를 지정 합니다 [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) 또는 [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) 클래스 정의에 매크로입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

##  <a name="declare_classfactory"></a>  DECLARE_CLASSFACTORY

선언 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 클래스 팩터리 되도록 합니다.

```
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>설명

[CComCoClass](../../atl/reference/ccomcoclass-class.md) 이 매크로 사용 하 여 개체에 대 한 기본 클래스 팩터리를 선언 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

##  <a name="ccomclassfactory_class"></a>  CComClassFactory 클래스

이 클래스에서 구현 된 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) 인터페이스입니다.

```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>설명

`CComClassFactory` 구현 된 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) 새 개체를 보다 신속 하 게 만들 수 있도록 메모리의 클래스 팩터리 잠금 수 있을 뿐만 아니라 특정 CLSID의 개체를 만드는 메서드를 포함 하는 인터페이스입니다. `IClassFactory` 시스템 레지스트리 및 CLSID에 할당 하는 등록 하는 모든 클래스에 대 한 구현 되어야 합니다.

ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로 포함 [DECLARE_CLASSFACTORY](#declare_classfactory)를 선언 하는 `CComClassFactory` 기본 클래스 팩터리로 합니다. 이 기본값을 재정의 하 여 DECLARE_CLASSFACTORY 중 하나를 지정*XXX* 클래스 정의에 매크로입니다. 예를 들어, 합니다 [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) 매크로 클래스 팩터리에 대 한 지정된 된 클래스를 사용 합니다.

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

위의 클래스 정의 지정 하는 `CMyClassFactory` 개체의 기본 클래스 팩터리로 사용 됩니다. `CMyClassFactory` 파생 되어야 합니다 `CComClassFactory` 시키고 `CreateInstance`합니다.

ATL은 클래스 팩터리를 선언 하는 다른 세 가지 매크로 제공 합니다.

- [DECLARE_CLASSFACTORY2](#declare_classfactory2) 사용 하 여 [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), 라이선스를 통해 생성을 제어 합니다.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) 사용 하 여 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)에 여러 아파트 개체를 만듭니다.

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) 사용 하 여 [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), 단일을 생성 하는 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 개체입니다.

##  <a name="declare_classfactory_ex"></a>  DECLARE_CLASSFACTORY_EX

선언 `cf` 클래스 팩터리 되도록 합니다.

```
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>매개 변수

*cf*<br/>
[in] 클래스 팩터리 개체를 구현 하는 클래스의 이름입니다.

### <a name="remarks"></a>설명

합니다 *cf* 매개 변수에서 파생 되어야 합니다 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 재정의 `CreateInstance` 메서드.

[CComCoClass](../../atl/reference/ccomcoclass-class.md) 포함 된 [DECLARE_CLASSFACTORY](#declare_classfactory) 매크로 지정 하는 `CComClassFactory` 기본 클래스 팩터리로 합니다. 그러나 개체의 클래스 정의에 DECLARE_CLASSFACTORY_EX 매크로 넣어이 기본값을 재정의할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

##  <a name="declare_classfactory2"></a>  DECLARE_CLASSFACTORY2

선언 [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) 클래스 팩터리 되도록 합니다.

```
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>매개 변수

*lic*<br/>
[in] 구현 하는 클래스 `VerifyLicenseKey`하십시오 `GetLicenseKey`, 및 `IsLicenseValid`합니다.

### <a name="remarks"></a>설명

[CComCoClass](../../atl/reference/ccomcoclass-class.md) 포함 된 [DECLARE_CLASSFACTORY](#declare_classfactory) 지정는 매크로 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 그러나 개체의 클래스 정의에 DECLARE_CLASSFACTORY2 매크로 넣어이 기본값을 재정의할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

##  <a name="ccomclassfactory2_class"></a>  CComClassFactory2 클래스

이 클래스에서 구현 된 [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) 인터페이스입니다.

```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

### <a name="parameters"></a>매개 변수

*license*<br/>
다음 정적 함수를 구현 하는 클래스:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

### <a name="remarks"></a>설명

`CComClassFactory2` 구현 된 [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) 인터페이스를 확장의 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)합니다. `IClassFactory2` 라이선스를 통해 개체 생성을 제어 합니다. 사용이 허가 된 컴퓨터에서 클래스 팩터리 실행 런타임 라이선스 키를 제공할 수 있습니다. 이 라이선스 키 개체를 인스턴스화하는 전체 컴퓨터 라이선스가 없는 경우 응용 프로그램을 수 있습니다.

ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로 포함 [DECLARE_CLASSFACTORY](#declare_classfactory)를 선언 하는 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 사용 하 `CComClassFactory2`를 지정 합니다 [DECLARE_CLASSFACTORY2](#declare_classfactory2) 개체의 클래스 정의에 매크로입니다. 예를 들어:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`를 템플릿 매개 변수를 `CComClassFactory2`, 정적 함수를 구현 해야 합니다 `VerifyLicenseKey`를 `GetLicenseKey`, 및 `IsLicenseValid`합니다. 다음은 간단한 라이선스 클래스의 예입니다.

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2` 둘 다에서 파생 `CComClassFactory2Base` 하 고 *라이선스*합니다. `CComClassFactory2Base`에서 파생 `IClassFactory2` 하 고 **CComObjectRootEx\< CComGlobalsThreadModel >** 합니다.

##  <a name="declare_classfactory_auto_thread"></a>  DECLARE_CLASSFACTORY_AUTO_THREAD

선언 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리 되도록 합니다.

```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>설명

[CComCoClass](../../atl/reference/ccomcoclass-class.md) 포함 된 [DECLARE_CLASSFACTORY](#declare_classfactory) 지정는 매크로 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 그러나 개체의 클래스 정의에 DECLARE_CLASSFACTORY_AUTO_THREAD 매크로 넣어이 기본값을 재정의할 수 있습니다.

(-의-out-proc 서버)에서 여러 아파트에서 개체를 만들 때 DECLARE_CLASSFACTORY_AUTO_THREAD 클래스에 추가 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

##  <a name="ccomclassfactoryautothread_class"></a>  CComClassFactoryAutoThread 클래스

이 클래스에서 구현 된 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) 인터페이스 및 개체를 여러 아파트에서 만들 수 있습니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>설명

`CComClassFactoryAutoThread` 비슷합니다 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), 개체를 여러 아파트에서 만들 수 있습니다. 이 지원을 활용 하려면에서 EXE 모듈을 파생 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)합니다.

ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로 포함 [DECLARE_CLASSFACTORY](#declare_classfactory)를 선언 하는 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 사용 하 `CComClassFactoryAutoThread`를 지정 합니다 [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) 개체의 클래스 정의에 매크로입니다. 예를 들어:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

##  <a name="declare_classfactory_singleton"></a>  DECLARE_CLASSFACTORY_SINGLETON

선언 [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) 클래스 팩터리 되도록 합니다.

```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>매개 변수

*obj*<br/>
[in] 클래스 개체의 이름입니다.

### <a name="remarks"></a>설명

[CComCoClass](../../atl/reference/ccomcoclass-class.md) 포함 된 [DECLARE_CLASSFACTORY](#declare_classfactory) 지정는 매크로 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 그러나 개체의 클래스 정의에 DECLARE_CLASSFACTORY_SINGLETON 매크로 넣어이 기본값을 재정의할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

##  <a name="ccomclassfactorysingleton_class"></a>  CComClassFactorySingleton 클래스

이 클래스에서 파생 됩니다 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 사용 하 여 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 단일 개체를 생성 하 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>매개 변수

*T*<br/>
클래스입니다.

`CComClassFactorySingleton` 파생 되 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 사용 하 여 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 단일 개체를 생성 합니다. 각 호출에는 `CreateInstance` 메서드는 단순히이 개체에 대 한 인터페이스 포인터를 쿼리 합니다.

### <a name="remarks"></a>설명

ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로 포함 [DECLARE_CLASSFACTORY](#declare_classfactory)를 선언 하는 `CComClassFactory` 기본 클래스 팩터리로 합니다. 사용 하 `CComClassFactorySingleton`를 지정 합니다 [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) 개체의 클래스 정의에 매크로입니다. 예를 들어:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

##  <a name="declare_get_controlling_unknown"></a>  DECLARE_GET_CONTROLLING_UNKNOWN

가상 함수 선언 `GetControllingUnknown`합니다.

```
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>설명

컴파일러 오류 메시지가 표시 하는 경우 개체에이 매크로 추가 `GetControllingUnknown` 정의 되지 않습니다 (예를 들어 `CComAggregateCreator`).

##  <a name="declare_not_aggregatable"></a>  DECLARE_NOT_AGGREGATABLE

개체를 집계할 수 없습니다 지정 합니다.

```
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 집계할 수 없는 것으로 정의 하는 클래스 개체의 이름입니다.

### <a name="remarks"></a>설명

DECLARE_NOT_AGGREGATABLE 하면 `CreateInstance` 하려고 시도 하는 경우 (CLASS_E_NOAGGREGATION) 오류를 반환할 개체에 대 한 집계를 합니다.

기본적으로 [CComCoClass](../../atl/reference/ccomcoclass-class.md) 포함 된 [DECLARE_AGGREGATABLE](#declare_aggregatable) 개체를 집계할 수 있도록 지정는 매크로입니다. 이 기본 동작을 재정의 하려면 DECLARE_NOT_AGGREGATABLE 클래스 정의에 포함 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

##  <a name="declare_only_aggregatable"></a>  DECLARE_ONLY_AGGREGATABLE

개체를 집계할 수 해야 지정 합니다.

```
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 만 집계할 수로 정의 하는 클래스 개체의 이름입니다.

### <a name="remarks"></a>설명

DECLARE_ONLY_AGGREGATABLE 하려고 시도 하는 경우 (E_FAIL) 오류를 생성 `CoCreate` 집계 개체와 개체입니다.

기본적으로 [CComCoClass](../../atl/reference/ccomcoclass-class.md) 포함 된 [DECLARE_AGGREGATABLE](#declare_aggregatable) 개체를 집계할 수 있도록 지정는 매크로입니다. 이 기본 동작을 재정의 하려면 DECLARE_ONLY_AGGREGATABLE 클래스 정의에 포함 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

##  <a name="declare_poly_aggregatable"></a>  DECLARE_POLY_AGGREGATABLE

지정 하는 인스턴스의 **CComPolyObject \<**  *x* **>** 개체를 만들 때 만들어집니다.

```
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 집계할 수 또는 집계할 수 없는 정의 하는 클래스 개체의 이름입니다.

### <a name="remarks"></a>설명

를 만드는 동안 알 수 없는 외부의 값이 확인 됩니다. 이 NULL 이면 `IUnknown` 집계 개체에 대 한 구현 됩니다. 알 수 없는 외부, NULL이 아닌 경우 `IUnknown` 집계 개체에 대해 구현 됩니다.

DECLARE_POLY_AGGREGATABLE를 사용 하 여의 장점은 둘 다를 것을 방지 하는 것 `CComAggObject` 고 `CComObject` 집계 및 집계 경우를 처리 하 여 모듈에서. 단일 `CComPolyObject` 두 경우를 처리 하는 개체입니다. 즉, 모듈에서 vtable의 복사본이 하나만 및 함수의 복사본 하나 존재 합니다. Vtable 큰 경우 현재 모듈 크기가 상당히 줄어들 수 있습니다이 합니다. Vtable이 작은 경우 사용 하는 반면 `CComPolyObject` 집계 또는 집계 개체에 대해 최적화 되어 있지 않으므로 약간 더 큰 모듈 크기를 발생할 수 있습니다는 `CComAggObject` 및 `CComObject`합니다.

ATL 컨트롤 마법사를 사용 하 여 전체 컨트롤을 만드는 DECLARE_POLY_AGGREGATABLE 매크로 개체에 자동으로 선언 됩니다.

##  <a name="declare_protect_final_construct"></a>  DECLARE_PROTECT_FINAL_CONSTRUCT

개체를 삭제할 경우 보호 (하는 동안 [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) 내부 집계 개체 수를 증가 시킵니다 참조 횟수를 감소 시킵니다 0입니다.

```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

##  <a name="declare_view_status"></a>  DECLARE_VIEW_STATUS

컨테이너에 VIEWSTATUS 플래그를 지정 하는 ATL ActiveX 컨트롤의 컨트롤 클래스에서이 매크로 배치 합니다.

```
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>매개 변수

*statusFlags*<br/>
[in] VIEWSTATUS 플래그입니다. 참조 [VIEWSTATUS](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus) 플래그의 목록은 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)
