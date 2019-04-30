---
title: COleSafeArray 클래스
ms.date: 08/27/2018
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
helpviewer_keywords:
- COleSafeArray [MFC], COleSafeArray
- COleSafeArray [MFC], AccessData
- COleSafeArray [MFC], AllocData
- COleSafeArray [MFC], AllocDescriptor
- COleSafeArray [MFC], Attach
- COleSafeArray [MFC], Clear
- COleSafeArray [MFC], Copy
- COleSafeArray [MFC], Create
- COleSafeArray [MFC], CreateOneDim
- COleSafeArray [MFC], Destroy
- COleSafeArray [MFC], DestroyData
- COleSafeArray [MFC], DestroyDescriptor
- COleSafeArray [MFC], Detach
- COleSafeArray [MFC], GetByteArray
- COleSafeArray [MFC], GetDim
- COleSafeArray [MFC], GetElement
- COleSafeArray [MFC], GetElemSize
- COleSafeArray [MFC], GetLBound
- COleSafeArray [MFC], GetOneDimSize
- COleSafeArray [MFC], GetUBound
- COleSafeArray [MFC], Lock
- COleSafeArray [MFC], PtrOfIndex
- COleSafeArray [MFC], PutElement
- COleSafeArray [MFC], Redim
- COleSafeArray [MFC], ResizeOneDim
- COleSafeArray [MFC], UnaccessData
- COleSafeArray [MFC], Unlock
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
ms.openlocfilehash: 0833dca9311689063c2ebeadd3942d9f5ce376e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224425"
---
# <a name="colesafearray-class"></a>COleSafeArray 클래스

임의의 형식 및 차원 배열 작업용 클래스입니다.

## <a name="syntax"></a>구문

