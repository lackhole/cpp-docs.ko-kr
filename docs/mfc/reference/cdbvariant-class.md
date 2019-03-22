---
title: CDBVariant 클래스
ms.date: 11/04/2016
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
helpviewer_keywords:
- CDBVariant [MFC], CDBVariant
- CDBVariant [MFC], Clear
- CDBVariant [MFC], m_dwType
- CDBVariant [MFC], m_boolVal
- CDBVariant [MFC], m_chVal
- CDBVariant [MFC], m_dblVal
- CDBVariant [MFC], m_fltVal
- CDBVariant [MFC], m_iVal
- CDBVariant [MFC], m_lVal
- CDBVariant [MFC], m_pbinary
- CDBVariant [MFC], m_pdate
- CDBVariant [MFC], m_pstring
- CDBVariant [MFC], m_pstringA
- CDBVariant [MFC], m_pstringW
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
ms.openlocfilehash: 48a2e08d056e3bfef8a06b80ae6607947923cbcb
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328950"
---
# <a name="cdbvariant-class"></a>CDBVariant 클래스

MFC ODBC 클래스의 variant 데이터 형식을 나타냅니다.

## <a name="syntax"></a>구문

```
class CDBVariant
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDBVariant::CDBVariant](#cdbvariant)|`CDBVariant` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDBVariant::Clear](#clear)|지웁니다는 `CDBVariant` 개체입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDBVariant::m_dwType](#m_dwtype)|현재 저장 된 값의 데이터 형식을 포함합니다. `DWORD`을 입력합니다.|

### <a name="public-union-members"></a>공용 공용 구조체 멤버

|이름|설명|
|----------|-----------------|
|[CDBVariant::m_boolVal](#m_boolval)|형식의 값을 포함 **BOOL**합니다.|
|[CDBVariant::m_chVal](#m_chval)|형식의 값을 포함 **unsigned char**합니다.|
|[CDBVariant::m_dblVal](#m_dblval)|형식의 값을 포함 **이중**합니다.|
|[CDBVariant::m_fltVal](#m_fltval)|형식의 값을 포함 **float**합니다.|
|[CDBVariant::m_iVal](#m_ival)|형식의 값을 포함 **짧은**합니다.|
|[CDBVariant::m_lVal](#m_lval)|형식의 값을 포함 **긴**합니다.|
|[CDBVariant::m_pbinary](#m_pbinary)|형식의 개체에 대 한 포인터를 포함 `CLongBinary`합니다.|
|[CDBVariant::m_pdate](#m_pdate)|형식의 개체에 대 한 포인터를 포함 **TIMESTAMP_STRUCT**합니다.|
|[CDBVariant::m_pstring](#m_pstring)|형식의 개체에 대 한 포인터를 포함 `CString`합니다.|
|[CDBVariant::m_pstringA](#m_pstringa)|ASCII에 대 한 포인터를 저장 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.|
|[CDBVariant::m_pstringW](#m_pstringw)|저장 된 차원에 대 한 포인터 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.|

## <a name="remarks"></a>설명

`CDBVariant` 기본 클래스는 없습니다.

`CDBVariant` 비슷합니다 [COleVariant](../../mfc/reference/colevariant-class.md)그러나 `CDBVariant` OLE를 사용 하지 않습니다. `CDBVariant` 값의 데이터 형식에 대 한 걱정 없이 값을 저장할 수 있습니다. `CDBVariant` 데이터 형식의 공용 구조체에 저장 된 현재 값을 추적 합니다.

클래스 [CRecordset](../../mfc/reference/crecordset-class.md) 활용 `CDBVariant` 의 세 멤버 함수가 개체: `GetFieldValue`를 `GetBookmark`, 및 `SetBookmark`합니다. 예를 들어 `GetFieldValue` 동적으로 열에 데이터를 가져올 수 있습니다. 열의 데이터 형식을 런타임에 확인할 수 없는 때문 `GetFieldValue` 사용을 `CDBVariant` 열의 데이터를 저장 하는 개체입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CDBVariant`

## <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

