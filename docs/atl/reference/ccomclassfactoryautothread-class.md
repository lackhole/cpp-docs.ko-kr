---
title: CComClassFactoryAutoThread 클래스
ms.date: 11/04/2016
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
ms.openlocfilehash: 473e697dfb0203b52713fcfb359ec4f56138f560
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246462"
---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread 클래스

이 클래스에서 구현 된 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) 인터페이스 및 개체를 여러 아파트에서 만들 수 있습니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CComClassFactoryAutoThread
    : public IClassFactory,
      public CComObjectRootEx<CComGlobalsThreadModel>
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|지정된 된 CLSID의 개체를 만듭니다.|
|[CComClassFactoryAutoThread::LockServer](#lockserver)|메모리의 클래스 팩터리를 잠급니다.|

## <a name="remarks"></a>설명

`CComClassFactoryAutoThread` 비슷합니다 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), 개체를 여러 아파트에서 만들 수 있습니다. 이 지원을 활용 하려면에서 EXE 모듈을 파생 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)합니다.

ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로 포함 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)를 선언 하는 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 사용 하 `CComClassFactoryAutoThread`를 지정 합니다 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 개체의 클래스 정의에 매크로입니다. 예를 들어:

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

`CComClassFactoryAutoThread`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactoryAutoThread::CreateInstance

지정된 된 CLSID의 개체를 만들고이 개체에 대 한 인터페이스 포인터를 검색 합니다.

```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
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

### <a name="remarks"></a>설명

모듈에서 파생 되는 경우 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), `CreateInstance` 먼저 개체를 만드는 연결된 아파트에 스레드를 선택 합니다.

##  <a name="lockserver"></a>  CComClassFactoryAutoThread::LockServer

증가 하 고 호출 하 여 모듈 잠금 횟수를 감소 시킵니다 `_Module::Lock` 고 `_Module::Unlock`, 각각.

```
STDMETHODIMP LockServer(BOOL fLock);
```

### <a name="parameters"></a>매개 변수

*fLock*<br/>
[in] TRUE 인 경우 잠금 수가 증가 하 고, 그렇지 않으면, 잠금 수가 감소 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

사용 하는 경우 `CComClassFactoryAutoThread`하십시오 `_Module` 의 전역 인스턴스는 일반적으로 가리킵니다 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)합니다.

호출 `LockServer` 클라이언트가 여러 개체를 신속 하 게 생성할 수 있도록 클래스 팩터리를 점유 하는 데 사용 합니다.

## <a name="see-also"></a>참고자료

[IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2 클래스](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactorySingleton 클래스](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