```
class COleSafeArray : public tagVARIANT
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleSafeArray::COleSafeArray](#colesafearray)|`COleSafeArray` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleSafeArray::AccessData](#accessdata)|배열 데이터에 대 한 포인터를 검색합니다.|
|[COleSafeArray::AllocData](#allocdata)|배열에 대 한 메모리를 할당합니다.|
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|안전 배열 설명자에 대 한 메모리를 할당합니다.|
|[COleSafeArray::Attach](#attach)|기존 제어할 `VARIANT` 배열을 `COleSafeArray` 개체입니다.|
|[COleSafeArray::Clear](#clear)|내부에서 모든 데이터를 해제 `VARIANT`합니다.|
|[COleSafeArray::Copy](#copy)|기존 배열의 복사본을 만듭니다.|
|[COleSafeArray::Create](#create)|안전 배열을 만듭니다.|
|[COleSafeArray::CreateOneDim](#createonedim)|1 차원 만듭니다 `COleSafeArray` 개체입니다.|
|[COleSafeArray::Destroy](#destroy)|기존 배열이 제거합니다.|
|[COleSafeArray::DestroyData](#destroydata)|안전 배열에서 데이터를 제거합니다.|
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|안전 배열 설명자를 제거합니다.|
|[COleSafeArray::Detach](#detach)|VARIANT 배열에서 분리 된 `COleSafeArray` 개체 (데이터 해제 되지 것입니다).|
|[COleSafeArray::GetByteArray](#getbytearray)|안전 배열의 내용을 복사 합니다는 [CByteArray](../../mfc/reference/cbytearray-class.md)합니다.|
|[COleSafeArray::GetDim](#getdim)|배열의 차원 수를 반환합니다.|
|[COleSafeArray::GetElement](#getelement)|안전 배열의 단일 요소를 검색 합니다.|
|[COleSafeArray::GetElemSize](#getelemsize)|안전 배열에 하나의 요소를 바이트 단위로 크기를 반환 합니다.|
|[COleSafeArray::GetLBound](#getlbound)|안전 배열의 모든 차원에 대 한 하한값을 반환합니다.|
|[COleSafeArray::GetOneDimSize](#getonedimsize)|1 차원에서 요소의 수를 반환 합니다. `COleSafeArray` 개체입니다.|
|[COleSafeArray::GetUBound](#getubound)|안전 배열의 모든 차원에 대 한 상한 값을 반환합니다.|
|[COleSafeArray::Lock](#lock)|배열의 잠금 횟수를 증가 시킵니다 배열 설명자에 배열 데이터에 대 한 포인터를 놓습니다.|
|[COleSafeArray::PtrOfIndex](#ptrofindex)|인덱싱된 요소에 대 한 포인터를 반환합니다.|
|[COleSafeArray::PutElement](#putelement)|단일 요소를 배열에 할당합니다.|
|[COleSafeArray::Redim](#redim)|안전 배열의 최하위 (오른쪽) 경계를 변경합니다.|
|[COleSafeArray::ResizeOneDim](#resizeonedim)|1 차원 요소 수가 변경 `COleSafeArray` 개체입니다.|
|[COleSafeArray::UnaccessData](#unaccessdata)|잠금을 배열의 수를 감소 하 여 검색 포인터를 무효화 `AccessData`합니다.|
|[COleSafeArray::Unlock](#unlock)|잠금 횟수를 줄입니다 배열 해제 하거나 크기 조정할 수 있도록 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|기본 액세스 `VARIANT` 구조는 `COleSafeArray` 개체입니다.|
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|기본 액세스 `VARIANT` 구조는 `COleSafeArray` 개체입니다.|
|[COleSafeArray::operator =](#operator_eq)|값을 복사를 `COleSafeArray` 개체 (`SAFEARRAY`를 `VARIANT`를 `COleVariant`, 또는 `COleSafeArray` 배열)입니다.|
|[COleSafeArray::operator ==](#operator_eq_eq)|Variant 두 배열을 비교 (`SAFEARRAY`, `VARIANT`를 `COleVariant`, 또는 `COleSafeArray` 배열)입니다.|
|[COleSafeArray::operator &lt;&lt;](#operator_lt_lt)|내용을 출력 한 `COleSafeArray` 덤프 컨텍스트 개체입니다.|

## <a name="remarks"></a>설명

`COleSafeArray` 파생 된 ole에서 `VARIANT` 구조입니다. OLE `SAFEARRAY` 멤버 함수를 통해 사용할 수 있는 `COleSafeArray`뿐만 아니라 1 차원 바이트 배열을 위해 특별히 설계 된 멤버 함수 집합으로 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

##  <a name="accessdata"></a>  COleSafeArray::AccessData

배열 데이터에 대 한 포인터를 검색합니다.

```
void AccessData(void** ppvData);
```

### <a name="parameters"></a>매개 변수

*ppvData*<br/>
배열 데이터에 대 한 포인터에 대 한 포인터입니다.

### <a name="remarks"></a>설명

함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

##  <a name="allocdata"></a>  COleSafeArray::AllocData

안전 배열에 대 한 메모리를 할당합니다.

```
void AllocData();
```

### <a name="remarks"></a>설명

함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.

##  <a name="allocdescriptor"></a>  COleSafeArray::AllocDescriptor

안전 배열 설명자에 대 한 메모리를 할당합니다.

```
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>매개 변수

*dwDims*<br/>
안전 배열의 차원 수입니다.

### <a name="remarks"></a>설명

함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.

##  <a name="attach"></a>  COleSafeArray::Attach

기존 데이터의 제어할 `VARIANT` 배열을 `COleSafeArray` 개체입니다.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>매개 변수

*varSrc*<br/>
`VARIANT` 개체입니다. 합니다 *varSrc* 매개 변수에 VARTYPE 있어야 [VT_ARRAY](/windows/desktop/api/wtypes/ne-wtypes-varenum)합니다.

### <a name="remarks"></a>설명

원본 `VARIANT`의 형식 값을 vt_empty로 설정 됩니다. 있는 경우이 함수는 현재 배열 데이터를 지웁니다.

