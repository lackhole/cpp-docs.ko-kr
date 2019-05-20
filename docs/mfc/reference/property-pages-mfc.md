---
title: 속성 페이지(MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- property page data transfer functions in MFC
- property pages [MFC], global MFC functions
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
ms.openlocfilehash: 1c4e6c585bf216518e46109e88a2388da03a0496
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611775"
---
# <a name="property-pages-mfc"></a>속성 페이지(MFC)

속성 페이지 보기 및 대화 상자 데이터 교환 (DDX)를 기반으로 데이터 매핑 메커니즘을 지원 하 여 편집에 대 한 사용자 지정 가능한, 그래픽 인터페이스에서 특정 OLE 컨트롤 속성의 현재 값을 표시 합니다.

이 데이터 매핑 메커니즘 OLE 컨트롤의 개별 속성에 속성 페이지 컨트롤을 매핑합니다. 컨트롤 속성의 값에는 상태 또는 속성 페이지 컨트롤의 내용을 반영합니다. 속성 페이지 컨트롤 및 속성 간의 매핑을 지정 하 여 **DDP_** 속성 페이지에서 함수 호출 `DoDataExchange` 멤버 함수입니다. 다음은 목록을 **DDP_** 컨트롤의 속성 페이지를 사용 하 여 입력 데이터를 교환 하는 함수:

### <a name="property-page-data-transfer"></a>속성 페이지 데이터 전송

|||
|-|-|
|[DDP_CBIndex](#ddp_cbindex)|컨트롤의 속성을 사용 하 여 콤보 상자에서 선택된 된 문자열의 인덱스를 연결합니다.|
|[DDP_CBString](#ddp_cbstring)|컨트롤의 속성을 사용 하 여 콤보 상자에서 선택한 문자열을 연결합니다. 선택된 된 문자열 속성의 값으로 동일한 문자로 시작할 수 있지만 완벽 하 게 일치 시킬 필요가 없습니다.|
|[DDP_CBStringExact](#ddp_cbstringexact)|컨트롤의 속성을 사용 하 여 콤보 상자에서 선택한 문자열을 연결합니다. 선택된 된 문자열 및 속성의 문자열 값을 정확 하 게 일치 해야 합니다.|
|[DDP_Check](#ddp_check)|컨트롤의 속성을 사용 하 여 컨트롤의 속성 페이지에서 확인란을 연결합니다.|
|[DDP_LBIndex](#ddp_lbindex)|컨트롤의 속성을 사용 하 여 목록 상자에서 선택된 된 문자열의 인덱스를 연결합니다.|
|[DDP_LBString](#ddp_lbstring)|컨트롤의 속성을 사용 하 여 목록 상자에서 선택한 문자열을 연결합니다. 선택한 문자열 속성의 값으로 동일한 문자로 시작할 수 있지만 완벽 하 게 일치 하지 않아도 됩니다.|
|[DDP_LBStringExact](#ddp_lbstringexact)|컨트롤의 속성을 사용 하 여 목록 상자에서 선택한 문자열을 연결합니다. 선택된 된 문자열 및 속성의 문자열 값을 정확 하 게 일치 해야 합니다.|
|[DDP_PostProcessing](#ddp_postprocessing)|컨트롤에서 속성 값의 전송을 완료 됩니다.|
|[DDP_Radio](#ddp_radio)|컨트롤의 속성을 사용 하 여 컨트롤의 속성 페이지에서 라디오 단추 그룹을 연결 합니다.|
|[DDP_Text](#ddp_text)|컨트롤의 속성을 사용 하 여 컨트롤의 속성 페이지에서 컨트롤을 연결합니다. 이 함수는 여러 가지 속성을 같은 처리 **이중**를 **짧은**, BSTR, 및 **긴**합니다.|

에 대 한 자세한 내용은 합니다 `DoDataExchange` 함수 및 속성 페이지, 문서를 참조 [ActiveX 컨트롤: 속성 페이지](../../mfc/mfc-activex-controls-property-pages.md)합니다.

다음은 만들고 OLE 컨트롤에 대 한 속성 페이지를 관리 하는 데 사용 되는 매크로 목록입니다.

### <a name="property-pages"></a>속성 페이지

|||
|-|-|
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|속성 페이지 Id 목록을 시작합니다.|
|[END_PROPPAGEIDS](#end_proppageids)|속성 페이지 Id 목록을 종료합니다.|
|[PROPPAGEID](#proppageid)|컨트롤 클래스의 속성 페이지를 선언합니다.|

##  <a name="ddp_cbindex"></a>  DDP_CBIndex

속성 페이지의 `DoDataExchange` 함수에서 이 함수를 호출하여 정수 속성의 값을 속성 페이지의 콤보 상자에 있는 현재 선택 항목의 인덱스와 동기화합니다.

```
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,
    int id,
    int& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*ID*<br/>
콤보의 리소스 ID로 지정 된 컨트롤 속성과 연결 된 컨트롤 상자 *pszPropName*합니다.

*member*<br/>
지정 된 속성 페이지 컨트롤과 연결 된 멤버 변수 *id* 속성과 지정 된 *pszPropName*합니다.

*pszPropName*<br/>
지정 된 콤보 상자 컨트롤과 교환할 컨트롤 속성의 속성 이름 *id*합니다.

### <a name="remarks"></a>설명

이 함수는 해당 `DDX_CBIndex` 함수 호출 전에 호출되어야 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="ddp_cbstring"></a>  DDP_CBString

속성 페이지에서이 함수를 호출 `DoDataExchange` 속성 페이지의 콤보 상자에서 현재 선택 영역을 사용 하 여 문자열 속성의 값을 동기화 하는 함수입니다.

```
void AFXAPI DDP_CBString(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*ID*<br/>
콤보의 리소스 ID로 지정 된 컨트롤 속성과 연결 된 컨트롤 상자 *pszPropName*합니다.

*member*<br/>
지정 된 속성 페이지 컨트롤과 연결 된 멤버 변수 *id* 속성과 지정 된 *pszPropName*합니다.

*pszPropName*<br/>
지정 된 콤보 상자의 문자열을 사용 하 여 교환할 컨트롤 속성의 속성 이름 *id*합니다.

### <a name="remarks"></a>설명

이 함수는 해당 `DDX_CBString` 함수 호출 전에 호출되어야 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="ddp_cbstringexact"></a>  DDP_CBStringExact

속성 페이지에서이 함수를 호출 `DoDataExchange` 속성 페이지의 콤보 상자에서 현재 선택 영역을 정확 하 게 일치 하는 문자열 속성의 값을 동기화 하는 함수입니다.

```
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*ID*<br/>
콤보의 리소스 ID로 지정 된 컨트롤 속성과 연결 된 컨트롤 상자 *pszPropName*합니다.

*member*<br/>
지정 된 속성 페이지 컨트롤과 연결 된 멤버 변수 *id* 속성과 지정 된 *pszPropName*합니다.

*pszPropName*<br/>
지정 된 콤보 상자의 문자열을 사용 하 여 교환할 컨트롤 속성의 속성 이름 *id*합니다.

### <a name="remarks"></a>설명

이 함수는 해당 `DDX_CBStringExact` 함수 호출 전에 호출되어야 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="ddp_check"></a>  DDP_Check

속성 페이지에서이 함수를 호출 `DoDataExchange` 연결된 속성 페이지 확인란 컨트롤을 사용 하 여 속성의 값을 동기화 하는 함수입니다.

```
void AFXAPI DDP_Check(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCSTR pszPropName);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*ID*<br/>
지정 된 컨트롤 속성을 사용 하 여 연결 된 확인란 컨트롤의 리소스 ID *pszPropName*합니다.

*member*<br/>
지정 된 속성 페이지 컨트롤과 연결 된 멤버 변수 *id* 속성과 지정 된 *pszPropName*합니다.

*pszPropName*<br/>
지정 된 확인란 컨트롤과 교환할 컨트롤 속성의 속성 이름 *id*합니다.

### <a name="remarks"></a>설명

이 함수는 해당 `DDX_Check` 함수 호출 전에 호출되어야 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="ddp_lbindex"></a>  DDP_LBIndex

속성 페이지에서이 함수를 호출 `DoDataExchange` 속성 페이지의 목록 상자에서 현재 선택 영역의 인덱스를 사용 하 여 정수 속성의 값을 동기화 하는 함수입니다.

```
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,
    int id,
    int& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*ID*<br/>
리소스 ID 목록의 box로 지정 된 컨트롤 속성과 연결 된 컨트롤 *pszPropName*합니다.

*member*<br/>
지정 된 속성 페이지 컨트롤과 연결 된 멤버 변수 *id* 속성과 지정 된 *pszPropName*합니다.

*pszPropName*<br/>
지정 된 목록 상자의 문자열을 사용 하 여 교환할 컨트롤 속성의 속성 이름 *id*합니다.

### <a name="remarks"></a>설명

이 함수는 해당 `DDX_LBIndex` 함수 호출 전에 호출되어야 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="ddp_lbstring"></a>  DDP_LBString

속성 페이지에서이 함수를 호출 `DoDataExchange` 속성 페이지의 목록 상자에서 현재 선택 영역을 사용 하 여 문자열 속성의 값을 동기화 하는 함수입니다.

```
void AFXAPI DDP_LBString(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*ID*<br/>
리소스 ID 목록의 box로 지정 된 컨트롤 속성과 연결 된 컨트롤 *pszPropName*합니다.

*member*<br/>
지정 된 속성 페이지 컨트롤과 연결 된 멤버 변수 *id* 속성과 지정 된 *pszPropName*합니다.

*pszPropName*<br/>
지정 된 목록 상자의 문자열을 사용 하 여 교환할 컨트롤 속성의 속성 이름 *id*합니다.

### <a name="remarks"></a>설명

이 함수는 해당 `DDX_LBString` 함수 호출 전에 호출되어야 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="ddp_lbstringexact"></a>  DDP_LBStringExact

속성 페이지에서이 함수를 호출 `DoDataExchange` 정확히 속성 페이지의 목록 상자에서 현재 선택한 일치 하는 문자열 속성의 값을 동기화 하는 함수입니다.

```
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,
    int id,
    CString& member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*ID*<br/>
리소스 ID 목록의 box로 지정 된 컨트롤 속성과 연결 된 컨트롤 *pszPropName*합니다.

*member*<br/>
지정 된 속성 페이지 컨트롤과 연결 된 멤버 변수 *id* 속성과 지정 된 *pszPropName*합니다.

*pszPropName*<br/>
지정 된 목록 상자의 문자열을 사용 하 여 교환할 컨트롤 속성의 속성 이름 *id*합니다.

### <a name="remarks"></a>설명

이 함수는 해당 `DDX_LBStringExact` 함수 호출 전에 호출되어야 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="ddp_postprocessing"></a>  DDP_PostProcessing

속성 페이지에서이 함수를 호출 `DoDataExchange` 함수, 속성 값을 저장 하는 경우 컨트롤 속성 페이지에서 속성 값의 전송이 완료 합니다.

```
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

### <a name="remarks"></a>설명

모든 데이터 교환 함수 완료 된 후이 함수를 호출 해야 합니다. 예를 들어:

[!code-cpp[NVC_MFCAxCtl#15](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="ddp_radio"></a>  DDP_Radio

컨트롤에서이 함수를 호출 `DoPropExchange` 연결된 속성 페이지 라디오 단추 컨트롤을 사용 하 여 속성의 값을 동기화 하는 함수입니다.

```
void AFXAPI DDP_Radio(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*ID*<br/>
라디오의 리소스 ID로 지정 된 컨트롤 속성과 연결 된 컨트롤 단추 *pszPropName*합니다.

*member*<br/>
지정 된 속성 페이지 컨트롤과 연결 된 멤버 변수 *id* 속성과 지정 된 *pszPropName*합니다.

*pszPropName*<br/>
지정 된 라디오 단추 컨트롤과 교환할 컨트롤 속성의 속성 이름 *id*합니다.

### <a name="remarks"></a>설명

이 함수는 해당 `DDX_Radio` 함수 호출 전에 호출되어야 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="ddp_text"></a>  DDP_Text

컨트롤에서이 함수를 호출 `DoDataExchange` 연결된 속성 페이지 컨트롤을 사용 하 여 속성의 값을 동기화 하는 함수입니다.

```
void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    BYTE & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    int & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    UINT & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    long & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    DWORD & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    float & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    double & member,
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,
    int id,
    CString & member,
    LPCTSTR pszPropName);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*ID*<br/>
지정 된 컨트롤 속성과 연결 된 컨트롤의 리소스 ID *pszPropName*합니다.

*member*<br/>
지정 된 속성 페이지 컨트롤과 연결 된 멤버 변수 *id* 속성과 지정 된 *pszPropName*합니다.

*pszPropName*<br/>
지정 된 컨트롤과 교환할 컨트롤 속성의 속성 이름 *id*합니다.

### <a name="remarks"></a>설명

이 함수는 해당 `DDX_Text` 함수 호출 전에 호출되어야 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="begin_proppageids"></a>  BEGIN_PROPPAGEIDS

컨트롤의 속성 페이지 Id 목록 정의 시작 합니다.

```
BEGIN_PROPPAGEIDS(class_name,  count)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
속성에 대 한 페이지 지정 된 컨트롤 클래스의 이름입니다.

*count*<br/>
컨트롤 클래스에 의해 사용 되는 속성 페이지의 수입니다.

### <a name="remarks"></a>설명

클래스의 멤버 함수를 정의 하는 구현 (.cpp) 파일에서 시작 속성 페이지 목록 BEGIN_PROPPAGEIDS 매크로 사용 하 여 다음 속성 페이지에서 각각에 대해 매크로 항목을 추가 및 완료를 END_PROPPAGEIDS 사용 하 여 속성 페이지 목록 매크로입니다.

속성 페이지에 대 한 자세한 내용은 문서를 참조 하세요. [ActiveX 컨트롤: 속성 페이지](../../mfc/mfc-activex-controls-property-pages.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="end_proppageids"></a>  END_PROPPAGEIDS

속성 페이지 ID 목록 정의 종료합니다.

```
END_PROPPAGEIDS(class_name)
```

### <a name="parameters"></a>매개 변수

*class_name*<br/>
속성 페이지를 소유 하는 컨트롤 클래스의 이름입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

##  <a name="proppageid"></a>  PROPPAGEID

OLE 컨트롤에서 사용 하 여에 대 한 속성 페이지를 추가합니다.

```
PROPPAGEID(clsid)
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
속성 페이지의 고유 클래스 ID입니다.

### <a name="remarks"></a>설명

컨트롤의 구현 파일에서 BEGIN_PROPPAGEIDS 및 END_PROPPAGEIDS 매크로 간의 모든 PROPPAGEID 매크로 배치 되어야 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxctl.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
