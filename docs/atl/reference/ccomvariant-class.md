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
ms.openlocfilehash: 6be05b52b96ada7871f955c687036a83b4e0b493
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259055"
---
# <a name="ccomvariant-class"></a>CComVariant 클래스

이 클래스는 저장 된 데이터의 형식을 나타내는 멤버를 제공 하는 VARIANT 형식을 래핑합니다.

## <a name="syntax"></a>구문

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComVariant::CComVariant](#ccomvariant)|생성자입니다.|
|[CComVariant::~CComVariant](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComVariant::Attach](#attach)|VARIANT를 연결 합니다 `CComVariant` 개체입니다.|
|[CComVariant::ChangeType](#changetype)|변환 된 `CComVariant` 개체를 새 형식입니다.|
|[CComVariant::Clear](#clear)|지웁니다는 `CComVariant` 개체입니다.|
|[CComVariant::Copy](#copy)|VARIANT를 복사 합니다 `CComVariant` 개체입니다.|
|[CComVariant::CopyTo](#copyto)|내용을 복사 합니다 `CComVariant` 개체입니다.|
|[CComVariant::Detach](#detach)|기본 변형에서 분리 된 `CComVariant` 개체입니다.|
|[CComVariant::GetSize](#getsize)|콘텐츠의 바이트 수의 크기를 반환 합니다 `CComVariant` 개체입니다.|
|[CComVariant::ReadFromStream](#readfromstream)|스트림에서 VARIANT를 로드합니다.|
|[CComVariant::SetByRef](#setbyref)|초기화를 `CComVariant` 집합과 개체를 `vt` VT_BYREF 멤버입니다.|
|[CComVariant::WriteToStream](#writetostream)|기본 변형 된 스트림에 저장합니다.|

### <a name="public-operators"></a>Public 연산자

|||
|-|-|
|[CComVariant::operator <](#operator_lt)|나타냅니다 여부는 `CComVariant` 개체를 사용 하면 지정 된 변형 보다 작습니다.|
|[CComVariant::operator >](#operator_gt)|나타냅니다 여부는 `CComVariant` 개체는 지정 된 변형 보다 큽니다.|
|[operator !=](#operator_neq)|나타냅니다 여부를 `CComVariant` 지정된 변형 개체와 같지 않습니다.|
|[operator =](#operator_eq)|에 값을 할당 합니다 `CComVariant` 개체입니다.|
|[operator ==](#operator_eq_eq)|나타냅니다 여부는 `CComVariant` 개체 같음 지정된 변형.|

## <a name="remarks"></a>설명

`CComVariant` 공용 구조체 및 공용 구조체에 저장 된 데이터의 형식을 나타내는 구성원으로 구성 하는 VARIANT 및 VARIANTARG 형식을 래핑합니다. 변형은 Automation에서 일반적으로 사용 됩니다.

`CComVariant` VARIANT를 사용할 수 있습니다 어디서 나 사용할 수 있도록 VARIANT 형식에서 파생 됩니다. 예를 들어 V_VT 매크로 사용 하 여 유형을 추출 하 수는 `CComVariant` 하거나 액세스할 수 있습니다는 `vt` VARIANT를 사용 하면 마찬가지로 직접 멤버입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>요구 사항

**헤더:** atlcomcli.h

##  <a name="attach"></a>  CComVariant::Attach

현재 콘텐츠를 안전 하 게 지웁니다 합니다 `CComVariant` 개체의 내용을 복사 *pSrc* 이 개체로 설정한 variant 형식의 *pSrc* 값을 vt_empty로 합니다.

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>매개 변수

*pSrc*<br/>
[in] 가리키는 합니다 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) 개체에 연결 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

보관 된 데이터의 소유권 *pSrc* 전송 되는 `CComVariant` 개체입니다.

##  <a name="ccomvariant"></a>  CComVariant::CComVariant

각 생성자의 안전 초기화를 처리 합니다 `CComVariant` 를 호출 하 여 개체를 `VariantInit` Win32 함수 또는 개체의 값 및 전달 된 매개 변수에 따라 형식을 설정 하 여 합니다.

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
[in] 합니다 `CComVariant` 또는 초기화 하는 데 사용 되는 VARIANT를 `CComVariant` 개체입니다. 원본 변형의 콘텐츠가 변환 하지 않고 대상에 복사 됩니다.

*lpszSrc*<br/>
[in] 문자열 초기화 하는 데는 `CComVariant` 개체입니다. 생성자 또는 LPCSTR 버전에는 ANSI 문자열의 LPCOLESTR 버전으로 (0으로 끝나는 와이드 유니코드) 문자열을 전달할 수 있습니다. 두 경우 모두에 문자열을 사용 하 여 할당 하는 BSTR 유니코드 변환 됩니다 `SysAllocString`합니다. 형식의 여 `CComVariant` 개체 VT_BSTR 됩니다.

*bSrc*<br/>
[in] 합니다 **bool** 초기화 하는 데는 `CComVariant` 개체입니다. 합니다 **bool** 저장 되기 전에 인수를 VARIANT_BOOL로 변환 합니다. 형식의 여 `CComVariant` 개체 VT_BOOL 됩니다.

*nSrc*<br/>
[in] **int**, **바이트**를 **짧은**를 **긴**, LONGLONG, ULONGLONG, **unsigned short**를 **부호 없는 long**, 또는 **부호 없는 int** 초기화 하는 데는 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체 됩니다 VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4, 또는 VT_UI4, 각각.

*vtSrc*<br/>
[in] 형식 변형입니다. 첫 번째 매개 변수 인 경우 **int**, 올바른 유형은 VT_I4 및 VT_INT 합니다. 첫 번째 매개 변수 인 경우 **긴**, 올바른 유형은 VT_I4 및 VT_ERROR 합니다. 첫 번째 매개 변수 인 경우 **이중**, 올바른 유형은 VT_R8 및 VT_DATE 합니다. 첫 번째 매개 변수 인 경우 **부호 없는 int**, 올바른 유형은 VT_UI4 및 VT_UINT 합니다.

*fltSrc*<br/>
[in] 합니다 **부동 소수점** 초기화 하는 데는 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체 VT_R4 됩니다.

*dblSrc*<br/>
[in] 합니다 **이중** 초기화 하는 데는 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체 VT_R8 됩니다.

*cySrc*<br/>
[in] 합니다 `CY` 초기화 하는 데는 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체 VT_CY 됩니다.

*pSrc*<br/>
[in] 합니다 `IDispatch` 또는 `IUnknown` 초기화 하는 데 대 한 포인터를 `CComVariant` 개체입니다. `AddRef` 인터페이스 포인터에서 호출 됩니다. 형식의 여 `CComVariant` 개체 VT_DISPATCH 또는 됩니다 VT_UNKNOWN, 각각.

또는 초기화 하는 데 SAFERRAY 포인터는 `CComVariant` 개체입니다. SAFEARRAY의 복사본에 저장 되는 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체는 원래 형식의 VT_ARRAY 고 SAFEARRAY 조합 됩니다.

*cSrc*<br/>
[in] 합니다 **char** 초기화 하는 데는 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체 VT_I1 됩니다.

*bstrSrc*<br/>
[in] 초기화를 사용 하는 BSTR을 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체 VT_BSTR 됩니다.

### <a name="remarks"></a>설명

호출 하 여 정리를 관리 하는 소멸자 [CComVariant::Clear](#clear)합니다.

##  <a name="dtor"></a>  CComVariant::~CComVariant

소멸자입니다.

```
~CComVariant() throw();
```

### <a name="remarks"></a>설명

이 메서드를 호출 하 여 정리를 관리 [CComVariant::Clear](#clear)합니다.

##  <a name="changetype"></a>  CComVariant::ChangeType

변환 된 `CComVariant` 개체를 새 형식입니다.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>매개 변수

*vtNew*<br/>
[in] 새 형식은 `CComVariant` 개체입니다.

*pSrc*<br/>
[in] 새 형식으로 변환할 값 변형에 대 한 포인터입니다. 기본값은 NULL 의미는 `CComVariant` 개체 위치에 변환 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

에 대 한 값을 전달 하는 경우 *pSrc*, `ChangeType` 변환 하는 데이 변형은 원본으로 사용 됩니다. 그렇지 않은 경우는 `CComVariant` 원본으로 사용할 개체입니다.

##  <a name="clear"></a>  CComVariant::Clear

지웁니다 합니다 `CComVariant` 를 호출 하 여 개체를 `VariantClear` Win32 함수입니다.

```
HRESULT Clear();
```

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

소멸자를 자동으로 호출 `Clear`합니다.

##  <a name="copy"></a>  CComVariant::Copy

해제 된 `CComVariant` 개체 및 지정 된 VARIANT의 복사본을 할당 합니다.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>매개 변수

*pSrc*<br/>
[in] 에 대 한 포인터를 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) 복사 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="copyto"></a>  CComVariant::CopyTo

내용을 복사 합니다 `CComVariant` 개체입니다.

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>매개 변수

*pstrDest*<br/>
Bstr의 내용의 복사본을 받는 요소를 `CComVariant` 개체입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

`CComVariant` VT_BSTR 형식의 개체 여야 합니다.

##  <a name="detach"></a>  CComVariant::Detach

기본 변형에서 분리 된 `CComVariant` 개체 및 개체의 형식 값을 vt_empty로 설정 합니다.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>매개 변수

*pDest*<br/>
[out] 개체의 기본 변형 값을 반환합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

참조 하는 변형의 콘텐츠가 참고 *pDest* 호출의 종류와 값이 할당 되기 전에 자동으로 해제 됩니다 `CComVariant` 개체입니다.

##  <a name="getsize"></a>  CComVariant::GetSize

간단한 고정 크기 변형에 대 한이 메서드는 다음과 같이 반환 됩니다. 합니다 **sizeof** 기본 데이터 형식 더하기 **sizeof(VARTYPE)** 합니다.

```
ULONG GetSize() const;
```

### <a name="return-value"></a>반환 값

현재 콘텐츠의 바이트 크기를 `CComVariant` 개체입니다.

### <a name="remarks"></a>설명

변형 인터페이스 포인터를 포함 하는 경우 `GetSize` 에 대 한 쿼리 `IPersistStream` 또는 `IPersistStreamInit`합니다. 경우 성공 하면 반환 값이 반환 하는 값의 하위 32 비트 `GetSizeMax` 와 함께 **sizeof** CLSID 및 **sizeof(VARTYPE)** 합니다. 인터페이스 포인터에 NULL 인 경우 `GetSize` 반환 된 **sizeof** 더하기 CLSID **sizeof(VARTYPE)** 합니다. 총 크기 ULONG_MAX, 보다 크면 `GetSize` 반환 **sizeof(VARTYPE)** 오류가 나타냅니다.

다른 모든 경우에서 VT_BSTR 형식의 VARIANT은 임시 현재 변형에서 강제 변환 됩니다. Null 문자 더하기의 크기를 더한 크기 문자열의 길이 문자열 자체의 길이 같이 계산 됩니다.이 BSTR 길이의 **sizeof(VARTYPE)** 합니다. VARIANT를 강제 하 여 VT_BSTR 형식의 VARIANT를 변환할 수 없는 경우 `GetSize` 반환 **sizeof(VARTYPE)** 합니다.

이 메서드에서 반환 되는 크기에 사용 된 바이트 수와 일치 [CComVariant::WriteToStream](#writetostream) 성공 조건입니다.

##  <a name="operator_eq"></a>  CComVariant::operator =

값과 해당 형식에 할당 된 `CComVariant` 개체입니다.

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
[in] 합니다 `CComVariant` 또는 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) 할당할 수는 `CComVariant` 개체입니다. 원본 변형의 콘텐츠가 변환 하지 않고 대상에 복사 됩니다.

*bstrSrc*<br/>
[in] 에 할당할 BSTR은 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체 VT_BSTR 됩니다.

*lpszSrc*<br/>
[in] 에 할당할 문자열의 `CComVariant` 개체입니다. LPCOLESTR 버전 연산자나 LPCSTR 버전에는 ANSI 문자열의 (0 종료 와이드 유니코드) 문자열을 전달할 수 있습니다. 두 경우 모두에 문자열을 사용 하 여 할당 하는 BSTR 유니코드 변환 됩니다 `SysAllocString`합니다. 형식의 여 `CComVariant` 개체 VT_BSTR 됩니다.

*bSrc*<br/>
[in] 합니다 **bool** 할당할 수는 `CComVariant` 개체입니다. 합니다 **bool** 저장 되기 전에 인수를 VARIANT_BOOL로 변환 합니다. 형식의 여 `CComVariant` 개체 VT_BOOL 됩니다.

*nSrc*<br/>
[in] **int**, 바이트 **짧은**를 **긴**, LONGLONG, ULONGLONG를 **unsigned short**를 **부호 없는 long**, 또는 **부호 없는 int** 할당할 수는 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체 됩니다 VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4, 또는 VT_UI4, 각각.

*fltSrc*<br/>
[in] 합니다 **부동 소수점** 할당할 수는 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체 VT_R4 됩니다.

*dblSrc*<br/>
[in] 합니다 **이중** 할당할 수는 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체 VT_R8 됩니다.

*cySrc*<br/>
[in] 합니다 `CY` 할당할 수는 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체 VT_CY 됩니다.

*pSrc*<br/>
[in] 합니다 `IDispatch` 또는 `IUnknown` 할당할 수에 대 한 포인터를 `CComVariant` 개체입니다. `AddRef` 인터페이스 포인터에서 호출 됩니다. 형식의 여 `CComVariant` 개체 VT_DISPATCH 또는 됩니다 VT_UNKNOWN, 각각.

또는 할당할 SAFEARRAY 포인터를 `CComVariant` 개체입니다. SAFEARRAY의 복사본에 저장 되는 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체는 원래 형식의 VT_ARRAY 고 SAFEARRAY 조합 됩니다.

*cSrc*<br/>
[in] 할당할 문자는 `CComVariant` 개체입니다. 형식의 여 `CComVariant` 개체 VT_I1 됩니다.

##  <a name="operator_eq_eq"></a>  CComVariant::operator ==

나타냅니다 여부는 `CComVariant` 개체 같음 지정된 변형.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>설명

경우 TRUE를 반환 값 및 유형의 *varSrc* 값 및 형식과 같은지 각각의 `CComVariant` 개체. 그렇지 않으면 FALSE입니다. 연산자 비교를 수행 하는 사용자의 기본 로캘을 사용 합니다.

연산자는 variant 형식의 값만을 비교합니다. 문자열, 정수 및 부동 소수점 하지만 하지 배열 또는 레코드를 비교합니다.

##  <a name="operator_neq"></a>  CComVariant::operator !=

나타냅니다 여부를 `CComVariant` 지정된 변형 개체와 같지 않습니다.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>설명

경우 TRUE를 반환 값 또는 유형의 *varSrc* 같지 않은 값 또는 형식 각각을 `CComVariant` 개체. 그렇지 않으면 FALSE입니다. 연산자 비교를 수행 하는 사용자의 기본 로캘을 사용 합니다.

연산자는 variant 형식의 값만을 비교합니다. 문자열, 정수 및 부동 소수점 하지만 하지 배열 또는 레코드를 비교합니다.

##  <a name="operator_lt"></a>  CComVariant::operator &lt;

나타냅니다 여부는 `CComVariant` 개체를 사용 하면 지정 된 변형 보다 작습니다.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>설명

경우 TRUE를 반환 값을 `CComVariant` 의 값 보다 작은지 *varSrc*합니다. 그렇지 않으면 FALSE입니다. 연산자 비교를 수행 하는 사용자의 기본 로캘을 사용 합니다.

##  <a name="operator_gt"></a>  CComVariant::operator &gt;

나타냅니다 여부는 `CComVariant` 개체는 지정 된 변형 보다 큽니다.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>설명

경우 TRUE를 반환 값을 `CComVariant` 개체의 값 보다 크면 *varSrc*합니다. 그렇지 않으면 FALSE입니다. 연산자 비교를 수행 하는 사용자의 기본 로캘을 사용 합니다.

##  <a name="readfromstream"></a>  CComVariant::ReadFromStream

지정 된 스트림에 포함 된 변형에 기본 변형 설정 합니다.

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
[in] 에 대 한 포인터를 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 인터페이스에 데이터를 포함 하는 스트림입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

`ReadToStream` 이전 호출을 [WriteToStream](#writetostream)합니다.

##  <a name="setbyref"></a>  CComVariant::SetByRef

초기화를 `CComVariant` 집합과 개체를 `vt` VT_BYREF 멤버입니다.

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>매개 변수

*T*<br/>
형식의 VARIANT BSTR, 예를 들어 **int**, 또는 **char**합니다.

*pT*<br/>
초기화 하는 데 포인터는 `CComVariant` 개체입니다.

### <a name="remarks"></a>설명

`SetByRef` 초기화 함수 템플릿입니다를 `CComVariant` 포인터에 대 한 개체 *pT* 설정 및는 `vt` VT_BYREF 멤버입니다. 예를 들어:

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

##  <a name="writetostream"></a>  CComVariant::WriteToStream

기본 변형 된 스트림에 저장합니다.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
[in] 에 대 한 포인터를 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 스트림에 대 한 인터페이스입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