### <a name="example"></a>예제

  예를 참조 하세요 [COleSafeArray::AccessData](#accessdata)합니다.

##  <a name="clear"></a>  COleSafeArray::Clear

안전 배열의 지웁니다.

```
void Clear();
```

### <a name="remarks"></a>설명

함수를 설정 하 여 안전 배열 지웁니다는 `VARTYPE` VT_EMPTY 개체의 합니다. 현재 내용이 릴리스되고 배열 해제 됩니다.

##  <a name="colesafearray"></a>  COleSafeArray::COleSafeArray

`COleSafeArray` 개체를 생성합니다.

```
COleSafeArray();

COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);

COleSafeArray(const COleSafeArray& saSrc);
COleSafeArray(const VARIANT& varSrc);
  COleSafeArray(LPCVARIANT pSrc);
COleSafeArray(const COleVariant& varSrc);
```

### <a name="parameters"></a>매개 변수

*saSrc*<br/>
기존 `COleSafeArray` 개체 또는 `SAFEARRAY` 복사할 새 `COleSafeArray` 개체입니다.

*vtSrc*<br/>
새 VARTYPE `COleSafeArray` 개체입니다.

*psaSrc*<br/>
에 대 한 포인터를 `SAFEARRAY` 복사할 새 `COleSafeArray` 개체입니다.

*varSrc*<br/>
기존 `VARIANT` 나 `COleVariant` 복사할 새 개체 `COleSafeArray` 개체입니다.

*pSrc*<br/>
에 대 한 포인터를 `VARIANT` 복사할 새 개체 `COleSafeArray` 개체입니다.

### <a name="remarks"></a>설명

이 생성자의 모든 새로 만들기 `COleSafeArray` 개체입니다. 매개 변수가 없을 경우 빈 경우 `COleSafeArray` 개체 (VT_EMPTY) 만들어집니다. 경우는 `COleSafeArray` 해당 VARTYPE 암시적으로 알려진 다른 배열에서 복사 됩니다 (을 `COleSafeArray`를 `COleVariant`, 또는 `VARIANT`), 소스 배열의 VARTYPE 유지 되 고 지정할 필요가 없습니다. 경우는 `COleSafeArray` 인 VARTYPE 알려지지 않은 다른 배열에서 복사 됩니다 (`SAFEARRAY`), VARTYPE 지정 해야 합니다 *vtSrc* 매개 변수.

함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.

##  <a name="copy"></a>  COleSafeArray::Copy

기존 안전 배열의 복사본을 만듭니다.

```
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>매개 변수

*ppsa*<br/>
새 배열 설명자를 반환 하는 위치에 대 한 포인터입니다.

### <a name="remarks"></a>설명

함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.

##  <a name="create"></a>  COleSafeArray::Create

할당 하 고 배열에 대 한 데이터를 초기화 합니다.

```
void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    DWORD* rgElements);

void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    SAFEARRAYBOUND* rgsabounds);
```

### <a name="parameters"></a>매개 변수

*vtSrc*<br/>
기본 형식 (즉, 각 배열 요소의 VARTYPE) 배열입니다. VARTYPE variant 형식의 하위 집합으로 제한 됩니다. VT_ARRAY 아니고 VT_BYREF 플래그를 설정할 수 있습니다. VT_EMPTY 및 VT_NULL는 배열에 대 한 유효한 기본 형식이 아닙니다. 다른 모든 형식이 올바릅니다.

*dwDims*<br/>
배열의 차원 수입니다. 배열을 사용 하 여 만들어진 후 변경할 수 있습니다 [Redim](#redim)합니다.

*rgElements*<br/>
배열의 각 차원에 대 한 요소 수의 배열에 대 한 포인터입니다.

*rgsabounds*<br/>
벡터의 범위 (각 차원에 대해 하나)에 대 한 포인터 배열에 대해 할당할 수 있습니다.

### <a name="remarks"></a>설명

필요한 경우이 함수는 현재 배열의 데이터를 지웁니다. 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="createonedim"></a>  COleSafeArray::CreateOneDim

새 1 차원 `COleSafeArray` 개체입니다.

```
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>매개 변수

