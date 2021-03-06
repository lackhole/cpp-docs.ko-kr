---
title: COleVariant 클래스
ms.date: 11/04/2016
f1_keywords:
- COleVariant
- AFXDISP/COleVariant
- AFXDISP/COleVariant::COleVariant
- AFXDISP/COleVariant::Attach
- AFXDISP/COleVariant::ChangeType
- AFXDISP/COleVariant::Clear
- AFXDISP/COleVariant::Detach
- AFXDISP/COleVariant::GetByteArrayFromVariantArray
- AFXDISP/COleVariant::SetString
helpviewer_keywords:
- COleVariant [MFC], COleVariant
- COleVariant [MFC], Attach
- COleVariant [MFC], ChangeType
- COleVariant [MFC], Clear
- COleVariant [MFC], Detach
- COleVariant [MFC], GetByteArrayFromVariantArray
- COleVariant [MFC], SetString
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
ms.openlocfilehash: 49cd4a8d3db436d5e3c4d29efbb4d80b4741a270
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739785"
---
# <a name="colevariant-class"></a>COleVariant 클래스

[VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 데이터 형식을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class COleVariant : public tagVARIANT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[COleVariant::COleVariant](#colevariant)|`COleVariant` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[COleVariant::Attach](#attach)|에 VARIANT `COleVariant`를 연결 합니다.|
|[COleVariant::ChangeType](#changetype)|이 `COleVariant` 개체의 변형 유형을 변경 합니다.|
|[COleVariant::Clear](#clear)|이 지우고 `COleVariant` 개체입니다.|
|[COleVariant::Detach](#detach)|에서 variant를 분리 `COleVariant` 하 고 variant를 반환 합니다.|
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|기존 variant 배열에서 바이트 배열을 검색 합니다.|
|[COleVariant::SetString](#setstring)|문자열을 특정 형식 (일반적으로 ANSI)으로 설정 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|Description|
|----------|-----------------|
|[COleVariant:: operator LPCVARIANT](#operator_lpcvariant)|`COleVariant` 값`LPCVARIANT`을로 변환 합니다.|
|[COleVariant:: operator LPVARIANT](#operator_lpvariant)|`COleVariant` 개체`LPVARIANT`를로 변환 합니다.|
|[COleVariant:: operator =](#operator_eq)|값을 `COleVariant` 복사 합니다.|
|[COleVariant::operator ==](#operator_eq_eq)|두 `COleVariant` 값을 비교 합니다.|
|[COleVariant::operator &lt;&lt;, &gt;&gt;](#operator_lt_lt__gt_gt)|`COleVariant` 또는 `COleVariant` `CArchive` `CArchive`에 대한값을출력하고에서개체를입력합니다.`CDumpContext`|

## <a name="remarks"></a>설명

이 데이터 형식은 OLE 자동화에 사용 됩니다. 특히 [DISPPARAMS](/windows/win32/api/oaidl/ns-oaidl-dispparams) 구조체에는 VARIANT 구조 배열에 대 한 포인터가 포함 되어 있습니다. 구조체는 [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)에 매개 변수를 전달 하는 데 사용 됩니다. `DISPPARAMS`

> [!NOTE]
> 이 클래스는 `VARIANT` 구조체에서 파생 됩니다. 즉,을 `VARIANT` 호출 하는 `COleVariant` 매개 변수에서 `VARIANT` 구조체의 데이터 멤버에 액세스할 수 있는 데이터 멤버가 `COleVariant`있는를 전달할 수 있습니다.

두 개의 관련 MFC 클래스인 [COleCurrency](../../mfc/reference/colecurrency-class.md) 및 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 는 variant 데이터 형식 CURRENCY ( `VT_CY`) 및 DATE ( `VT_DATE`)를 캡슐화 합니다. `COleVariant`클래스는 DAO 클래스에서 광범위 하 게 사용 됩니다 .이 클래스의 일반적인 사용에 대해서는 이러한 클래스 (예: [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 및 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md))를 참조 하세요.

자세한 내용은 Windows SDK에서 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy~r1), [DISPPARAMS](/windows/win32/api/oaidl/ns-oaidl-dispparams)및 [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) 항목을 참조 하세요.

`COleVariant` 클래스에 대 한 자세한 내용과 ole 자동화에서의 사용에 대 한 자세한 내용은 [자동화](../../mfc/automation.md)문서의 "ole automation에서 매개 변수 전달"을 참조 하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층

`tagVARIANT`

`COleVariant`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

##  <a name="attach"></a>  COleVariant::Attach

지정 된 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 개체를 현재 `COleVariant` 개체에 연결 하려면이 함수를 호출 합니다.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>매개 변수

*varSrc*<br/>
`VARIANT` 현재`COleVariant` 개체에 연결 되는 기존 개체입니다.

### <a name="remarks"></a>설명

이 함수는 *Varsrc* 의 VARTYPE을 VT_EMPTY로 설정 합니다.

자세한 내용은 Windows SDK에서 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 및 [varenum](/windows/win32/api/wtypes/ne-wtypes-varenum) 항목을 참조 하세요.

##  <a name="colevariant"></a>  COleVariant::COleVariant

`COleVariant` 개체를 생성합니다.

```
COleVariant();
COleVariant(const VARIANT& varSrc);
COleVariant(const COleVariant& varSrc);
COleVariant(LPCVARIANT pSrc);
COleVariant(LPCTSTR lpszSrc);
COleVariant(LPCTSTR lpszSrc, VARTYPE vtSrc);
COleVariant(CString& strSrc);
COleVariant(BYTE nSrc);
COleVariant(short nSrc, VARTYPE vtSrc = VT_I2);
COleVariant(long lSrc,VARTYPE vtSrc = VT_I4);
COleVariant(const COleCurrency& curSrc);
COleVariant(float fltSrc);
COleVariant(double dblSrc);
COleVariant(const COleDateTime& timeSrc);
COleVariant(const CByteArray& arrSrc);
COleVariant(const CLongBinary& lbSrc);
COleVariant(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>매개 변수

*varSrc*<br/>
새 `VARIANT` `COleVariant` 개체`COleVariant` 에 복사할 기존 또는 개체입니다.

*pSrc*<br/>
`VARIANT` 새`COleVariant` 개체에 복사 되는 개체에 대 한 포인터입니다.

*lpszSrc*<br/>
새 `COleVariant` 개체에 복사할 null 종료 문자열입니다.

*vtSrc*<br/>
`VARTYPE` 새`COleVariant` 개체에 대 한입니다.

*strSrc*<br/>
새`COleVariant` 개체에 복사할 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.

*nsrc*, *lsrc* 새 `COleVariant` 개체로 복사할 숫자 값입니다.

*vtSrc*<br/>
`VARTYPE` 새`COleVariant` 개체에 대 한입니다.

*curSrc*<br/>
새`COleVariant` 개체에 복사할 [COleCurrency](../../mfc/reference/colecurrency-class.md) 개체입니다.

*fltSrc*, *dblSrc*<br/>
새 `COleVariant` 개체에 복사될 숫자 값입니다.

*timeSrc*<br/>
새`COleVariant` 개체에 복사할 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체입니다.

*arrSrc*<br/>
새`COleVariant` 개체에 복사할 [CByteArray](../../mfc/reference/cbytearray-class.md) 개체입니다.

*lbSrc*<br/>
새`COleVariant` 개체에 복사할 [CLongBinary](../../mfc/reference/clongbinary-class.md) 개체입니다.

*pidl*<br/>
새`COleVariant` 개체로 복사할 [itemidlist](/windows/win32/api/shtypes/ns-shtypes-itemidlist) 구조체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이러한 모든 생성자는 지정 `COleVariant` 된 값으로 초기화 된 새 개체를 만듭니다. 이러한 각 생성자에 대 한 간략 한 설명은 다음과 같습니다.

- **COleVariant ()** 빈 `COleVariant` 개체인 VT_EMPTY을 만듭니다.

- **COleVariant (** *varsrc* **)** 기존 `VARIANT` 또는`COleVariant` 개체를 복사 합니다. 변형 형식이 유지됩니다.

- **COleVariant (** *psrc* **)** 기존 `VARIANT` 또는`COleVariant` 개체를 복사 합니다. 변형 형식이 유지됩니다.

- **COleVariant (** *lpszSrc* **)** 새 개체인 VT_BSTR (유니코드)에 문자열을 복사 합니다.

- **COleVariant (** *lpszSrc* **,** *vtSrc* **)** 새 개체에 문자열을 복사 합니다. *VtSrc* 매개 변수는 VT_BSTR (유니코드) 또는 VT_BSTRT (ANSI) 여야 합니다.

- **COleVariant (** *strsrc* **)** 새 개체인 VT_BSTR (유니코드)에 문자열을 복사 합니다.

- **COleVariant (** *nsrc* **)** 8 비트 정수를 새 개체인 VT_UI1에 복사 합니다.

- **COleVariant (** *nsrc* **,** *vtSrc* **)** 16 비트 정수 (또는 부울 값)를 새 개체에 복사 합니다. *VtSrc* 매개 변수는 VT_I2 또는 VT_BOOL 여야 합니다.

- **COleVariant (** *lsrc* **,** *vtSrc* **)** 32 비트 정수 (또는 값)를 새 개체에 복사 합니다. *VtSrc* 매개 변수는 VT_I4, VT_ERROR 또는 VT_BOOL 여야 합니다.

- **COleVariant (** *cursrc* **)** 새 개체인 `COleCurrency` VT_CY에 값을 복사 합니다.

- **COleVariant (** *fltSrc* **)** 32 비트 부동 소수점 값을 VT_R4 새 개체에 복사 합니다.

- **COleVariant (** *dblSrc* **)** 64 비트 부동 소수점 값을 VT_R8 새 개체에 복사 합니다.

- **COleVariant (** *timesrc* **)** 새 개체인 `COleDateTime` VT_DATE에 값을 복사 합니다.

- **COleVariant (** *arrsrc* **)** 새 개체인 VT_EMPTY에 개체를복사합니다.`CByteArray`

- **COleVariant (** *lbSrc* **)** 새 개체인 VT_EMPTY에 개체를복사합니다.`CLongBinary`

이에 대 한 자세한 내용은 Windows SDK의 [COM 오류 코드 구조](/windows/win32/com/structure-of-com-error-codes) 를 참조 하십시오.

##  <a name="changetype"></a>  COleVariant::ChangeType

이 `COleVariant` 개체의 변형 값 형식을 변환 합니다.

```
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```

### <a name="parameters"></a>매개 변수

*vartype*<br/>
이 `COleVariant` 개체의 VARTYPE입니다.

*pSrc*<br/>
변환할 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 개체에 대 한 포인터입니다. 이 값이 NULL 이면이 `COleVariant` 개체가 변환의 소스로 사용 됩니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK에서 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), [Varenum](/windows/win32/api/wtypes/ne-wtypes-varenum)및 [VariantChangeType](/windows/win32/api/oleauto/nf-oleauto-variantchangetype) 항목을 참조 하세요.

##  <a name="clear"></a>  COleVariant::Clear

지웁니다는 `VARIANT`합니다.

```
void Clear();
```

### <a name="remarks"></a>설명

그러면이 개체의 VARTYPE이 VT_EMPTY로 설정 됩니다. 소멸자 `COleVariant` 는이 함수를 호출 합니다.

자세한 내용은 Windows SDK의 `VARIANT`, VARTYPE 및 `VariantClear` 항목을 참조 하세요.

##  <a name="detach"></a>  COleVariant::Detach

이`COleVariant` 개체에서 기본 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 개체를 분리 합니다.

```
VARIANT Detach();
```

### <a name="remarks"></a>설명

이 함수는이 `COleVariant` 개체에 대 한 VARTYPE을 VT_EMPTY로 설정 합니다.

> [!NOTE]
>  를 호출한 `Detach`후 `VariantClear` 결과`VARIANT` 구조체에서를 호출 하는 것은 호출자의 책임입니다.

자세한 내용은 Windows SDK에서 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), [Varenum](/windows/win32/api/wtypes/ne-wtypes-varenum)및 [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) 항목을 참조 하세요.

##  <a name="getbytearrayfromvariantarray"></a>  COleVariant::GetByteArrayFromVariantArray

기존 variant 배열에서 바이트 배열을 검색 합니다.

```
void GetByteArrayFromVariantArray(CByteArray& bytes);
```

### <a name="parameters"></a>매개 변수

*bytes*<br/>
기존 [CByteArray](../../mfc/reference/cbytearray-class.md) 개체에 대 한 참조입니다.

##  <a name="operator_lpcvariant"></a>COleVariant:: operator LPCVARIANT

이 캐스팅 연산자는 값 `VARIANT` 이이 `COleVariant` 개체에서 복사 된 구조체를 반환 합니다.

```
operator LPCVARIANT() const;
```

### <a name="remarks"></a>설명

##  <a name="operator_lpvariant"></a>COleVariant:: operator LPVARIANT

이 캐스팅 연산자를 호출 하 여이 `VARIANT` `COleVariant` 개체의 기본 구조에 액세스 합니다.

```
operator LPVARIANT();
```

### <a name="remarks"></a>설명

> [!CAUTION]
> 이 함수에서 반환 하 `VARIANT` 는 포인터에 의해 액세스 되는 구조체의 값을 변경 하면이 개체 `COleVariant` 의 값이 변경 됩니다.

##  <a name="operator_eq"></a>  COleVariant::operator =

이러한 오버 로드 된 할당 연산자는 원본 값을 `COleVariant` 이 개체에 복사 합니다.

```
const COleVariant& operator=(const VARIANT& varSrc);
const COleVariant& operator=(LPCVARIANT pSrc);
const COleVariant& operator=(const COleVariant& varSrc);
const COleVariant& operator=(const LPCTSTR lpszSrc);
const COleVariant& operator=(const CString& strSrc);
const COleVariant& operator=(BYTE nSrc);
const COleVariant& operator=(short nSrc);
const COleVariant& operator=(long lSrc);
const COleVariant& operator=(const COleCurrency& curSrc);
const COleVariant& operator=(float fltSrc);
const COleVariant& operator=(double dblSrc);
const COleVariant& operator=(const COleDateTime& dateSrc);
const COleVariant& operator=(const CByteArray& arrSrc);
const COleVariant& operator=(const CLongBinary& lbSrc);
```

### <a name="remarks"></a>설명

각 연산자에 대 한 간략 한 설명은 다음과 같습니다.

- **operator = (** *varsrc* **)** 기존 VARIANT 또는 `COleVariant` 개체를이 개체에 복사 합니다.

- **operator = (** *psrc* **)** *Psrc* 에서 액세스 하는 변형 개체를이 개체에 복사 합니다.

- **연산자 = (** *lpszSrc* **)** Null로 끝나는 문자열을이 개체에 복사 하 고 VARTYPE을 VT_BSTR로 설정 합니다.

- **operator = (** *strsrc* **)** [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체를이 개체에 복사 하 고 VARTYPE을 VT_BSTR로 설정 합니다.

- **operator = (** *nsrc* **)** 8 비트 또는 16 비트 정수 값을이 개체에 복사 합니다. *Nsrc* 가 8 비트 값인 경우이의 VARTYPE은 VT_UI1로 설정 됩니다. *Nsrc* 가 16 비트 값이 고이의 VARTYPE이 VT_BOOL 경우 유지 됩니다. 그렇지 않으면 VT_I2로 설정 됩니다.

- **operator = (** *lsrc* **)** 32 비트 정수 값을이 개체에 복사 합니다. 이의 VARTYPE이 VT_ERROR 경우 유지 됩니다. 그렇지 않으면 VT_I4로 설정 됩니다.

- **연산자 = (** *cursrc* **)** [COleCurrency](../../mfc/reference/colecurrency-class.md) 개체를이 개체에 복사 하 고 VARTYPE을 VT_CY로 설정 합니다.

- **연산자 = (** *fltSrc* **)** 32 비트 부동 소수점 값을이 개체에 복사 하 고 VARTYPE을 VT_R4로 설정 합니다.

- **연산자 = (** *dblSrc* **)** 64 비트 부동 소수점 값을이 개체에 복사 하 고 VARTYPE을 VT_R8로 설정 합니다.

- **연산자 = (** *dateSrc* **)** [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체를이 개체에 복사 하 고 VARTYPE을 VT_DATE로 설정 합니다.

- **operator = (** *arrsrc* **)** [CByteArray](../../mfc/reference/cbytearray-class.md) 개체를이 `COleVariant` 개체에 복사 합니다.

- **연산자 = (** *lbSrc* **)** [CLongBinary](../../mfc/reference/clongbinary-class.md) 개체를이 `COleVariant` 개체에 복사 합니다.

자세한 내용은 Windows SDK에서 [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) 및 [varenum](/windows/win32/api/wtypes/ne-wtypes-varenum) 항목을 참조 하세요.

##  <a name="operator_eq_eq"></a>  COleVariant::operator ==

이 연산자는 두 variant 값을 비교 하 고 같으면 0이 아닌 값을 반환 합니다. 그렇지 않으면 0입니다.

```
BOOL operator==(const VARIANT& varSrc) const;
BOOL operator==(LPCVARIANT pSrc) const;
```

##  <a name="operator_lt_lt__gt_gt"></a>  COleVariant::operator &lt;&lt;, &gt;&gt;

`COleVariant` 또는 `COleVariant` `CArchive` `CArchive`에 대한값을출력하고에서개체를입력합니다.`CdumpContext`

```
friend CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    OleVariant varSrc);

friend CArchive& AFXAPI operator<<(
    CArchive& ar,
    COleVariant varSrc);

friend CArchive& AFXAPI operator>>(
    CArchive& ar,
    COleVariant& varSrc);
```

### <a name="remarks"></a>설명

삽입 `COleVariant` **(\<) 연산자는 진단 덤프를 지원 하 고 보관 파일에 저장 합니다.\<** 추출 ( **>>** ) 연산자는 보관 파일에서 로드를 지원 합니다.

##  <a name="setstring"></a>  COleVariant::SetString

문자열을 특정 형식으로 설정 합니다.

```
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```

### <a name="parameters"></a>매개 변수

*lpszSrc*<br/>
새 `COleVariant` 개체에 복사할 null 종료 문자열입니다.

*VtSrc*<br/>
새 `COleVariant` 개체에 대 한 VARTYPE입니다.

### <a name="remarks"></a>설명

*VtSrc* 매개 변수는 VT_BSTR (유니코드) 또는 VT_BSTRT (ANSI) 여야 합니다. `SetString`는 일반적으로 문자열 또는 문자열 포인터 매개 변수를 포함 하는 [COleVariant:: COleVariant](#colevariant) 생성자의 기본값이 며 VARTYPE은 유니코드가 아니기 때문에 문자열을 ANSI로 설정 하는 데 사용 됩니다.

유니코드가 아닌 빌드에서 DAO 레코드 집합을 사용할 경우 문자열은 ANSI로 예상 됩니다. 따라서 개체를 사용 `COleVariant` 하는 DAO 함수의 경우, 유니코드 레코드 집합을 만들지 않는 경우 *vtSrc* 이 VT로 설정 된 생성자의 **COleVariant:: COleVariant (** *lpszSrc* **,** *vtSrc* **)** 형식을 사용 해야 합니다. _BSTRT (ansi) 또는 `SetString` with *vtSrc* 를 VT_BSTRT로 설정 하 여 ansi 문자열을 만듭니다. 예를 들어 `CDaoRecordset` [CDaoRecordset:: Seek](../../mfc/reference/cdaorecordset-class.md#seek) 및 [CDaoRecordset:: SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) 함수는 개체 `COleVariant` 를 매개 변수로 사용 합니다. DAO 레코드 집합이 유니코드가 아니면 이러한 개체는 ANSI 여야 합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
