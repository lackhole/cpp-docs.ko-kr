---
title: CComClassFactorySingleton 클래스
ms.date: 11/04/2016
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
ms.openlocfilehash: 480b4c2a6e052e8e0823b97b548fc5d07b55230f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260177"
---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton 클래스

이 클래스에서 파생 됩니다 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 사용 하 여 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 단일 개체를 생성 하 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스입니다.

`CComClassFactorySingleton` 파생 되 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 사용 하 여 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 단일 개체를 생성 합니다. 각 호출에는 `CreateInstance` 메서드는 단순히이 개체에 대 한 인터페이스 포인터를 쿼리 합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComClassFactorySingleton::CreateInstance](#createinstance)|쿼리 `m_spObj` 인터페이스 포인터에 대 한 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CComClassFactorySingleton::m_spObj](#m_spobj)|합니다 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 하 여 생성 된 개체 `CComClassFactorySingleton`합니다.|

## <a name="remarks"></a>설명

ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로 포함 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)를 선언 하는 `CComClassFactory` 기본 클래스 팩터리로 합니다. 사용 하 `CComClassFactorySingleton`를 지정 합니다 [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) 개체의 클래스 정의에 매크로입니다. 예를 들어:

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)

`CComClassFactorySingleton`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactorySingleton::CreateInstance

호출 `QueryInterface` 를 통해 [m_spObj](#m_spobj) 는 인터페이스 포인터를 검색 합니다.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>매개 변수

*pUnkOuter*<br/>
[in] 개체를 만드는 경우 집계의 일부로 다음 *pUnkOuter* 알 수 없는 외부 이어야 합니다. 그렇지 않으면 *pUnkOuter* NULL 이어야 합니다.

*riid*<br/>
[in] 요청된 된 인터페이스의 IID입니다. 하는 경우 *pUnkOuter* 가 NULL이 아닌 *riid* 있어야 `IID_IUnknown`합니다.

*ppvObj*<br/>
[out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 *riid*합니다. 개체는이 인터페이스를 지원 하지 않는 경우 *ppvObj* NULL로 설정 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="m_spobj"></a>  CComClassFactorySingleton::m_spObj

합니다 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 하 여 생성 된 개체 `CComClassFactorySingleton`합니다.

```
CComPtr<IUnknown> m_spObj;
```

### <a name="remarks"></a>설명

각 호출에는 [CreateInstance](#createinstance) 메서드는 단순히이 개체에 대 한 인터페이스 포인터를 쿼리 합니다.

현재 형태로 `m_spObj` 주요 변경 내용 방식에서 제공 하는 `CComClassFactorySingleton` ATL.의 이전 버전에서 작동 이전 버전에서의 `CComClassFactorySingleton` 클래스 팩터리로 동시에 서버를 초기화 하는 동안 개체를 만든 합니다. 시각적 개체의 C++.NET 2003에서는 개체가 만들어진 느리게 첫 번째 요청 시. 이 변경에는 초기 초기화를 사용 하는 프로그램에서 오류가 발생할 수 있습니다.

## <a name="see-also"></a>참고자료

[IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2 클래스](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactoryAutoThread 클래스](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