*vtSrc*<br/>
기본 형식 (즉, 각 배열 요소의 VARTYPE) 배열입니다.

*dwElements*<br/>
배열의 요소 수입니다. 배열을 사용 하 여 만들어진 후 변경할 수 있습니다 [ResizeOneDim](#resizeonedim)합니다.

*pvSrcData*<br/>
배열에 복사 하려면 데이터에 대 한 포인터입니다.

*nLBound*<br/>
배열의 하한값입니다.

### <a name="remarks"></a>설명

할당 하 고 경우에 지정된 된 데이터를 복사 하 여 배열에 대 한 데이터를 초기화 하는 함수 포인터 *pvSrcData* NULL이 아닙니다.

함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

##  <a name="destroy"></a>  COleSafeArray::Destroy

기존 배열 설명자와 배열에 있는 모든 데이터를 제거합니다.

```
void Destroy();
```

### <a name="remarks"></a>설명

개체 배열에 저장 되며, 각 개체 해제 됩니다. 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.

##  <a name="destroydata"></a>  COleSafeArray::DestroyData

안전 배열에서 모든 데이터를 제거합니다.

```
void DestroyData();
```

### <a name="remarks"></a>설명

개체 배열에 저장 되며, 각 개체 해제 됩니다. 함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.

##  <a name="destroydescriptor"></a>  COleSafeArray::DestroyDescriptor

안전 배열 설명자를 제거합니다.

```
void DestroyDescriptor();
```

### <a name="remarks"></a>설명

함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.

##  <a name="detach"></a>  COleSafeArray::Detach

분리 된 `VARIANT` 데이터로 `COleSafeArray` 개체입니다.

```
VARIANT Detach();
```

### <a name="return-value"></a>반환 값

내부 `VARIANT` 값을 `COleSafeArray` 개체입니다.

### <a name="remarks"></a>설명

함수 개체의 VARTYPE 값을 vt_empty로 설정 하 여 안전 하 게 배열에서 데이터를 분리 합니다. Windows 함수를 호출 하 여 배열 해제를 호출자의 책임 [VariantClear](/windows/desktop/api/oleauto/nf-oleauto-variantclear)합니다.

함수에서 오류를 throw 한 [COleException](../../mfc/reference/coleexception-class.md)합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [COleSafeArray::PutElement](#putelement)합니다.

##  <a name="getbytearray"></a>  COleSafeArray::GetByteArray

안전 배열의 내용을 복사는 `CByteArray`합니다.

```
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>매개 변수

*bytes*<br/>
에 대 한 참조를 [CByteArray](../../mfc/reference/cbytearray-class.md) 개체입니다.

##  <a name="getdim"></a>  COleSafeArray::GetDim

차원 수를 반환 합니다 `COleSafeArray` 개체입니다.

```
DWORD GetDim();
```

### <a name="return-value"></a>반환 값

안전 배열의 차원 수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="getelement"></a>  COleSafeArray::GetElement

안전 배열의 단일 요소를 검색 합니다.

```
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>매개 변수

*rgIndices*<br/>
각 배열 차원의 인덱스 배열에 대한 포인터입니다.

*pvData*<br/>
배열의 요소를 배치할 위치에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 함수는 자동으로 windows 함수 호출 `SafeArrayLock` 고 `SafeArrayUnlock` 앞과 뒤 요소를 검색 합니다. 데이터 요소가 문자열, 개체 또는 variant 이면 함수는 올바른 방법은의 요소를 복사 합니다. 매개 변수 *pvData* 가리켜야 하는 많은 요소를 포함 하도록 충분 한 버퍼입니다.

함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

##  <a name="getelemsize"></a>  COleSafeArray::GetElemSize

에 있는 요소의 크기를 검색 한 `COleSafeArray` 개체입니다.

```
DWORD GetElemSize();
```

### <a name="return-value"></a>반환 값

안전 배열 요소의 바이트 크기입니다.

##  <a name="getlbound"></a>  COleSafeArray::GetLBound

모든 차원에 대 한 하한값을 반환을 `COleSafeArray` 개체입니다.

```
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>매개 변수

*dwDim*<br/>
하한값을 가져올 배열 차원입니다.

*pLBound*<br/>
하한값을 반환할 위치에 대 한 포인터입니다.

### <a name="remarks"></a>설명

함수에서 오류를 throw 한 [COleException](../../mfc/reference/coleexception-class.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

##  <a name="getonedimsize"></a>  COleSafeArray::GetOneDimSize

1 차원에서 요소의 수를 반환 합니다. `COleSafeArray` 개체입니다.

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>반환 값

1 차원 안전 배열에서 요소의 수입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [COleSafeArray::CreateOneDim](#createonedim)합니다.

##  <a name="getubound"></a>  COleSafeArray::GetUBound

안전 배열의 모든 차원에 대 한 상한 값을 반환합니다.

```
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>매개 변수

*dwDim*<br/>
상한 값을 가져올 배열 차원입니다.

*pUBound*<br/>
상한 값을 반환할 위치에 대 한 포인터입니다.

### <a name="remarks"></a>설명

함수에서 오류를 throw 한 [COleException](../../mfc/reference/coleexception-class.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

##  <a name="lock"></a>  COleSafeArray::Lock

배열 및 위치에 대 한 포인터 배열 설명자에 배열 데이터의 잠금 수를 늘립니다.

```
void Lock();
```

### <a name="remarks"></a>설명

오류 시 throw 된 [COleException](../../mfc/reference/coleexception-class.md)합니다.

배열 설명자에 대 한 포인터가 유효 기간 `Unlock` 라고 합니다. 에 대 한 호출 `Lock` 중첩 될 수 있습니다; 동일한 수에 대 한 호출의 `Unlock` 필요 합니다.

잠겨 있는 동안에 배열을 삭제할 수 없습니다.

##  <a name="operator_lpcvariant"></a>  COleSafeArray::operator LPCVARIANT

기본 액세스 하려면이 캐스팅 연산자를 호출 `VARIANT` 이 대 한 구조 `COleSafeArray` 개체입니다.

```
operator LPCVARIANT() const;
```

##  <a name="operator_lpvariant"></a>  COleSafeArray::operator LPVARIANT

기본 액세스 하려면이 캐스팅 연산자를 호출 `VARIANT` 이 대 한 구조 `COleSafeArray` 개체입니다.

```
operator LPVARIANT();
```

### <a name="remarks"></a>설명

값을 변경 합니다 `VARIANT` 이 함수에서 반환 된 포인터에 의해 액세스 되는 구조는이 값을 변경 `COleSafeArray` 개체입니다.

##  <a name="operator_eq"></a>  COleSafeArray::operator =

이러한 오버 로드 된 할당 연산자 복사 원본 값이 `COleSafeArray` 개체입니다.

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
  COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>설명

각 연산자에 대 한 간단한 설명은 다음과 같습니다.

- **operator = (** *saSrc* **)** 기존 복사 `COleSafeArray` 개체로이 개체입니다.

- **operator = (** *varSrc* **)** 기존 복사 `VARIANT` 또는 `COleVariant` 이 개체 배열입니다.

- **연산자 = (** *pSrc* **)** 복사본을 `VARIANT` 액세스 하는 배열 개체 *pSrc* 이 개체로 합니다.

##  <a name="operator_eq_eq"></a>  COleSafeArray::operator ==

이 연산자는 두 배열을 비교 (`SAFEARRAY`, `VARIANT`를 `COleVariant`, 또는 `COleSafeArray` 배열) 같으면 0이 고 그렇지 않은 경우 0이 아닌 값을 반환 합니다.

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>설명

두 배열은 동일한 수의 차원, 동일한 크기의 각 차원과 같은 요소 값을 가질 경우 동일 합니다.

##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;

`COleSafeArray` 삽입 (<<) 연산자 지원 진단 덤프 및 저장을 `COleSafeArray` 보관 하는 개체입니다.

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex

인덱스 값으로 지정 된 요소에 대 한 포인터를 반환 합니다.

```
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>매개 변수

*rgIndices*<br/>
배열의 요소를 식별 하는 인덱스 값의 배열입니다. 요소에 대 한 모든 인덱스를 지정 해야 합니다.

*ppvData*<br/>
값에 의해 식별 되는 요소에 대 한 포인터를 반환 되는 경우에 *rgIndices*합니다.

##  <a name="putelement"></a>  COleSafeArray::PutElement

단일 요소를 배열에 할당합니다.

```
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>매개 변수

*rgIndices*<br/>
각 배열 차원의 인덱스 배열에 대한 포인터입니다.

*pvData*<br/>
배열에 할당할 데이터에 대한 포인터입니다. VT_DISPATCH 고 VT_UNKNOWN, VT_BSTR variant 형식은 포인터 이며 다른 수준의 간접 참조가 필요 하지 않습니다.

### <a name="remarks"></a>설명

이 함수는 자동으로 Windows 함수 호출 [SafeArrayLock](/windows/desktop/api/oleauto/nf-oleauto-safearraylock) 하 고 [SafeArrayUnlock](/windows/desktop/api/oleauto/nf-oleauto-safearrayunlock) 앞과 뒤 요소를 할당 합니다. 데이터 요소가 문자열, 개체 또는 Variant이면 함수는 이를 올바르게 복사하고 기존 요소가 문자열, 개체 또는 Variant이면 제대로 지워집니다.

배열에는 여러 잠금이 있을 수 있으므로 다른 작업에 의해 배열이 잠긴 동안 요소를 배열에 삽입할 수 있습니다.

함수에서 오류를 throw 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

##  <a name="redim"></a>  COleSafeArray::Redim

안전 배열의 최하위 (오른쪽) 경계를 변경합니다.

```
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>매개 변수

*psaboundNew*<br/>
새 안전 배열에 대 한 포인터를 새 배열 범위를 포함 하는 구조체가 바인딩됩니다. 배열의 최소 유효 치수만 변경할 수 있습니다.

### <a name="remarks"></a>설명

함수에서 오류를 throw 한 [COleException](../../mfc/reference/coleexception-class.md)합니다.

##  <a name="resizeonedim"></a>  COleSafeArray::ResizeOneDim

1 차원 요소 수가 변경 `COleSafeArray` 개체입니다.

```
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>매개 변수

*dwElements*<br/>
1 차원 안전 배열의 요소 수입니다.

### <a name="remarks"></a>설명

함수에서 오류를 throw 한 [COleException](../../mfc/reference/coleexception-class.md)합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [COleSafeArray::CreateOneDim](#createonedim)합니다.

##  <a name="unaccessdata"></a>  COleSafeArray::UnaccessData

잠금을 배열의 수를 감소 하 여 검색 포인터를 무효화 `AccessData`합니다.

```
void UnaccessData();
```

### <a name="remarks"></a>설명

함수에서 오류를 throw 한 [COleException](../../mfc/reference/coleexception-class.md)합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [COleSafeArray::AccessData](#accessdata)합니다.

##  <a name="unlock"></a>  COleSafeArray::Unlock

잠금 횟수를 줄입니다 배열 해제 하거나 크기 조정할 수 있도록 합니다.

```
void Unlock();
```

### <a name="remarks"></a>설명

이 함수는 배열에 있는 데이터에 대 한 액세스 완료 된 후 호출 됩니다. 오류 시 throw 된 [COleException](../../mfc/reference/coleexception-class.md)합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleVariant 클래스](../../mfc/reference/colevariant-class.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)<br/>
[CDatabase 클래스](../../mfc/reference/cdatabase-class.md)<br/>
