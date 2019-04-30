---
title: CComCoClass 클래스
ms.date: 11/04/2016
f1_keywords:
- CComCoClass
- ATLCOM/ATL::CComCoClass
- ATLCOM/ATL::CComCoClass::CreateInstance
- ATLCOM/ATL::CComCoClass::Error
- ATLCOM/ATL::CComCoClass::GetObjectCLSID
- ATLCOM/ATL::CComCoClass::GetObjectDescription
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
ms.openlocfilehash: c52e1a95483807f9c842b0b904cd2314258f0e26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259874"
---
# <a name="ccomcoclass-class"></a>CComCoClass 클래스

이 클래스는 클래스의 인스턴스를 만들고 해당 속성을 가져오는 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
template <class T, const CLSID* pclsid = &CLSID_NULL>
class CComCoClass
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `CComCoClass`합니다.

*pclsid*<br/>
개체의 CLSID에 대 한 포인터입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComCoClass::CreateInstance](#createinstance)|(정적) 클래스 및 인터페이스에 대 한 쿼리 인스턴스를 만듭니다.|
|[CComCoClass::Error](#error)|(정적) 클라이언트에 자세한 오류 정보를 반환합니다.|
|[CComCoClass::GetObjectCLSID](#getobjectclsid)|(정적) 개체의 클래스 식별자를 반환합니다.|
|[CComCoClass::GetObjectDescription](#getobjectdescription)|(정적) 개체의 설명을 반환 하려면 재정의 합니다.|

## <a name="remarks"></a>설명

`CComCoClass` 개체의 CLSID를 검색, 오류 정보를 설정 하 고, 클래스의 인스턴스를 만드는 메서드를 제공 합니다. 개체 맵의에 등록 된 모든 클래스에서 파생 되는 `CComCoClass`합니다.

`CComCoClass` 또한 개체에 대 한 기본 클래스 팩터리 및 집계 모델을 정의합니다. `CComCoClass` 다음 두 매크로 사용합니다.

- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) 선언 되도록 클래스 팩터리 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)합니다.

- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable) 개체를 집계할 수 있도록 선언 합니다.

클래스 정의에서 다른 매크로 지정 하 여 이러한 기본값 중 하나를 재정의할 수 있습니다. 예를 사용 하려면 [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) 대신 `CComClassFactory`를 지정 합니다 [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) 매크로:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="createinstance"></a>  CComCoClass::CreateInstance

이 사용 하 여 `CreateInstance` COM의 인스턴스를 만드는 함수 개체 및 COM API를 사용 하지 않고 인터페이스 포인터를 검색 합니다.

```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```

### <a name="parameters"></a>매개 변수

*Q*<br/>
통해 반환 되어야 하는 COM 인터페이스 *pp*합니다.

*punkOuter*<br/>
[in] 알 수 없는 외부 또는 집계의 제어 알 수 없음.

*pp*<br/>
[out] 만들기가 성공 하는 경우 요청 된 인터페이스 포인터를 받는 포인터 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다. 참조 [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance) 가능한 반환 값에 대 한 Windows SDK에 있습니다.

### <a name="remarks"></a>설명

이 함수의 첫 번째 오버 로드를 사용 하 여 일반적인 개체를 생성 합니다. 생성 되는 개체를 집계 해야 하는 경우 두 번째 오버 로드를 사용 합니다.

필요한 COM 개체가 구현 하는 ATL 클래스 (첫 번째 템플릿 매개 변수로 사용 되는 클래스 이므로 [CComCoClass](../../atl/reference/ccomcoclass-class.md)) 호출 하는 코드와 동일한 프로젝트에 있어야 합니다. COM 개체의 생성이 ATL 클래스에 대 한 등록 클래스 팩터리에서 수행 됩니다.

이러한 함수는 사용 하 여 외부에서 만들 수 없도록 방지할 수 있는 개체를 만드는 데 유용 합니다 [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto) 매크로입니다. 효율성을 위해 COM API를 방지 하려는 경우에도 유용 합니다.

인터페이스 *Q* 사용 하 여 검색할 수 있는 IID 연결 되어 있어야 합니다. 합니다 [__uuidof](../../cpp/uuidof-operator.md) 연산자입니다.

### <a name="example"></a>예제

다음 예에서 `CDocument` ATL 마법사에서 생성 된 클래스에서 파생 `CComCoClass` 구현 하는 `IDocument` 인터페이스입니다. 클래스는 OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO 매크로 사용 하 여 개체 맵에 등록 클라이언트에서 사용 하 여 문서 인스턴스를 만들 수 없습니다 [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)합니다. `CApplication` 문서 클래스의 인스턴스를 만드는 고유한 COM 인터페이스 중 하나에서 메서드를 제공 하는 CoClass를입니다. 얼마나 쉬운지 아래 코드를 사용 하 여 문서 클래스의 인스턴스를 만들 수는 `CreateInstance` 에서 상속 된 멤버는 `CComCoClass` 기본 클래스입니다.

[!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]

##  <a name="error"></a>  CComCoClass::Error

이 정적 함수를 설정 합니다 `IErrorInfo` 클라이언트에 오류 정보를 제공 하는 인터페이스입니다.

```
static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance ());

static HRESULT Error(
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```

### <a name="parameters"></a>매개 변수

*lpszDesc*<br/>
[in] 오류를 설명 하는 문자열입니다. 유니코드 버전 `Error` 형식임 *lpszDesc* 입니다 LPCOLESTR 입력; ANSI 버전 LPCSTR 형식을 지정 합니다.

*iid*<br/>
[in] 오류는 운영 체제에 의해 정의 된 경우 오류 또는 GUID_NULL (기본값)를 정의 하는 인터페이스의 IID입니다.

*hRes*<br/>
[in] 원하는 HRESULT 호출자에 게 반환 합니다. 기본값은 0입니다. 대 한 자세한 내용은 *hRes*, 주의 참조 하세요.

*nID*<br/>
[in] 오류 설명 문자열을 저장 된 리소스 식별자입니다. 이 값 사이 있어야 0x0200 및 0xFFFF 까지입니다. 디버그 빌드에서 **ASSERT** 경우에 발생 합니다 *nID* 는 유효한 문자열을 인덱싱하지 않습니다. 릴리스 빌드에서 오류 설명 문자열을 "알 수 없는 오류입니다."로 설정 됩니다.

*dwHelpID*<br/>
[in] 오류에 대 한 도움말 컨텍스트 식별자입니다.

*lpszHelpFile*<br/>
[in] 경로 오류를 설명 하는 도움말 파일의 이름입니다.

*hInst*<br/>
[in] 리소스에 대 한 핸들입니다. 이 매개 변수는 기본적으로 `_AtlModule::GetResourceInstance`, 여기서 `_AtlModule` 의 인스턴스인 전역 [CAtlModule](../../atl/reference/catlmodule-class.md)합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

호출 `Error`, 개체를 구현 해야 합니다 `ISupportErrorInfo Interface` 인터페이스.

경우는 *hRes* 매개 변수 이면 0이 아니면 `Error` 의 값을 반환 *hRes*합니다. 하는 경우 *hRes* 이 0 이면의 처음 4 개 버전 `Error` DISP_E_EXCEPTION을 반환 합니다. 매크로의 결과 반환 하는 마지막 두 버전 **MAKE_HRESULT (1, FACILITY_ITF** *nID* **)** 합니다.

##  <a name="getobjectclsid"></a>  CComCoClass::GetObjectCLSID

개체의 CLSID를 검색 하는 일관 된 방법을 제공 합니다.

```
static const CLSID& WINAPI GetObjectCLSID();
```

### <a name="return-value"></a>반환 값

개체의 클래스 식별자입니다.

##  <a name="getobjectdescription"></a>  CComCoClass::GetObjectDescription

이 정적 함수에는 클래스 개체에 대 한 텍스트 설명을 가져옵니다.

```
static LPCTSTR WINAPI GetObjectDescription();
```

### <a name="return-value"></a>반환 값

클래스 개체의 설명입니다.

### <a name="remarks"></a>설명

기본 구현은 NULL을 반환합니다. 이 메서드를 재정의할 수 있습니다 합니다 [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description) 매크로입니다. 예를 들어:

[!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]

`GetObjectDescription` 호출한 `IComponentRegistrar::GetComponents`합니다. `IComponentRegistrar` 등록 및 DLL의 개별 구성 요소를 등록 취소할 수 있는 자동화 인터페이스가입니다. ATL 프로젝트 마법사를 사용 하 여 구성 요소 등록자 개체를 만들 때 마법사는 자동으로 구현 된 `IComponentRegistrar` 인터페이스입니다. `IComponentRegistrar` Microsoft Transaction Server에서 주로 사용 됩니다.

ATL 프로젝트 마법사에 대 한 자세한 내용은 문서 참조 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
