---
title: CComVariant 클래스
ms.date: 11/04/2016
f1_keywords:
- CComVariant
- ATLCOMCLI/ATL::CComVariant
- ATLCOMCLI/ATL::CComVariant::CComVariant
- ATLCOMCLI/ATL::CComVariant::Attach
- ATLCOMCLI/ATL::CComVariant::ChangeType
- ATLCOMCLI/ATL::CComVariant::Clear
- ATLCOMCLI/ATL::CComVariant::Copy
- ATLCOMCLI/ATL::CComVariant::CopyTo
- ATLCOMCLI/ATL::CComVariant::Detach
- ATLCOMCLI/ATL::CComVariant::GetSize
- ATLCOMCLI/ATL::CComVariant::ReadFromStream
- ATLCOMCLI/ATL::CComVariant::SetByRef
- ATLCOMCLI/ATL::CComVariant::WriteToStream
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
ms.openlocfilehash: b4c157435aaffab5f1315fd4636f55f9d4e0d5b4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496869"
---
# <a name="ccomvariant-class"></a>CComVariant 클래스

이 클래스는 VARIANT 형식을 래핑하여 저장 된 데이터의 형식을 나타내는 멤버를 제공 합니다.

## <a name="syntax"></a>구문

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[CComVariant::CComVariant](#ccomvariant)|생성자입니다.|
|[CComVariant::~CComVariant](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComVariant::Attach](#attach)|`CComVariant` 개체에 VARIANT를 연결 합니다.|
|[CComVariant::ChangeType](#changetype)|개체를 `CComVariant` 새 형식으로 변환 합니다.|
|[CComVariant::Clear](#clear)|개체를 `CComVariant` 지웁니다.|
|[CComVariant::Copy](#copy)|`CComVariant` 개체에 VARIANT를 복사 합니다.|
|[CComVariant::CopyTo](#copyto)|`CComVariant` 개체의 내용을 복사 합니다.|
|[CComVariant::Detach](#detach)|`CComVariant` 개체에서 내부 VARIANT를 분리 합니다.|
|[CComVariant::GetSize](#getsize)|`CComVariant` 개체 내용의 크기 (바이트)를 반환 합니다.|
|[CComVariant::ReadFromStream](#readfromstream)|스트림에서 VARIANT를 로드 합니다.|
|[CComVariant::SetByRef](#setbyref)|개체를 `CComVariant` 초기화 하 고 `vt` 멤버를 VT_BYREF로 설정 합니다.|
|[CComVariant::WriteToStream](#writetostream)|원본 변형을 스트림에 저장 합니다.|

### <a name="public-operators"></a>Public 연산자

|||
|-|-|
|[CComVariant:: operator <](#operator_lt)|`CComVariant` 개체가 지정 된 VARIANT 보다 적은지 여부를 나타냅니다.|
|[CComVariant:: operator >](#operator_gt)|`CComVariant` 개체가 지정 된 VARIANT 보다 큰지 여부를 나타냅니다.|
|[operator !=](#operator_neq)|`CComVariant` 개체가 지정 된 VARIANT와 같지 않은지 여부를 나타냅니다.|
|[operator =](#operator_eq)|`CComVariant` 개체에 값을 할당 합니다.|
|[operator ==](#operator_eq_eq)|`CComVariant` 개체가 지정 된 VARIANT와 같은지 여부를 나타냅니다.|

## <a name="remarks"></a>설명

`CComVariant`union 및 union에 저장 된 데이터의 형식을 나타내는 멤버로 구성 된 VARIANT 및 VARIANTARG 형식을 래핑합니다. 변형은 일반적으로 자동화에 사용 됩니다.

`CComVariant`는 variant 형식에서 파생 되므로 VARIANT를 사용할 수 있는 모든 곳에서 사용할 수 있습니다. 예를 들어 V_VT 매크로를 사용 하 여의 `CComVariant` 형식을 추출 하거나 VARIANT를 사용할 때와 마찬가지로 멤버에 `vt` 직접 액세스할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>요구 사항

**헤더:** comcli .h

##  <a name="attach"></a>  CComVariant::Attach

`CComVariant` 개체의 현재 콘텐츠를 안전 하 게 지우고 *psrc* 의 내용을이 개체에 복사한 다음 *psrc* 의 변형 형식을 VT_EMPTY로 설정 합니다.

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>매개 변수

*pSrc*<br/>
진행 개체에 연결할 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 를 가리킵니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

*Psrc* 에서 보유 한 데이터의 소유권이 `CComVariant` 개체에 전송 됩니다.

##  <a name="ccomvariant"></a>  CComVariant::CComVariant

각 생성자는 Win32 함수를 `CComVariant` `VariantInit` 호출 하거나 전달 된 매개 변수에 따라 개체의 값과 형식을 설정 하 여 개체의 안전 초기화를 처리 합니다.

```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```

### <a name="parameters"></a>매개 변수

*varSrc*<br/>
진행 개체를 초기화 하는 데 사용 되는 또는VARIANT입니다.`CComVariant` `CComVariant` 원본 변형의 내용은 변환 하지 않고 대상으로 복사 됩니다.

*lpszSrc*<br/>
진행 `CComVariant` 개체를 초기화 하는 데 사용 되는 문자열입니다. 0으로 끝나는 와이드 (유니코드) 문자열을 생성자의 LPCOLESTR 버전 또는 ANSI 문자열에서 LPCSTR 버전으로 전달할 수 있습니다. 두 경우 모두 문자열은를 사용 하 여 `SysAllocString`할당 된 유니코드 BSTR로 변환 됩니다. `CComVariant` 개체의 형식은 VT_BSTR 됩니다.

*bSrc*<br/>
진행 개체 를 `CComVariant` 초기화 하는 데 사용 되는 부울입니다. **Bool** 인수는 저장 되기 전에 VARIANT_BOOL로 변환 됩니다. `CComVariant` 개체의 형식은 VT_BOOL 됩니다.

*nSrc*<br/>
진행 `CComVariant` 개체를 초기화 하는 데 사용 되는 **int**, **BYTE**, **short**, **long**, intlong, ULONGLONG, unsigned **short**, **unsigned long**또는 **unsigned int** 입니다. `CComVariant` 개체의 형식은 각각 VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 또는 VT_UI4입니다.

*vtSrc*<br/>
진행 변형 유형입니다. 첫 번째 매개 변수가 **int**인 경우 유효한 유형은 VT_I4 및 VT_INT입니다. 첫 번째 매개 변수가 **long**인 경우 유효한 유형은 VT_I4 및 VT_ERROR입니다. 첫 번째 매개 변수가 **double**인 경우 유효한 형식은 VT_R8 및 VT_DATE입니다. 첫 번째 매개 변수가 **unsigned int**인 경우 유효한 유형은 VT_UI4 및 VT_UINT입니다.

*fltSrc*<br/>
진행 개체를 `CComVariant` 초기화 하는 데 사용 되는 **부동 소수점** 입니다. `CComVariant` 개체의 형식은 VT_R4 됩니다.

*dblSrc*<br/>
진행 `CComVariant` 개체를 초기화 하는 데 사용 되는 **double** 입니다. `CComVariant` 개체의 형식은 VT_R8 됩니다.

*cySrc*<br/>
진행 개체를`CComVariant` 초기화 하는 데사용`CY` 되는입니다. `CComVariant` 개체의 형식은 VT_CY 됩니다.

*pSrc*<br/>
진행 개체를 `IUnknown` 초기화 하는 데 사용 되는 또는포인터입니다.`IDispatch` `CComVariant` `AddRef`는 인터페이스 포인터에서 호출 됩니다. `CComVariant` 개체의 형식은 각각 VT_DISPATCH 또는 VT_UNKNOWN가 됩니다.

또는 `CComVariant` 개체를 초기화 하는 데 사용 되는가 나 er광선 포인터입니다. SAFEARRAY의 복사본은 `CComVariant` 개체에 저장 됩니다. `CComVariant` 개체의 형식은 SAFEARRAY 및 VT_ARRAY의 원래 형식으로 결합 됩니다.

*cSrc*<br/>
진행 `CComVariant` 개체를 초기화 하는 데 사용 되는 **문자** 입니다. `CComVariant` 개체의 형식은 VT_I1 됩니다.

*bstrSrc*<br/>
진행 개체를 `CComVariant` 초기화 하는 데 사용 되는 BSTR입니다. `CComVariant` 개체의 형식은 VT_BSTR 됩니다.

### <a name="remarks"></a>설명

소멸자는 [CComVariant:: Clear](#clear)를 호출 하 여 정리를 관리 합니다.

##  <a name="dtor"></a>  CComVariant::~CComVariant

소멸자입니다.

```
~CComVariant() throw();
```

### <a name="remarks"></a>설명

이 메서드는 [CComVariant:: Clear](#clear)를 호출 하 여 정리를 관리 합니다.

##  <a name="changetype"></a>  CComVariant::ChangeType

개체를 `CComVariant` 새 형식으로 변환 합니다.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>매개 변수

*vtNew*<br/>
진행 `CComVariant` 개체의 새 형식입니다.

*pSrc*<br/>
진행 값이 새 형식으로 변환 될 변형에 대 한 포인터입니다. 기본값은 NULL입니다. 즉 `CComVariant` , 개체가 현재 위치로 변환 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

*Psrc*의 값을 전달 하는 경우 `ChangeType` 는 변환의 원본으로이 VARIANT를 사용 합니다. 그렇지 않으면 개체가 원본이 됩니다. `CComVariant`

##  <a name="clear"></a>  CComVariant::Clear

Win32 함수 `CComVariant` 를 `VariantClear` 호출 하 여 개체를 지웁니다.

```
HRESULT Clear();
```

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

소멸자는를 자동 `Clear`으로 호출 합니다.

##  <a name="copy"></a>  CComVariant::Copy

개체를 `CComVariant` 해제 한 다음 지정 된 VARIANT의 복사본을 할당 합니다.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>매개 변수

*pSrc*<br/>
진행 복사할 [변형](/windows/win32/api/oaidl/ns-oaidl-variant) 에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="copyto"></a>  CComVariant::CopyTo

`CComVariant` 개체의 내용을 복사 합니다.

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>매개 변수

*pstrDest*<br/>
`CComVariant` 개체 콘텐츠의 복사본을 받을 BSTR을 가리킵니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

개체 `CComVariant` 는 VT_BSTR 형식 이어야 합니다.

##  <a name="detach"></a>  CComVariant::Detach

`CComVariant` 개체에서 내부 VARIANT를 분리 하 고 개체의 형식을 VT_EMPTY로 설정 합니다.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>매개 변수

*pDest*<br/>
제한이 개체의 내부 변형 값을 반환 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

*Pdest* 에서 참조 되는 변형의 내용은 호출 `CComVariant` 하는 개체의 값과 형식이 할당 되기 전에 자동으로 지워집니다.

##  <a name="getsize"></a>  CComVariant::GetSize

단순 고정 크기 변형에 대해이 메서드는 내부 데이터 형식에 **sizeof (VARTYPE)** 를 더한 **sizeof** 를 반환 합니다.

```
ULONG GetSize() const;
```

### <a name="return-value"></a>반환 값

`CComVariant` 개체의 현재 내용에 대 한 크기 (바이트)입니다.

### <a name="remarks"></a>설명

VARIANT에 인터페이스 포인터가 `GetSize` 포함 된 경우는 또는 `IPersistStreamInit`에 `IPersistStream` 대해 쿼리 합니다. 성공 하는 경우 반환 값은에서 `GetSizeMax` 반환 된 값의 하위 32 비트이 고 **sizeof** a CLSID와 **sizeof (VARTYPE)** 를 더한 값입니다. 인터페이스 포인터가 NULL `GetSize` 인 경우 sizeof a의 **sizeof** 와 **sizeof (VARTYPE)** 를 반환 합니다. 총 크기가 ULONG_MAX 보다 크면에서 오류를 나타내는 `GetSize` **sizeof (VARTYPE)** 을 반환 합니다.

다른 모든 경우에는 VT_BSTR 형식의 임시 변형이 현재 변형에서 강제 변환 됩니다. 이 BSTR의 길이는 문자열의 길이와 문자열 자체의 길이 + null 문자 + **sizeof (VARTYPE)** 의 크기에 따라 계산 됩니다. 변형을 VT_BSTR 형식의 변형으로 강제 변환할 수 없는 경우 `GetSize` **sizeof (VARTYPE)** 을 반환 합니다.

이 메서드에서 반환 되는 크기는 성공 조건에서 [CComVariant:: WriteToStream](#writetostream) 에 사용 되는 바이트 수와 일치 합니다.

##  <a name="operator_eq"></a>  CComVariant::operator =

값과 해당 형식을 `CComVariant` 개체에 할당 합니다.

```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```

### <a name="parameters"></a>매개 변수

*varSrc*<br/>
진행 개체에`CComVariant` 할당할 [또는 VARIANT입니다](/windows/win32/api/oaidl/ns-oaidl-variant) `CComVariant` . 원본 변형의 내용은 변환 하지 않고 대상으로 복사 됩니다.

*bstrSrc*<br/>
진행 `CComVariant` 개체에 할당할 BSTR입니다. `CComVariant` 개체의 형식은 VT_BSTR 됩니다.

*lpszSrc*<br/>
진행 `CComVariant` 개체에 할당 될 문자열입니다. 0으로 끝나는 와이드 (유니코드) 문자열을 해당 연산자의 LPCOLESTR 버전 또는 ANSI 문자열을 LPCSTR 버전으로 전달할 수 있습니다. 두 경우 모두 문자열은를 사용 하 여 `SysAllocString`할당 된 유니코드 BSTR로 변환 됩니다. `CComVariant` 개체의 형식은 VT_BSTR 됩니다.

*bSrc*<br/>
진행 `CComVariant` 개체에 할당할 **bool** 입니다. **Bool** 인수는 저장 되기 전에 VARIANT_BOOL로 변환 됩니다. `CComVariant` 개체의 형식은 VT_BOOL 됩니다.

*nSrc*<br/>
진행 개체`CComVariant` 에 할당할 **int**, BYTE, **short**, **long**, slong, ULONGLONG, unsigned **short**, **unsigned long**또는 **unsigned int** 입니다. `CComVariant` 개체의 형식은 각각 VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 또는 VT_UI4입니다.

*fltSrc*<br/>
진행 `CComVariant` 개체에 할당할 **부동 소수점** 입니다. `CComVariant` 개체의 형식은 VT_R4 됩니다.

*dblSrc*<br/>
진행 `CComVariant` 개체에 할당할 **double** 입니다. `CComVariant` 개체의 형식은 VT_R8 됩니다.

*cySrc*<br/>
진행 개체에`CComVariant`할당할입니다. `CY` `CComVariant` 개체의 형식은 VT_CY 됩니다.

*pSrc*<br/>
진행 개체에`CComVariant` 할당할 `IUnknown`또는포인터입니다 `IDispatch` . `AddRef`는 인터페이스 포인터에서 호출 됩니다. `CComVariant` 개체의 형식은 각각 VT_DISPATCH 또는 VT_UNKNOWN가 됩니다.

또는 `CComVariant` 개체에 할당 될 SAFEARRAY 포인터입니다. SAFEARRAY의 복사본은 `CComVariant` 개체에 저장 됩니다. `CComVariant` 개체의 형식은 SAFEARRAY 및 VT_ARRAY의 원래 형식으로 결합 됩니다.

*cSrc*<br/>
진행 `CComVariant` 개체에 할당 될 문자입니다. `CComVariant` 개체의 형식은 VT_I1 됩니다.

##  <a name="operator_eq_eq"></a>CComVariant:: operator = =

`CComVariant` 개체가 지정 된 VARIANT와 같은지 여부를 나타냅니다.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>설명

*Varsrc* 의 값과 형식이 각각 `CComVariant` 개체의 값 및 형식과 같은 경우 TRUE를 반환 합니다. 그렇지 않으면 FALSE입니다. 연산자는 사용자의 기본 로캘을 사용 하 여 비교를 수행 합니다.

연산자는 variant 형식의 값만 비교 합니다. 배열 또는 레코드는 제외 하 고 문자열, 정수 및 부동 소수점을 비교 합니다.

##  <a name="operator_neq"></a>  CComVariant::operator !=

`CComVariant` 개체가 지정 된 VARIANT와 같지 않은지 여부를 나타냅니다.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>설명

*Varsrc* 의 값 또는 형식이 각각 `CComVariant` 개체의 값 또는 형식과 같지 않으면 TRUE를 반환 합니다. 그렇지 않으면 FALSE입니다. 연산자는 사용자의 기본 로캘을 사용 하 여 비교를 수행 합니다.

연산자는 variant 형식의 값만 비교 합니다. 배열 또는 레코드는 제외 하 고 문자열, 정수 및 부동 소수점을 비교 합니다.

##  <a name="operator_lt"></a>CComVariant:: operator&lt;

`CComVariant` 개체가 지정 된 VARIANT 보다 적은지 여부를 나타냅니다.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>설명

`CComVariant` 개체의 값이 *varsrc*의 값 보다 작은 경우 TRUE를 반환 합니다. 그렇지 않으면 FALSE입니다. 연산자는 사용자의 기본 로캘을 사용 하 여 비교를 수행 합니다.

##  <a name="operator_gt"></a>CComVariant:: operator&gt;

`CComVariant` 개체가 지정 된 VARIANT 보다 큰지 여부를 나타냅니다.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>설명

`CComVariant` 개체의 값이 *varsrc*값 보다 크면 TRUE를 반환 합니다. 그렇지 않으면 FALSE입니다. 연산자는 사용자의 기본 로캘을 사용 하 여 비교를 수행 합니다.

##  <a name="readfromstream"></a>  CComVariant::ReadFromStream

기본 변형을 지정 된 스트림에 포함 된 변형으로 설정 합니다.

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
진행 데이터를 포함 하는 스트림의 [IStream](/windows/win32/api/objidl/nn-objidl-istream) 인터페이스에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

`ReadToStream`[WriteToStream](#writetostream)에 대 한 이전 호출이 필요 합니다.

##  <a name="setbyref"></a>  CComVariant::SetByRef

개체를 `CComVariant` 초기화 하 고 `vt` 멤버를 VT_BYREF로 설정 합니다.

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
변형 유형입니다 (예: BSTR, **int**또는 **char**).

*pT*<br/>
`CComVariant` 개체를 초기화 하는 데 사용 되는 포인터입니다.

### <a name="remarks"></a>설명

`SetByRef`는 `CComVariant` 개체를 포인터 *pT* 로 초기화 하 고 `vt` 멤버를 VT_BYREF로 설정 하는 함수 템플릿입니다. 예를 들어:

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

##  <a name="writetostream"></a>  CComVariant::WriteToStream

원본 변형을 스트림에 저장 합니다.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
진행 스트림의 [IStream](/windows/win32/api/objidl/nn-objidl-istream) 인터페이스에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
