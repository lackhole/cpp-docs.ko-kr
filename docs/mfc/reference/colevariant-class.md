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
ms.openlocfilehash: 2b2d0935380caed8ad9d6741b9107a5f879f7903
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373312"
---
# <a name="colevariant-class"></a>COleVariant 클래스

[VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) 데이터 형식을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class COleVariant : public tagVARIANT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleVariant::COleVariant](#colevariant)|`COleVariant` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleVariant::Attach](#attach)|VARIANT를 연결 된 `COleVariant`합니다.|
|[COleVariant::ChangeType](#changetype)|이 변형 유형을 변경 `COleVariant` 개체입니다.|
|[COleVariant::Clear](#clear)|이 지우고 `COleVariant` 개체입니다.|
|[COleVariant::Detach](#detach)|변형에서 분리 된 `COleVariant` VARIANT를 반환 합니다.|
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|기존 variant 배열에서 바이트 배열을 검색합니다.|
|[COleVariant::SetString](#setstring)|특정 형식에 일반적으로 ANSI 문자열을 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[COleVariant::operator LPCVARIANT](#operator_lpcvariant)|변환 된 `COleVariant` 값에 `LPCVARIANT`.|
|[COleVariant::operator LPVARIANT](#operator_lpvariant)|변환 된 `COleVariant` 개체를 `LPVARIANT`합니다.|
|[COleVariant::operator =](#operator_eq)|복사본을 `COleVariant` 값입니다.|
|[COleVariant::operator ==](#operator_eq_eq)|두 `COleVariant` 값입니다.|
|[COleVariant::operator &lt;&lt;, &gt;&gt;](#operator_lt_lt__gt_gt)|출력을 `COleVariant` 값을 `CArchive` 또는 `CDumpContext` 입력을 `COleVariant` 에서 개체 `CArchive`합니다.|

## <a name="remarks"></a>설명

이 데이터 형식은 OLE 자동화에 사용 됩니다. 특히 합니다 [DISPPARAMS](/windows/desktop/api/oaidl/ns-oaidl-tagdispparams) 구조 VARIANT 구조의 배열에 대 한 포인터를 포함 합니다. A `DISPPARAMS` 구조는 매개 변수를 전달 하는 데 사용 됩니다 [idispatch:: Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)합니다.

> [!NOTE]
> 이 클래스에서 파생 되는 `VARIANT` 구조입니다. 즉, 전달할 수 있습니다는 `COleVariant` 필요로 하는 매개 변수를 `VARIANT` 하 고의 데이터 멤버를 `VARIANT` 구조는 액세스할 수 있는 데이터 멤버의 `COleVariant`합니다.

MFC 클래스와 관련 된 두 [COleCurrency](../../mfc/reference/colecurrency-class.md) 하 고 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 통화 variant 데이터 형식을 캡슐화 ( `VT_CY`) 및 날짜 ( `VT_DATE`). 합니다 `COleVariant` 클래스를 DAO 클래스에서 광범위 하 게 사용 됩니다; 예를 들어이 클래스의 일반적인 사용에 대 한 이러한 클래스를 참조 하세요 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 하 고 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다.

자세한 내용은 참조 하세요. 합니다 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [통화](/windows/desktop/api/wtypes/ns-wtypes-tagcy), [DISPPARAMS](/windows/desktop/api/oaidl/ns-oaidl-tagdispparams), 및 [idispatch:: Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) Windows SDK에는 항목입니다.

대 한 자세한 내용은 합니다 `COleVariant` 클래스 및 해당 OLE automation 사용 문서의 "전달 매개 변수에서 OLE Automation"을 참조 하세요. [Automation](../../mfc/automation.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagVARIANT`

`COleVariant`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

##  <a name="attach"></a>  COleVariant::Attach

연결 하려면이 함수를 호출 합니다 주어진 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) 개체를 현재 `COleVariant` 개체입니다.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>매개 변수

*varSrc*<br/>
기존 `VARIANT` 개체에 현재 연결할 `COleVariant` 개체입니다.

### <a name="remarks"></a>설명

이 함수는 설정의 VARTYPE *varSrc* 값을 vt_empty로 합니다.

자세한 내용은 참조는 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) 및 [VARENUM](/windows/desktop/api/wtypes/ne-wtypes-varenum) Windows SDK에는 항목입니다.

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
기존 `COleVariant` 나 `VARIANT` 복사할 새 개체 `COleVariant` 개체입니다.

*pSrc*<br/>
에 대 한 포인터를 `VARIANT` 개체를 새 복사 될 `COleVariant` 개체입니다.

*lpszSrc*<br/>
복사할 새 null로 끝나는 문자열을 `COleVariant` 개체입니다.

*vtSrc*<br/>
합니다 `VARTYPE` 새 `COleVariant` 개체입니다.

*strSrc*<br/>
A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체를 새 복사할 `COleVariant` 개체입니다.

*nSrc*하십시오 *lSrc* 복사할 새 숫자 값을 `COleVariant` 개체입니다.

*vtSrc*<br/>
합니다 `VARTYPE` 새 `COleVariant` 개체입니다.

*curSrc*<br/>
A [COleCurrency](../../mfc/reference/colecurrency-class.md) 개체를 새 복사할 `COleVariant` 개체입니다.

*fltSrc*, *dblSrc*<br/>
새 `COleVariant` 개체에 복사될 숫자 값입니다.

*timeSrc*<br/>
A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체를 새 복사할 `COleVariant` 개체입니다.

*arrSrc*<br/>
A [CByteArray](../../mfc/reference/cbytearray-class.md) 개체를 새 복사할 `COleVariant` 개체입니다.

*lbSrc*<br/>
A [CLongBinary](../../mfc/reference/clongbinary-class.md) 개체를 새 복사할 `COleVariant` 개체입니다.

*pidl*<br/>
에 대 한 포인터를 [ITEMIDLIST](/windows/desktop/api/shtypes/ns-shtypes-_itemidlist) 구조에 새 복사할 `COleVariant` 개체입니다.

### <a name="remarks"></a>설명

이러한 모든 생성자는 새로 만들기 `COleVariant` 개체를 지정된 된 값으로 초기화 합니다. 이 생성자의 각 간략 한 설명은 다음과 같습니다.

- **COleVariant ()** 빈 만듭니다 `COleVariant` VT_EMPTY 개체입니다.

- **COleVariant (** *varSrc* **)** 기존 복사 `VARIANT` 또는 `COleVariant` 개체입니다. 변형 형식이 유지됩니다.

- **COleVariant (** *pSrc* **)** 기존 복사 `VARIANT` 또는 `COleVariant` 개체입니다. 변형 형식이 유지됩니다.

- **COleVariant (** *lpszSrc* **)** 새 개체로 VT_BSTR (유니코드) 문자열을 복사 합니다.

- **COleVariant (** *lpszSrc* **하십시오** *vtSrc* **)** 새 개체에 문자열을 복사 합니다. 매개 변수 *vtSrc* VT_BSTR (유니코드) 또는 VT_BSTRT (ANSI) 여야 합니다.

- **COleVariant (** *strSrc* **)** 새 개체로 VT_BSTR (유니코드) 문자열을 복사 합니다.

- **COleVariant (** *nSrc* **)** VT_UI1 새 개체에는 8 비트 정수를 복사 합니다.

- **COleVariant (** *nSrc* **하십시오** *vtSrc* **)** 새 개체에는 16 비트 정수 또는 부울 값을 복사 합니다. 매개 변수 *vtSrc* VT_I2 또는 VT_BOOL 여야 합니다.

- **COleVariant (** *lSrc* **하십시오** *vtSrc* **)** 새 개체에는 32 비트 정수 (또는 SCODE 값)을 복사 합니다. 매개 변수 *vtSrc* VT_ERROR, VT_I4, VT_BOOL 이어야 합니다.

- **COleVariant (** *curSrc* **)** 복사본을 `COleCurrency` VT_CY 새 개체에는 값입니다.

- **COleVariant (** *fltSrc* **)** VT_R4 새 개체에는 32 비트 부동 소수점 값을 복사 합니다.

- **COleVariant (** *dblSrc* **)** VT_R8 새 개체에는 64 비트 부동 소수점 값을 복사 합니다.

- **COleVariant(** *timeSrc* **)** Copies a `COleDateTime` value into the new object, VT_DATE.

- **COleVariant (** *arrSrc* **)** 복사본을 `CByteArray` VT_EMPTY 새 개체에는 개체입니다.

- **COleVariant (** *lbSrc* **)** 복사본을 `CLongBinary` VT_EMPTY 새 개체에는 개체입니다.

SCODE에 대 한 자세한 내용은 참조 하세요. [COM 오류 코드 구조](/windows/desktop/com/structure-of-com-error-codes) Windows SDK에 있습니다.

##  <a name="changetype"></a>  COleVariant::ChangeType

이 변형 값의 형식을 변환 `COleVariant` 개체입니다.

```
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```

### <a name="parameters"></a>매개 변수

*vartype*<br/>
이 대 한 VARTYPE `COleVariant` 개체입니다.

*pSrc*<br/>
에 대 한 포인터를 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) 변환 될 개체입니다. 이 값이 NULL 이면이 `COleVariant` 개체 변환에 원본으로 사용 됩니다.

### <a name="remarks"></a>설명

자세한 내용은 참조는 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [VARENUM](/windows/desktop/api/wtypes/ne-wtypes-varenum), 및 [VariantChangeType](/windows/desktop/api/oleauto/nf-oleauto-variantchangetype) Windows SDK에는 항목.

##  <a name="clear"></a>  COleVariant::Clear

지웁니다는 `VARIANT`합니다.

```
void Clear();
```

### <a name="remarks"></a>설명

이 개체에 대 한 VARTYPE 값을 vt_empty로 설정합니다. `COleVariant` 소멸자는이 함수를 호출 합니다.

자세한 내용은 참조는 `VARIANT`, VARTYPE, 및 `VariantClear` Windows SDK에는 항목.

##  <a name="detach"></a>  COleVariant::Detach

기본 분리 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) 개체에서 `COleVariant` 개체입니다.

```
VARIANT Detach();
```

### <a name="remarks"></a>설명

이 함수는이 VARTYPE 설정 `COleVariant` VT_EMPTY 개체입니다.

> [!NOTE]
>  호출한 후 `Detach`은 호출 하는 호출자의 책임 `VariantClear` 결과에 `VARIANT` 구조입니다.

자세한 내용은 참조는 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [VARENUM](/windows/desktop/api/wtypes/ne-wtypes-varenum), 및 [VariantClear](/windows/desktop/api/oleauto/nf-oleauto-variantclear) Windows SDK에는 항목.

##  <a name="getbytearrayfromvariantarray"></a>  COleVariant::GetByteArrayFromVariantArray

기존 variant 배열에서 바이트 배열을 검색합니다

```
void GetByteArrayFromVariantArray(CByteArray& bytes);
```

### <a name="parameters"></a>매개 변수

*bytes*<br/>
기존에 대 한 참조가 [CByteArray](../../mfc/reference/cbytearray-class.md) 개체입니다.

##  <a name="operator_lpcvariant"></a>  COleVariant::operator LPCVARIANT

이 캐스팅 연산자를 반환 합니다는 `VARIANT` 값이 복사 됩니다 구조 `COleVariant` 개체입니다.

```
operator LPCVARIANT() const;
```

### <a name="remarks"></a>설명

##  <a name="operator_lpvariant"></a>  COleVariant::operator LPVARIANT

기본 액세스 하려면이 캐스팅 연산자를 호출 `VARIANT` 이 대 한 구조 `COleVariant` 개체입니다.

```
operator LPVARIANT();
```

### <a name="remarks"></a>설명

> [!CAUTION]
> 값을 변경 합니다 `VARIANT` 이 함수에서 반환 된 포인터에 의해 액세스 되는 구조는이 값을 변경 `COleVariant` 개체입니다.

##  <a name="operator_eq"></a>  COleVariant::operator =

이러한 오버 로드 된 할당 연산자 복사 원본 값이 `COleVariant` 개체입니다.

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

각 연산자에 대 한 간단한 설명은 다음과 같습니다.

- **operator = (** *varSrc* **)** 는 기존 변형에 복사 또는 `COleVariant` 개체로이 개체입니다.

- **operator = (** *pSrc* **)** 복사 하 여 액세스 하는 VARIANT 개체 *pSrc* 이 개체로.

- **operator = (** *lpszSrc* **)** 이 개체에는 null로 끝나는 문자열을 복사 하 고 VARTYPE VT_BSTR를 설정 합니다.

- **연산자 = (** *strSrc* **)** 복사본을 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체로이 개체 및 VARTYPE VT_BSTR로 설정 합니다.

- **operator = (** *nSrc* **)** 8 또는 16 비트 정수 값이이 개체에 복사 합니다. 하는 경우 *nSrc* 는 8 비트 값이 VARTYPE VT_UI1로 설정 됩니다. 하는 경우 *nSrc* 16 비트 값이 VARTYPE 이며 VT_BOOL, 그렇지 않으면 유지, VT_I2로 설정 됩니다.

- **operator = (** *lSrc* **)** 32 비트 정수 값을이 개체에 복사 합니다. 이 VARTYPE VT_ERROR 경우 유지 됩니다. 그렇지 않으면 VT_I4에 설정 됩니다.

- **연산자 = (** *curSrc* **)** 복사본을 [COleCurrency](../../mfc/reference/colecurrency-class.md) 개체로이 개체 및 VARTYPE VT_CY 설정 합니다.

- **operator = (** *fltSrc* **)** 이 개체에는 32 비트 부동 소수점 값을 복사 하 고 VARTYPE VT_R4를 설정 합니다.

- **operator = (** *dblSrc* **)** 이 개체에는 64 비트 부동 소수점 값을 복사 하 고 VARTYPE VT_R8를 설정 합니다.

- **연산자 = (** *dateSrc* **)** 복사본을 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체로이 개체 및 VARTYPE VT_DATE 설정 합니다.

- **operator = (** *arrSrc* **)** 복사본을 [CByteArray](../../mfc/reference/cbytearray-class.md) 이 개체로 `COleVariant` 개체입니다.

- **operator = (** *lbSrc* **)** 복사본을 [CLongBinary](../../mfc/reference/clongbinary-class.md) 이 개체로 `COleVariant` 개체입니다.

자세한 내용은 참조는 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) 및 [VARENUM](/windows/desktop/api/wtypes/ne-wtypes-varenum) Windows SDK에는 항목입니다.

##  <a name="operator_eq_eq"></a>  COleVariant::operator ==

두 variant 값을 비교 하 고 같지 않은 경우 0이 아닌 값을 반환 하는이 연산자 그렇지 않으면 0입니다.

```
BOOL operator==(const VARIANT& varSrc) const;
BOOL operator==(LPCVARIANT pSrc) const;
```

##  <a name="operator_lt_lt__gt_gt"></a>  COleVariant::operator &lt;&lt;, &gt;&gt;

출력을 `COleVariant` 값을 `CArchive` 또는 `CdumpContext` 입력을 `COleVariant` 에서 개체 `CArchive`합니다.

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

합니다 `COleVariant` 삽입 (**\<\<**) 연산자 지원 진단 덤프 및 보관에 저장 합니다. 추출 (**>>**) 연산자는 보관 파일에서 로드를 지원 합니다.

##  <a name="setstring"></a>  COleVariant::SetString

특정 형식으로 문자열을 설정합니다.

```
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```

### <a name="parameters"></a>매개 변수

*lpszSrc*<br/>
복사할 새 null로 끝나는 문자열을 `COleVariant` 개체입니다.

*VtSrc*<br/>
새 VARTYPE `COleVariant` 개체입니다.

### <a name="remarks"></a>설명

매개 변수 *vtSrc* VT_BSTR (유니코드) 또는 VT_BSTRT (ANSI) 여야 합니다. `SetString` 에 대 한 기본 이후 ansi 문자열을 설정 하려면 일반적으로 사용 됩니다 합니다 [COleVariant::COleVariant](#colevariant) 문자열 또는 문자열 포인터 매개 변수 및 없습니다 VARTYPE 생성자는 유니코드입니다.

유니코드가 아닌 빌드에서 DAO 레코드 집합에는 ANSI 하는 문자열은 필요 합니다. 따라서 DAO 사용 하는 함수 `COleVariant` 를 사용 해야 개체를 유니코드 레코드 집합을 만들지 않는 경우에 **COleVariant::COleVariant (** *lpszSrc* **,** *vtSrc* **)** 사용 하 여 생성자 형태의 *vtSrc* VT_BSTRT (ANSI)를 설정 하거나 사용 하 여 `SetString` 사용 하 여 *vtSrc* VT로 설정 _BSTRT ANSI 문자열을 확인 합니다. 예를 들어 합니다 `CDaoRecordset` 함수 [CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek) 하 고 [CDaoRecordset::SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) 사용 하 여 `COleVariant` 개체를 매개 변수로 합니다. 이러한 개체는 DAO 레코드 집합 유니코드가 아닌 경우 ANSI 이어야 합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
