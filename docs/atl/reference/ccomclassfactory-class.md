---
title: CComClassFactory 클래스
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
ms.openlocfilehash: 85ef287a905abc7b3151628c0f5dc29b9050b187
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246724"
---
# <a name="ccomclassfactory-class"></a>CComClassFactory 클래스

이 클래스에서 구현 된 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) 인터페이스입니다.

## <a name="syntax"></a>구문

```
class CComClassFactory
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComClassFactory::CreateInstance](#createinstance)|지정된 된 CLSID의 개체를 만듭니다.|
|[CComClassFactory::LockServer](#lockserver)|메모리의 클래스 팩터리를 잠급니다.|

## <a name="remarks"></a>설명

`CComClassFactory` 구현 된 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) 새 개체를 보다 신속 하 게 만들 수 있도록 메모리의 클래스 팩터리 잠금 수 있을 뿐만 아니라 특정 CLSID의 개체를 만드는 메서드를 포함 하는 인터페이스입니다. `IClassFactory` 시스템 레지스트리 및 CLSID에 할당 하는 등록 하는 모든 클래스에 대 한 구현 되어야 합니다.

ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로 포함 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)를 선언 하는 `CComClassFactory` 기본 클래스 팩터리로 합니다. 이 기본값을 재정의 하려면 중 하나를 지정 합니다 `DECLARE_CLASSFACTORY` *XXX* 클래스 정의에 매크로입니다. 예를 들어, 합니다 [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) 매크로 클래스 팩터리에 대 한 지정된 된 클래스를 사용 합니다.

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]

위의 클래스 정의 지정 하는 `CMyClassFactory` 개체의 기본 클래스 팩터리로 사용 됩니다. `CMyClassFactory` 파생 되어야 합니다 `CComClassFactory` 시키고 `CreateInstance`합니다.

ATL은 클래스 팩터리를 선언 하는 다른 세 가지 매크로 제공 합니다.

- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) 사용 하 여 [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), 라이선스를 통해 생성을 제어 합니다.

- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 사용 하 여 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)에 여러 아파트 개체를 만듭니다.

- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) 사용 하 여 [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), 단일을 생성 하는 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactory::CreateInstance

지정된 된 CLSID의 개체를 만들고이 개체에 대 한 인터페이스 포인터를 검색 합니다.

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

##  <a name="lockserver"></a>  CComClassFactory::LockServer

증가 하 고 호출 하 여 모듈 잠금 횟수를 감소 시킵니다 `_Module::Lock` 고 `_Module::Unlock`, 각각.

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>매개 변수

*fLock*<br/>
[in] TRUE 인 경우 잠금 수가 증가 하 고, 그렇지 않으면, 잠금 수가 감소 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

`_Module` 전역 인스턴스를 가리키며 [CComModule](../../atl/reference/ccommodule-class.md) 클래스에서 파생 된 또는 합니다.

호출 `LockServer` 클라이언트가 여러 개체를 신속 하 게 만들 수 있도록 클래스 팩터리를 점유 하는 데 사용 합니다.

## <a name="see-also"></a>참고자료

[CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
