---
title: CComClassFactory2 클래스
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
ms.openlocfilehash: b3b14fa59765aa72a1142e0eef41aa84abea35de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259692"
---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2 클래스

이 클래스에서 구현 된 [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) 인터페이스입니다.

## <a name="syntax"></a>구문

```
template <class license>
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

#### <a name="parameters"></a>매개 변수

*license*<br/>
다음 정적 함수를 구현 하는 클래스:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComClassFactory2::CreateInstance](#createinstance)|지정된 된 CLSID의 개체를 만듭니다.|
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|라이선스 키를 지정 된 지정된 된 CLSID의 개체를 만듭니다.|
|[CComClassFactory2::GetLicInfo](#getlicinfo)|클래스 팩터리의 라이선스 기능을 설명 하는 정보를 검색 합니다.|
|[CComClassFactory2::LockServer](#lockserver)|메모리의 클래스 팩터리를 잠급니다.|
|[CComClassFactory2::RequestLicKey](#requestlickey)|만들고 라이선스 키를 반환 합니다.|

## <a name="remarks"></a>설명

`CComClassFactory2` 구현 된 [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) 인터페이스를 확장의 [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory)합니다. `IClassFactory2` 라이선스를 통해 개체 생성을 제어 합니다. 사용이 허가 된 컴퓨터에서 클래스 팩터리 실행 런타임 라이선스 키를 제공할 수 있습니다. 이 라이선스 키 개체를 인스턴스화하는 전체 컴퓨터 라이선스가 없는 경우 응용 프로그램을 수 있습니다.

ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로 포함 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)를 선언 하는 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 사용 하 `CComClassFactory2`를 지정 합니다 [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) 개체의 클래스 정의에 매크로입니다. 예를 들어:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]

`CMyLicense`를 템플릿 매개 변수를 `CComClassFactory2`, 정적 함수를 구현 해야 합니다 `VerifyLicenseKey`를 `GetLicenseKey`, 및 `IsLicenseValid`합니다. 다음은 간단한 라이선스 클래스의 예입니다.

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]

`CComClassFactory2` 둘 다에서 파생 `CComClassFactory2Base` 하 고 *라이선스*합니다. `CComClassFactory2Base`에서 파생 차례로 `IClassFactory2` 및 `CComObjectRootEx< CComGlobalsThreadModel >`합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

`license`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory2`

`CComClassFactory2`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="createinstance"></a>  CComClassFactory2::CreateInstance

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

### <a name="remarks"></a>설명

완벽 하 게 사용 허가 받아야 하는 컴퓨터에 필요 합니다. 전체 컴퓨터 라이선스 존재 하지 않는 경우 호출 [CreateInstanceLic](#createinstancelic)합니다.

##  <a name="createinstancelic"></a>  CComClassFactory2::CreateInstanceLic

비슷합니다 [CreateInstance](#createinstance)점을 제외 하 고 `CreateInstanceLic` 라이선스 키가 필요 합니다.

```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
*/,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*pUnkOuter*<br/>
[in] 개체를 만드는 경우 집계의 일부로 다음 *pUnkOuter* 알 수 없는 외부 이어야 합니다. 그렇지 않으면 *pUnkOuter* NULL 이어야 합니다.

*pUnkReserved*<br/>
[in] 사용 되지 않습니다. Null이어야 합니다.

*riid*<br/>
[in] 요청된 된 인터페이스의 IID입니다. 하는 경우 *pUnkOuter* 가 NULL이 아닌 *riid* 있어야 `IID_IUnknown`합니다.

*bstrKey*<br/>
[in] 런타임 라이선스 키에 대 한 호출에서 이전에 얻은 `RequestLicKey`합니다. 이 키는 개체를 만드는 데 필요 합니다.

*ppvObject*<br/>
[out] 지정 된 인터페이스 포인터에 대 한 포인터 *riid*합니다. 개체는이 인터페이스를 지원 하지 않는 경우 *ppvObject* NULL로 설정 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

사용 하는 라이선스 키를 가져올 수 있습니다 [RequestLicKey](#requestlickey)합니다. 허가 되지 않은 컴퓨터에서 개체를 만들기 위해 호출 해야 `CreateInstanceLic`합니다.

##  <a name="getlicinfo"></a>  CComClassFactory2::GetLicInfo

채웁니다를 [LICINFO](/windows/desktop/api/ocidl/ns-ocidl-taglicinfo) 클래스 팩터리를 설명 하는 정보를 사용 하 여 구조 기능 라이선스의 합니다.

```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```

### <a name="parameters"></a>매개 변수

*pLicInfo*<br/>
[out] 에 대 한 포인터를 `LICINFO` 구조입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

`fRuntimeKeyAvail` 이 구조체의 멤버로 허용 하는지 여부를, 라이선스 키가 지정 된, 클래스 팩터리 개체를 허가 되지 않은 컴퓨터에서 만들 수를 나타냅니다. 합니다 *fLicVerified* 멤버 전체 컴퓨터 라이선스가 있는지 여부를 나타냅니다.

##  <a name="lockserver"></a>  CComClassFactory2::LockServer

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

호출 `LockServer` 클라이언트가 여러 개체를 신속 하 게 생성할 수 있도록 클래스 팩터리를 점유 하는 데 사용 합니다.

##  <a name="requestlickey"></a>  CComClassFactory2::RequestLicKey

만들고 제공 하는 라이선스 키를 반환 합니다 `fRuntimeKeyAvail` 의 멤버는 [LICINFO](/windows/desktop/api/ocidl/ns-ocidl-taglicinfo) 구조는 TRUE.

```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```

### <a name="parameters"></a>매개 변수

*dwReserved*<br/>
[in] 사용 되지 않습니다. 0 이어야 합니다.

*pbstrKey*<br/>
[out] 라이선스 키에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

호출에 대 한 라이선스 키를 반드시 [CreateInstanceLic](#createinstancelic) 허가 되지 않은 컴퓨터에서 개체를 만들려고 합니다. 경우 `fRuntimeKeyAvail` FALSE 이면 개체를 완벽 하 게 사용이 허가 된 컴퓨터만 만들 수 있습니다.

호출 [만들도록](#getlicinfo) 의 값을 검색할 `fRuntimeKeyAvail`합니다.

## <a name="see-also"></a>참고자료

[CComClassFactoryAutoThread 클래스](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComClassFactorySingleton 클래스](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
