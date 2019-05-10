---
title: CRecordView 및 CDaoRecordView에 대한 대화 상자 데이터 교환 함수
ms.date: 11/04/2016
f1_keywords:
- AFXDAO/DDX_FieldCBIndex
- AFXDAO/DDX_FieldCBString
- AFXDAO/DDX_FieldCBStringExact
- AFXDAO/DDX_FieldCheck
- AFXDAO/DDX_FieldLBIndex
- AFXDAO/DDX_FieldLBString
- AFXDAO/DDX_FieldLBStringExact
- AFXDAO/DDX_FieldRadio
- AFXDAO/DDX_FieldScroll
- AFXDAO/DDX_FieldText
helpviewer_keywords:
- DDX_Field functions [MFC]
- ODBC [MFC], dialog data exchange (DDX) support
- DDX (dialog data exchange) [MFC], database support
- DDX (dialog data exchange) [MFC], functions
- databases [MFC], dialog data exchange (DDX) support
- DAO [MFC], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
ms.openlocfilehash: 2a794d16b2f94bf8ba66b6c0398dec262d8829e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322555"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>CRecordView 및 CDaoRecordView에 대한 대화 상자 데이터 교환 함수

이 항목에서는 간에 데이터를 교환 하는 데 DDX_Field 함수는 [CRecordset](../../mfc/reference/crecordset-class.md) 및 [CRecordView](../../mfc/reference/crecordview-class.md) 폼 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 및 [ CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 폼입니다.

> [!NOTE]
>  DDX_Field 함수는 폼의 컨트롤을 사용 하 여 데이터를 교환에서 DDX 함수와 같습니다. 하지만 DDX를 달리 보기의 관련된 레코드 집합 개체의 필드를 사용 하 여 대신 레코드 뷰 자체의 필드를 사용 하 여 데이터를 교환 합니다. 자세한 내용은 클래스를 참조 하십시오 `CRecordView` 고 `CDaoRecordView`입니다.

### <a name="ddxfield-functions"></a>DDX_Field 함수

|||
|-|-|
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|레코드 집합 필드 데이터 멤버에 콤보 상자에서 현재 선택 영역의 인덱스 사이의 정수 데이터를 전송 된 [CRecordView](../../mfc/reference/crecordview-class.md) 하거나 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)합니다.|
|[DDX_FieldCBString](#ddx_fieldcbstring)|전송을 `CString` 레코드 집합 필드 데이터 멤버는 콤보 편집 컨트롤 사이 데이터 상자에 `CRecordView` 또는 `CDaoRecordView`합니다. 컨트롤에 레코드 집합에서 데이터를 이동 하는 경우이 함수는 지정된 된 문자열의 문자를 시작 하는 콤보 상자에서 항목을 선택 합니다.|
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|전송을 `CString` 레코드 집합 필드 데이터 멤버는 콤보 편집 컨트롤 사이 데이터 상자에 `CRecordView` 또는 `CDaoRecordView`합니다. 컨트롤에 레코드 집합에서 데이터를 이동 하는 경우이 함수는 지정 된 문자열과 정확히 일치 하는 콤보 상자에서 항목을 선택 합니다.|
|[DDX_FieldCheck](#ddx_fieldcheck)|레코드 집합 필드 데이터 멤버 사이 확인란을 부울 데이터를 전송 된 `CRecordView` 또는 `CDaoRecordView`합니다.|
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|레코드 집합 필드 데이터 멤버의 목록 상자에서 현재 선택 영역의 인덱스 사이의 정수 데이터를 전송 된 `CRecordView` 또는 `CDaoRecordView`합니다.|
|[DDX_FieldLBString](#ddx_fieldlbstring)|으로의 전송을 관리 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 목록 상자 컨트롤을 레코드 집합의 필드 데이터 멤버 사이 데이터입니다. 컨트롤에 레코드 집합에서 데이터를 이동 하는 경우이 함수는 지정된 된 문자열의 문자를 시작 하는 목록 상자에서 항목을 선택 합니다.|
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|으로의 전송을 관리 `CString` 목록 상자 컨트롤을 레코드 집합의 필드 데이터 멤버 사이 데이터입니다. 컨트롤에 레코드 집합에서 데이터를 이동 하는 경우이 함수는 지정 된 문자열과 정확히 일치 하는 첫 번째 항목을 선택 합니다.|
|[DDX_FieldRadio](#ddx_fieldradio)|레코드 집합 필드 데이터 멤버의 라디오 단추 그룹 사이의 정수 데이터를 전송 된 `CRecordView` 또는 `CDaoRecordView`합니다.|
|[DDX_FieldScroll](#ddx_fieldscroll)|Scroll bar 컨트롤의 스크롤 위치를 가져오거나 설정 합니다.는 `CRecordView` 또는 `CDaoRecordView`합니다. 호출 하면 [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) 함수입니다.|
|[DDX_FieldSlider](#ddx_fieldslider)|레코드 뷰에서의 슬라이더 컨트롤의 스크롤 상자 위치를 동기화 및 `int` 레코드 집합의 필드 데이터 멤버입니다. |
|[DDX_FieldText](#ddx_fieldtext)|전송할 수 있는 오버 로드 된 버전 `int`, **UINT**, **long**를 `DWORD`를 [CString](../../atl-mfc-shared/reference/cstringt-class.md)를 **float** 를 **이중**를 **짧은**를 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), 및 [COleCurrency](../../mfc/reference/colecurrency-class.md) 레코드 집합 필드 데이터 멤버와 편집 간 데이터 상자에 `CRecordView` 또는 `CDaoRecordView`합니다.|

##  <a name="ddx_fieldcbindex"></a>  DDX_FieldCBIndex

합니다 `DDX_FieldCBIndex` 레코드 뷰에서의 콤보 상자 컨트롤의 목록 상자 컨트롤에서 선택한 항목의 인덱스를 동기화 하는 함수 및 `int` 레코드 뷰와 연결 된 레코드 집합의 필드 데이터 멤버입니다.

```
void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
컨트롤의 ID를 [CRecordView](../../mfc/reference/crecordview-class.md) 하거나 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.

*index*<br/>
연결 된 필드 데이터 멤버에 대 한 참조가 `CRecordset` 또는 `CDaoRecordset` 개체입니다.

*pRecordset*<br/>
에 대 한 포인터를 [CRecordset](../../mfc/reference/crecordset-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 데이터가 교환 되는 개체입니다.

### <a name="remarks"></a>설명

컨트롤에 레코드 집합에서 데이터를 이동 하는 경우이 함수에 지정 된 값을 기준으로 컨트롤의 선택 항목을 설정 *인덱스*합니다. 컨트롤에는 레코드 집합에서 전송, 레코드 집합 필드에 Null 인 경우 MFC 설정 된 인덱스의 값을 0으로. 컨트롤에서 레코드 집합에 전송, 컨트롤 비어 있거나 없는 항목을 선택 하면 레코드 집합 필드를 0으로 설정 됩니다.

ODBC 기반 클래스를 사용 하 여 작업 하는 경우 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 하 고 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 문서를 참조 하세요. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.

### <a name="example"></a>예제

참조 [DDX_FieldText](#ddx_fieldtext) 일반 DDX_Field 예제입니다. 이 예제에서는 비슷한 `DDX_FieldCBIndex`합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

##  <a name="ddx_fieldcbstring"></a>  DDX_FieldCBString

합니다 `DDX_FieldCBString` 함수도의 전송을 관리 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 레코드 뷰에서의 콤보 상자 컨트롤의 편집 컨트롤 간에 데이터 및 `CString` 레코드 뷰와 연결 된 레코드 집합의 필드 데이터 멤버입니다.

```
void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
컨트롤의 ID를 [CRecordView](../../mfc/reference/crecordview-class.md) 하거나 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.

*값*<br/>
연결 된 필드 데이터 멤버에 대 한 참조가 `CRecordset` 또는 `CDaoRecordset` 개체입니다.

*pRecordset*<br/>
에 대 한 포인터를 [CRecordset](../../mfc/reference/crecordset-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 데이터가 교환 되는 개체입니다.

### <a name="remarks"></a>설명

이 함수는 첫 번째 행에서 지정 된 문자열의 문자를 시작 하는 콤보 상자에서 현재 선택 영역 설정 컨트롤에 레코드 집합에서 데이터를 이동 하는 경우 *값*합니다. 컨트롤에 레코드 집합에서 전송에서 레코드 집합 필드에 Null 인 경우 모든 선택 콤보 상자에서 제거 되 고 콤보 상자의 편집 컨트롤이 설정 된 비어 있는 것으로 합니다. 컨트롤에서 레코드 집합에 전송에서 컨트롤이 비어 있으면 레코드 집합 필드 Null로 설정 됩니다 필드에서 허용 하는 경우.

ODBC 기반 클래스를 사용 하 여 작업 하는 경우 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 하 고 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 문서를 참조 하세요. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.

### <a name="example"></a>예제

참조 [DDX_FieldText](#ddx_fieldtext) 일반 DDX_Field 예제입니다. 예제에 대 한 호출에 포함 되어 `DDX_FieldCBString`입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="ddx_fieldcbstringexact"></a>  DDX_FieldCBStringExact

합니다 `DDX_FieldCBStringExact` 함수도의 전송을 관리 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 레코드 뷰에서의 콤보 상자 컨트롤의 편집 컨트롤 간에 데이터 및 `CString` 레코드 뷰와 연결 된 레코드 집합의 필드 데이터 멤버입니다.

```
void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
컨트롤의 ID를 [CRecordView](../../mfc/reference/crecordview-class.md) 하거나 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.

*값*<br/>
연결 된 필드 데이터 멤버에 대 한 참조가 `CRecordset` 또는 `CDaoRecordset` 개체입니다.

*pRecordset*<br/>
에 대 한 포인터를 [CRecordset](../../mfc/reference/crecordset-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 데이터가 교환 되는 개체입니다.

### <a name="remarks"></a>설명

이 함수에 지정 된 문자열과 정확히 일치 하는 첫 번째 행에 콤보 상자에서 현재 선택 영역 설정 컨트롤에 레코드 집합에서 데이터를 이동 하는 경우 *값*합니다. 컨트롤에 레코드 집합에서 전송에서 레코드 집합 필드에 NULL 인 경우 모든 선택 콤보 상자에서 제거 되 고 콤보 상자의 편집 상자 설정 되어 비어 있도록 합니다. 컨트롤에서 레코드 집합에 전송, 컨트롤이 비어 있으면 레코드 집합 필드를 NULL로 설정 됩니다.

ODBC 기반 클래스를 사용 하 여 작업 하는 경우 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 하 고 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 문서를 참조 하세요. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.

### <a name="example"></a>예제

참조 [DDX_FieldText](#ddx_fieldtext) 일반 DDX_Field 예제입니다. 에 대 한 호출 `DDX_FieldCBStringExact` 와 유사 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

##  <a name="ddx_fieldcheck"></a>  DDX_FieldCheck

합니다 `DDX_FieldCheck` 함수도의 전송을 관리 **int** 대화 상자에 확인란 컨트롤 간에 데이터 폼 뷰 또는 컨트롤 뷰 개체와 **int** 대화 상자, 폼 뷰 또는 컨트롤의 데이터 멤버 뷰 개체입니다.

```
void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
컨트롤 속성과 연결 된 확인란 컨트롤의 리소스 ID입니다.

*값*<br/>
대화 상자, 폼 뷰 또는 데이터를 교환할 컨트롤 뷰 개체의 멤버 변수 참조입니다.

*pRecordset*<br/>
에 대 한 포인터를 [CRecordset](../../mfc/reference/crecordset-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 데이터가 교환 되는 개체입니다.

### <a name="remarks"></a>설명

때 `DDX_FieldCheck` 가 호출 *값* check box 컨트롤의 현재 상태로 설정 됩니다 컨트롤의 상태 설정할지 *값*전송의 방향에 따라 합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

##  <a name="ddx_fieldlbindex"></a>  DDX_FieldLBIndex

합니다 `DDX_FieldLBIndex` 레코드 뷰에서의 목록 상자 컨트롤에서 선택한 항목의 인덱스를 동기화 하는 함수 및 **int** 레코드 뷰와 연결 된 레코드 집합의 필드 데이터 멤버입니다.

```
void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,
    int nIDC,
    int& index,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
컨트롤의 ID를 [CRecordView](../../mfc/reference/crecordview-class.md) 하거나 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.

*index*<br/>
연결 된 필드 데이터 멤버에 대 한 참조가 `CRecordset` 또는 `CDaoRecordset` 개체입니다.

*pRecordset*<br/>
에 대 한 포인터를 [CRecordset](../../mfc/reference/crecordset-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 데이터가 교환 되는 개체입니다.

### <a name="remarks"></a>설명

컨트롤에 레코드 집합에서 데이터를 이동 하는 경우이 함수에 지정 된 값을 기준으로 컨트롤의 선택 항목을 설정 *인덱스*합니다. 컨트롤에는 레코드 집합에서 전송, 레코드 집합 필드에 Null 인 경우 MFC 설정 된 인덱스의 값을 0으로. 컨트롤에서 레코드 집합에 전송, 컨트롤이 비어 있으면 레코드 집합 필드를 0으로 설정 됩니다.

ODBC 기반 클래스를 사용 하 여 작업 하는 경우 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 하 고 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 문서를 참조 하세요. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.

### <a name="example"></a>예제

참조 [DDX_FieldText](#ddx_fieldtext) 일반 DDX_Field 예제입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

##  <a name="ddx_fieldlbstring"></a>  DDX_FieldLBString

합니다 `DDX_FieldLBString` 레코드 뷰를 목록 상자 컨트롤의 현재 선택 영역 복사를 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 레코드 뷰와 연결 된 레코드 집합의 필드 데이터 멤버입니다.

```
void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
컨트롤의 ID를 [CRecordView](../../mfc/reference/crecordview-class.md) 하거나 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.

*값*<br/>
연결 된 필드 데이터 멤버에 대 한 참조가 `CRecordset` 또는 `CDaoRecordset` 개체입니다.

*pRecordset*<br/>
에 대 한 포인터를 [CRecordset](../../mfc/reference/crecordset-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 데이터가 교환 되는 개체입니다.

### <a name="remarks"></a>설명

현재 선택 영역에서 지정 된 문자열의 문자를 시작 하는 첫 번째 행에 있는 목록 상자에서이 함수는 반대 방향으로 설정 *값*합니다. 컨트롤에는 레코드 집합에서 전송에서 레코드 집합 필드는 Null을 모든 선택 목록 상자에서 제거 됩니다. 컨트롤에서 레코드 집합에 전송, 컨트롤이 비어 있으면 레코드 집합 필드를 Null로 설정 됩니다.

ODBC 기반 클래스를 사용 하 여 작업 하는 경우 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 하 고 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 문서를 참조 하세요. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.

### <a name="example"></a>예제

참조 [DDX_FieldText](#ddx_fieldtext) 일반 DDX_Field 예제입니다. 에 대 한 호출 `DDX_FieldLBString` 와 유사 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

##  <a name="ddx_fieldlbstringexact"></a>  DDX_FieldLBStringExact

합니다 `DDX_FieldLBStringExact` 함수를 레코드 뷰에 목록 상자 컨트롤의 현재 선택 영역 복사를 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 레코드 뷰와 연결 된 레코드 집합의 필드 데이터 멤버입니다.

```
void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
컨트롤의 ID를 [CRecordView](../../mfc/reference/crecordview-class.md) 하거나 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.

*값*<br/>
연결 된 필드 데이터 멤버에 대 한 참조가 `CRecordset` 또는 `CDaoRecordset` 개체입니다.

*pRecordset*<br/>
에 대 한 포인터를 [CRecordset](../../mfc/reference/crecordset-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 데이터가 교환 되는 개체입니다.

### <a name="remarks"></a>설명

현재 선택 영역에 지정 된 문자열과 정확히 일치 하는 첫 번째 행에 목록 상자에서이 함수는 반대 방향으로 설정 *값*합니다. 컨트롤에는 레코드 집합에서 전송에서 레코드 집합 필드는 Null을 모든 선택 목록 상자에서 제거 됩니다. 컨트롤에서 레코드 집합에 전송, 컨트롤이 비어 있으면 레코드 집합 필드를 Null로 설정 됩니다.

ODBC 기반 클래스를 사용 하 여 작업 하는 경우 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 하 고 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 문서를 참조 하세요. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.

### <a name="example"></a>예제

참조 [DDX_FieldText](#ddx_fieldtext) 일반 DDX_Field 예제입니다. 에 대 한 호출 `DDX_FieldLBStringExact` 와 유사 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

##  <a name="ddx_fieldradio"></a>  DDX_FieldRadio

합니다 `DDX_FieldRadio` 함수는 0부터 시작 연결 **int** 레코드 뷰에 라디오 단추 그룹에서 현재 선택 된 라디오 단추를 사용 하 여 레코드 뷰의 레코드 집합의 멤버 변수입니다.

```
void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
첫 번째 ID 옆에 있는 라디오 단추 컨트롤 (스타일 WS_GROUP) 설정 된 그룹에는 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.

*값*<br/>
연결 된 필드 데이터 멤버에 대 한 참조가 `CRecordset` 또는 `CDaoRecordset` 개체입니다.

*pRecordset*<br/>
에 대 한 포인터를 [CRecordset](../../mfc/reference/crecordset-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 데이터가 교환 되는 개체입니다.

### <a name="remarks"></a>설명

레코드 집합 필드에서 보기를 전송이 함수를 설정 합니다 *n 번째* (0부터 시작) 라디오 단추 및 다른 단추를 해제 합니다. 반대 방향으로이 함수는 현재 (선택 됨)에 있는 라디오 단추에 대해 서 수를 레코드 집합 필드를 설정 합니다. 컨트롤에는 레코드 집합에서 전송, 레코드 집합 필드에 Null 인 경우 단추가 제공 되지 않음 선택 되어 있습니다. 전송 컨트롤에서 레코드 집합에 없는 컨트롤을 선택 하면 레코드 집합 필드 설정 됩니다 Null로 필드를 허용 하는 경우.

ODBC 기반 클래스를 사용 하 여 작업 하는 경우 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 하 고 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 문서를 참조 하세요. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.

### <a name="example"></a>예제

참조 [DDX_FieldText](#ddx_fieldtext) 일반 DDX_Field 예제입니다. 에 대 한 호출 `DDX_FieldRadio` 와 유사 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

##  <a name="ddx_fieldscroll"></a>  DDX_FieldScroll

합니다 `DDX_FieldScroll` 레코드 뷰에서의 scroll bar 컨트롤의 스크롤 위치를 동기화 하는 함수 및 **int** 레코드 뷰를 사용 하 여 (또는 매핑할 하려는 모든 정수 변수를 사용 하 여) 연결 된 레코드 집합의 필드 데이터 멤버 .

```
void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
첫 번째 ID 옆에 있는 라디오 단추 컨트롤 (스타일 WS_GROUP) 설정 된 그룹에는 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.

*값*<br/>
연결 된 필드 데이터 멤버에 대 한 참조가 `CRecordset` 또는 `CDaoRecordset` 개체입니다.

*pRecordset*<br/>
에 대 한 포인터를 [CRecordset](../../mfc/reference/crecordset-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 데이터가 교환 되는 개체입니다.

### <a name="remarks"></a>설명

컨트롤에 레코드 집합에서 데이터를 이동 하는 경우이 함수에 지정 된 값 scroll bar 컨트롤의 스크롤 위치를 설정 *값*합니다. 컨트롤에는 레코드 집합에서 전송, 레코드 집합 필드에 Null 인 경우 스크롤 막대 컨트롤을 0으로 설정 됩니다. 컨트롤에서 레코드 집합에 전송에서 컨트롤이 비어 있으면 레코드 집합 필드의 값은 0입니다.

ODBC 기반 클래스를 사용 하 여 작업 하는 경우 첫 번째 버전을 사용 합니다. DAO 기반 클래스를 사용 하는 경우에 두 번째 버전을 사용 합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 하 고 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 문서를 참조 하세요. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.

### <a name="example"></a>예제

참조 [DDX_FieldText](#ddx_fieldtext) 일반 DDX_Field 예제입니다. 에 대 한 호출 `DDX_FieldScroll` 와 유사 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

  ## <a name="ddx_fieldslider"></a>  DDX_FieldSlider
합니다 `DDX_FieldSlider` 레코드 뷰에서의 슬라이더 컨트롤의 스크롤 상자 위치를 동기화 하는 함수 및 **int** 레코드 뷰를 사용 하 여 (또는 매핑할 하려는 모든 정수 변수를 사용 하 여) 연결 된 레코드 집합의 필드 데이터 멤버입니다.

### <a name="syntax"></a>구문

  ```
   void AFXAPI DDX_FieldSlider(
       CDataExchange* pDX,
       int nIDC,
       int& value,
       CRecordset* pRecordset );

void AFXAPI DDX_FieldSlider(
   CDataExchange* pDX,
   int nIDC,
   int& value,
   CDaoRecordset* pRecordset );
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
슬라이더 컨트롤의 리소스 ID입니다.

*값*<br/>
교환할 값에 대 한 참조입니다. 이 매개 변수를 보유 슬라이더 컨트롤의 현재 위치를 설정 하려면이 사용 됩니다.

*pRecordset*<br/>
연결에 대 한 포인터 `CRecordset` 또는 `CDaoRecordset` 데이터가 교환 되는 개체입니다.

### <a name="remarks"></a>설명

이 함수에 지정 된 값을 슬라이더의 위치를 설정 데이터를 레코드 집합에서 슬라이더를 이동할 때 *값*합니다. 컨트롤에는 레코드 집합에서 전송, 레코드 집합 필드에 Null 인 경우 슬라이더 컨트롤의 위치를 0으로 설정 됩니다. 컨트롤에서 레코드 집합에 전송에서 컨트롤이 비어 있으면 레코드 집합 필드의 값은 0입니다.

`DDX_FieldSlider` 단순히 위치 대신 범위를 설정할 수 있는 슬라이더 컨트롤을 사용 하 여 범위 정보를 교환 하지 않습니다.

ODBC 기반 클래스를 사용 하는 경우에 함수의 첫 번째 재정의 사용 합니다. DAO 기반 클래스를 사용 하 여 두 번째 재정의 사용 합니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../dialog-data-exchange-and-validation.md)를 참조하세요. 예제 및에 대 한 DDX에 대 한 자세한 내용은 `CRecordView` 하 고 `CDaoRecordView` 필드를 참조 하십시오 [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다. 슬라이더 컨트롤에 대 한 자세한 내용은 [CSliderCtrl 사용 하 여](../using-csliderctrl.md)입니다.

### <a name="example"></a>예제

참조 [DDX_FieldText](#ddx_fieldtext) 일반 DDX_Field 예제입니다. 에 대 한 호출 `DDX_FieldSlider` 와 유사 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

##  <a name="ddx_fieldtext"></a>  DDX_FieldText

`DDX_FieldText` 함수도의 전송을 관리 **int**, **짧은**를 **긴**, DWORD [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **double**합니다 **BOOL**, 또는 **바이트** 레코드 집합의 필드 데이터 멤버는 편집 상자 컨트롤 사이 데이터입니다.

```
void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    int& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    UINT& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    long& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    float& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    double& value,
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    short& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BOOL& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    BYTE& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    long& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    DWORD& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    CString& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    float& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    double& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    COleDateTime& value,
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,
    int nIDC,
    COleCurrency& value,
    CDaoRecordset* pRecordset);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
컨트롤의 ID를 [CRecordView](../../mfc/reference/crecordview-class.md) 하거나 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 개체입니다.

*값*<br/>
연결 된 필드 데이터 멤버에 대 한 참조가 `CRecordset` 또는 `CDaoRecordset` 개체입니다. 오버 로드 된 버전의 기반이 값의 데이터 형식에 따라 달라 집니다 `DDX_FieldText` 사용 합니다.

*pRecordset*<br/>
에 대 한 포인터를 [CRecordset](../../mfc/reference/crecordset-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 데이터가 교환 되는 개체입니다. 이 포인터를 사용 하 `DDX_FieldText` 를 감지 하 여 Null 값을 설정 합니다.

### <a name="remarks"></a>설명

에 대 한 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체를 `DDX_FieldText` 전송도 관리 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), 및 [COleCurrency](../../mfc/reference/colecurrency-class.md) 값입니다. 빈 입력란 컨트롤에는 Null 값을 나타냅니다. 컨트롤에는 레코드 집합에서 전송, 레코드 집합 필드에 Null 인 경우 입력란은 설정 비어 있도록 합니다. 컨트롤에서 레코드 집합에 전송, 컨트롤이 비어 있으면 레코드 집합 필드를 Null로 설정 됩니다.

사용 하 여 버전을 사용 하 여 [CRecordset](../../mfc/reference/crecordset-class.md) ODBC 기반 클래스를 사용 하 여 작업 하는 경우 매개 변수입니다. 사용 하 여 버전을 사용 하 여 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) DAO 기반 클래스를 사용 하 여 작업 하는 경우 매개 변수입니다.

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요. 예제 및에 대 한 DDX에 대 한 자세한 내용은 [CRecordView](../../mfc/reference/crecordview-class.md) 하 고 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 문서를 참조 하세요. [레코드 뷰](../../data/record-views-mfc-data-access.md)합니다.

### <a name="example"></a>예제

다음 `DoDataExchange` 함수를 [CRecordView](../../mfc/reference/crecordview-class.md) 포함 `DDX_FieldText` 세 개의 데이터 형식에 대 한 함수 호출: `IDC_COURSELIST` 은 콤보 상자;는 다른 두 컨트롤은 편집 상자입니다. DAO 프로그래밍에 대 한 합니다 *하기 위해* 매개 변수는에 대 한 포인터는 [CRecordset](../../mfc/reference/crecordset-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다.

[!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](mfc-macros-and-globals.md)