##  <a name="cdbvariant"></a>  CDBVariant::CDBVariant

NULL 만듭니다 `CDBVariant` 개체입니다.

```
CDBVariant();
```

### <a name="remarks"></a>설명

설정 된 [m_dwType](#m_dwtype) DBVT_NULL 데이터 멤버입니다.

##  <a name="clear"></a>  CDBVariant::Clear

선택을 취소 하려면이 멤버 함수를 호출 합니다 `CDBVariant` 개체입니다.

```
void Clear();
```

### <a name="remarks"></a>설명

하는 경우의 값을 [m_dwType](#m_dwtype) DBVT_DATE, DBVT_STRING, 또는 DBVT_BINARY, 데이터 멤버는 `Clear` 공용 구조체 포인터 멤버에 연결 된 메모리를 해제 합니다. `Clear` 설정 `m_dwType` DBVT_NULL 하 합니다.

합니다 `CDBVariant` 소멸자 호출 `Clear`합니다.

##  <a name="m_boolval"></a>  CDBVariant::m_boolVal

BOOL 형식의 값을 저장합니다.

### <a name="remarks"></a>설명

`m_boolVal` 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 `m_boolVal`, 먼저 값을 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 한 다음, DBVT_BOOL로 `m_boolVal` 에 액세스 하 고, 그렇지 않으면 올바른 값이 포함 됩니다 `m_boolVal` 신뢰할 수 없는 결과가 생성 됩니다.

##  <a name="m_chval"></a>  CDBVariant::m_chVal

형식의 값을 저장 **unsigned char**합니다.

### <a name="remarks"></a>설명

`m_chVal` 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 `m_chVal`, 먼저 값을 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 한 다음, DBVT_UCHAR로 `m_chVal` 에 액세스 하 고, 그렇지 않으면 유효한 값을 포함 `m_chVal` 신뢰할 수 없는 결과가 생성 됩니다.

##  <a name="m_dblval"></a>  CDBVariant::m_dblVal

형식의 값을 저장 **이중**합니다.

### <a name="remarks"></a>설명

`m_dblVal` 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 `m_dblVal`, 먼저 값을 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 한 다음, DBVT_DOUBLE로 `m_dblVal` 에 액세스 하 고, 그렇지 않으면 유효한 값을 포함 `m_dblVal` 신뢰할 수 없는 결과가 생성 됩니다.

##  <a name="m_dwtype"></a>  CDBVariant::m_dwType

이 데이터 멤버에 현재 저장 된 값에 대 한 데이터 형식이 포함 된 `CDBVariant` 개체의 공용 구조체 데이터 멤버입니다.

### <a name="remarks"></a>설명

이 공용 구조체에 액세스 하기 전에 값을 확인 해야 `m_dwType` 공용 구조체 데이터 멤버에 액세스를 확인 하기 위해. 다음 표에서 대 한 가능한 값 `m_dwType` 및 해당 공용 구조체 데이터 멤버입니다.

|m_dwType|공용 구조체 데이터 멤버|
|---------------|-----------------------|
|DBVT_NULL|없는 공용 구조체 멤버 액세스에 대 한 유효합니다.|
|DBVT_BOOL|[m_boolVal](#m_boolval)|
|DBVT_UCHAR|[m_chVal](#m_chval)|
|DBVT_SHORT|[m_iVal](#m_ival)|
|DBVT_LONG|[m_lVal](#m_lval)|
|DBVT_SINGLE|[m_fltVal](#m_fltval)|
|DBVT_DOUBLE|[m_dblVal](#m_dblval)|
|DBVT_DATE|[m_pdate](#m_pdate)|
|DBVT_STRING|[m_pstring](#m_pstring)|
|DBVT_BINARY|[m_pbinary](#m_pbinary)|
|DBVT_ASTRING|[m_pstringA](#m_pstringa)|
|DBVT_WSTRING|[m_pstringW](#m_pstringw)|

##  <a name="m_fltval"></a>  CDBVariant::m_fltVal

형식의 값을 저장 **float**합니다.

### <a name="remarks"></a>설명

`m_fltVal` 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 `m_fltVal`, 먼저 값을 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 한 다음, DBVT_SINGLE로 `m_fltVal` 에 액세스 하 고, 그렇지 않으면 유효한 값을 포함 `m_fltVal` 신뢰할 수 없는 결과가 생성 됩니다.

##  <a name="m_ival"></a>  CDBVariant::m_iVal

형식의 값을 저장 **짧은**합니다.

### <a name="remarks"></a>설명

`m_iVal` 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 `m_iVal`, 먼저 값을 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 한 다음, DBVT_SHORT로 `m_iVal` 에 액세스 하 고, 그렇지 않으면 유효한 값을 포함 `m_iVal` 신뢰할 수 없는 결과가 생성 됩니다.

##  <a name="m_lval"></a>  CDBVariant::m_lVal

형식의 값을 저장 **긴**합니다.

### <a name="remarks"></a>설명

`m_lVal` 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 `m_lVal`, 먼저 값을 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 한 다음, DBVT_LONG로 `m_lVal` 에 액세스 하 고, 그렇지 않으면 유효한 값을 포함 `m_lVal` 신뢰할 수 없는 결과가 생성 됩니다.

##  <a name="m_pbinary"></a>  CDBVariant::m_pbinary

형식의 개체에 대 한 포인터를 저장 [CLongBinary](../../mfc/reference/clongbinary-class.md)합니다.

### <a name="remarks"></a>설명

`m_pbinary` 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 `m_pbinary`, 먼저 값을 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 하는 경우 `m_dwType` 다음 DBVT_BINARY로 `m_pbinary` 대 한 유효한 포인터를 포함에 액세스 하 고, 그렇지 않으면 `m_pbinary` 신뢰할 수 없는 결과가 생성 됩니다.

##  <a name="m_pdate"></a>  CDBVariant::m_pdate

TIMESTAMP_STRUCT 형식의 개체에 대 한 포인터를 저장합니다.

### <a name="remarks"></a>설명

`m_pdate` 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 `m_pdate`, 먼저 값을 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 하는 경우 `m_dwType` 다음 DBVT_DATE로 `m_pdate` 대 한 유효한 포인터를 포함에 액세스 하 고, 그렇지 않으면 `m_pdate` 신뢰할 수 없는 결과가 생성 됩니다.

TIMESTAMP_STRUCT 데이터 형식에 대 한 자세한 내용은 항목을 참조 하세요. [C 데이터 형식](/sql/odbc/reference/appendixes/c-data-types) 의 부록 D에는 *ODBC 프로그래머 참조* Windows sdk에서입니다.

##  <a name="m_pstring"></a>  CDBVariant::m_pstring

형식의 개체에 대 한 포인터를 저장 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.

### <a name="remarks"></a>설명

`m_pstring` 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 `m_pstring`, 먼저 값을 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 하는 경우 `m_dwType` 다음 DBVT_STRING로 `m_pstring` 대 한 유효한 포인터를 포함에 액세스 하 고, 그렇지 않으면 `m_pstring` 신뢰할 수 없는 결과가 생성 됩니다.

##  <a name="m_pstringa"></a>  CDBVariant::m_pstringA

ASCII에 대 한 포인터를 저장 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.

### <a name="remarks"></a>설명

`m_pstringA` 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 `m_pstringA`, 먼저 값을 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 하는 경우 `m_dwType` 다음 DBVT_ASTRING로 `m_pstringA` 대 한 유효한 포인터를 포함에 액세스 하 고, 그렇지 않으면 `m_pstringA` 신뢰할 수 없는 결과가 생성 됩니다.

##  <a name="m_pstringw"></a>  CDBVariant::m_pstringW

저장 된 차원에 대 한 포인터 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.

### <a name="remarks"></a>설명

`m_pstringW` 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 `m_pstringW`, 먼저 값을 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 하는 경우 `m_dwType` 다음 DBVT_WSTRING로 `m_pstringW` 대 한 유효한 포인터를 포함에 액세스 하 고, 그렇지 않으면 `m_pstringW` 신뢰할 수 없는 결과가 생성 됩니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)
