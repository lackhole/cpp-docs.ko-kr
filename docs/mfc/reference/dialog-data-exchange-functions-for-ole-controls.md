---
title: OLE 컨트롤에 대한 대화 상자 데이터 교환 함수
ms.date: 11/04/2016
f1_keywords:
- AFXDISP/DDX_OCBool
- AFXDISP/DDX_OCBoolRO
- AFXDISP/DDX_OCColor
- AFXDISP/DDX_OCColorRO
- AFXDISP/DDX_OCFloat
- AFXDISP/DDX_OCFloatRO
- AFXDISP/DDX_OCInt
- AFXDISP/DDX_OCIntRO
- AFXDISP/DDX_OCShort
- AFXDISP/DDX_OCShortRO
- AFXDISP/DDX_OCText
- AFXDISP/DDX_OCTextRO
helpviewer_keywords:
- OLE controls [MFC], DDX functions
- DDX (dialog data exchange), OLE support
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
ms.openlocfilehash: df96d44cefeb15d89653538c3006d109a97a21a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322568"
---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>OLE 컨트롤에 대한 대화 상자 데이터 교환 함수

이 항목에서는 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 내 OLE 컨트롤의 속성 및 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버 간에 데이터를 교환 하는 데 사용 하 여 DDX_OC 함수를 나열 합니다.

### <a name="ddxoc-functions"></a>DDX_OC 함수

|||
|-|-|
|[DDX_OCBool](#ddx_ocbool)|으로의 전송을 관리 **BOOL** OLE 컨트롤의 속성 간에 데이터와 **BOOL** 데이터 멤버입니다.|
|[DDX_OCBoolRO](#ddx_ocboolro)|으로의 전송을 관리 **BOOL** OLE 컨트롤의 읽기 전용 속성 간에 데이터와 **BOOL** 데이터 멤버입니다.|
|[DDX_OCColor](#ddx_occolor)|으로의 전송을 관리 **OLE_COLOR** OLE 컨트롤의 속성 간에 데이터와 **OLE_COLOR** 데이터 멤버입니다.|
|[DDX_OCColorRO](#ddx_occolorro)|으로의 전송을 관리 **OLE_COLOR** OLE 컨트롤의 읽기 전용 속성 간에 데이터와 **OLE_COLOR** 데이터 멤버입니다.|
|[DDX_OCFloat](#ddx_ocfloat)|으로의 전송을 관리 **부동 소수점** (또는 **double**) OLE 컨트롤의 속성 간에 데이터와 **float** (또는 **double**) 데이터 멤버입니다.|
|[DDX_OCFloatRO](#ddx_ocfloatro)|으로의 전송을 관리 **부동 소수점** (또는 **double**) OLE 컨트롤의 읽기 전용 속성 간에 데이터와 **float** (또는 **double**) 데이터 멤버입니다.|
|[DDX_OCInt](#ddx_ocint)|으로의 전송을 관리 **int** (또는 **긴**) OLE 컨트롤의 속성 간에 데이터와 **int** (또는 **긴**) 데이터 멤버입니다.|
|[DDX_OCIntRO](#ddx_ocintro)|으로의 전송을 관리 **int** (또는 **긴**) OLE 컨트롤의 읽기 전용 속성 간에 데이터와 **int** (또는 **긴**) 데이터 멤버입니다.|
|[DDX_OCShort](#ddx_ocshort)|으로의 전송을 관리 **짧은** OLE 컨트롤의 속성 간에 데이터와 **짧은** 데이터 멤버입니다.|
|[DDX_OCShortRO](#ddx_ocshortro)|으로의 전송을 관리 **짧은** OLE 컨트롤의 읽기 전용 속성 간에 데이터와 **짧은** 데이터 멤버입니다.|
|[DDX_OCText](#ddx_octext)|으로의 전송을 관리 **CString** OLE 컨트롤의 속성 간에 데이터와 **CString** 데이터 멤버입니다.|
|[DDX_OCTextRO](#ddx_octextro)|으로의 전송을 관리 **CString** OLE 컨트롤의 읽기 전용 속성 간에 데이터와 **CString** 데이터 멤버입니다.|

##  <a name="ddx_ocbool"></a>  DDX_OCBool

합니다 `DDX_OCBool` 함수도의 전송을 관리 **BOOL** 대화 상자에서 OLE 컨트롤의 속성 간에 데이터 폼 뷰 또는 컨트롤 뷰 개체와 **BOOL** 대화 상자 폼 보기의 데이터 멤버 또는 컨트롤 뷰 개체입니다.

```
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*dispid*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*값*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더:** afxdisp.h

##  <a name="ddx_ocboolro"></a>  DDX_OCBoolRO

합니다 `DDX_OCBoolRO` 함수도의 전송을 관리 **BOOL** 대화 상자에서 OLE 컨트롤의 읽기 전용 속성 간에 데이터 폼 뷰 또는 컨트롤 뷰 개체와 **BOOL** 대화 상자의 데이터 멤버 폼 뷰 또는 컨트롤 뷰 개체입니다.

```
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    BOOL& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*dispid*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*값*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="ddx_occolor"></a>  DDX_OCColor

`DDX_OCColor` 함수 대화 상자 폼 보기에에서는 OLE 컨트롤의 속성 간에 OLE_COLOR 데이터의 전송을 관리 또는 컨트롤 뷰 개체 OLE_COLOR 데이터 멤버인 대화 상자 폼 보기에서 뷰 개체를 제어 합니다.

```
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*dispid*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*값*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="ddx_occolorro"></a>  DDX_OCColorRO

`DDX_OCColorRO` 함수 대화 상자 폼 보기에에서는 OLE 컨트롤의 읽기 전용 속성 간의 OLE_COLOR 데이터의 전송을 관리 또는 컨트롤 뷰 개체 OLE_COLOR 데이터 멤버인 대화 상자 폼 보기에서 뷰 개체를 제어 합니다.

```
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    OLE_COLOR& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*dispid*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*값*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="ddx_ocfloat"></a>  DDX_OCFloat

합니다 `DDX_OCFloat` 함수도의 전송을 관리 **float** (또는 **double**) 대화 상자에서 OLE 컨트롤의 속성 간에 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 **float** (또는 **이중**) 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.

```
void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    float& value);

void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    double& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*dispid*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*값*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="ddx_ocfloatro"></a>  DDX_OCFloatRO

합니다 `DDX_OCFloatRO` 함수도의 전송을 관리 **float** (또는 **double**) 대화 상자에서 OLE 컨트롤의 읽기 전용 속성 간에 데이터 폼 뷰 또는 컨트롤 뷰 개체 및  **부동 소수점** (또는 **double**) 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.

```
void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    float& value);

void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    double& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*dispid*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*값*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="ddx_ocint"></a>  DDX_OCInt

합니다 `DDX_OCInt` 함수도의 전송을 관리 **int** (또는 **long**) 대화 상자에서 OLE 컨트롤의 속성 간에 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 **int**(또는 **긴**) 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.

```
void AFXAPI DDX_OCInt(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    int& value);

void AFXAPI DDX_OCInt(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    long& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*dispid*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*값*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="ddx_ocintro"></a>  DDX_OCIntRO

합니다 `DDX_OCIntRO` 함수도의 전송을 관리 **int** (또는 **long**) 대화 상자에서 OLE 컨트롤의 읽기 전용 속성 간에 데이터 폼 뷰 또는 컨트롤 뷰 개체 및 **int** (또는 **긴**) 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 데이터 멤버입니다.

```
void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    int& value);

void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    long& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*dispid*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*값*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="ddx_ocshort"></a>  DDX_OCShort

`DDX_OCShort` 함수 대화 상자 폼 보기에에서는 OLE 컨트롤의 속성 간에 간단한 데이터 전송을 관리 또는 컨트롤 뷰 개체 및 간단한 데이터 멤버인 대화 상자 폼 보기에서 뷰 개체를 제어 합니다.

```
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*dispid*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*값*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="ddx_ocshortro"></a>  DDX_OCShortRO

`DDX_OCShortRO` 함수 대화 상자 폼 보기에에서는 OLE 컨트롤의 읽기 전용 속성 간의 간단한 데이터 전송을 관리 또는 컨트롤 뷰 개체 및 간단한 데이터 멤버인 대화 상자 폼 보기에서 뷰 개체를 제어 합니다.

```
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    short& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*dispid*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*값*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="ddx_octext"></a>  DDX_OCText

합니다 **DDX_OCText** 함수도의 전송을 관리 **CString** 대화 상자에서 OLE 컨트롤의 속성 간에 데이터 폼 뷰 또는 컨트롤 뷰 개체와 **CString** 데이터 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버입니다.

```
void AFXAPI DDX_OCText(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 **CDataExchange** 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*dispid*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*값*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

##  <a name="ddx_octextro"></a>  DDX_OCTextRO

`DDX_OCTextRO` 함수는 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체 내 OLE 컨트롤의 읽기 전용 속성과 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 `CString` 데이터 멤버 간 `CString` 데이터 전송을 관리합니다.

```
void AFXAPI DDX_OCTextRO(
    CDataExchange* pDX,
    int nIDC,
    DISPID dispid,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*nIDC*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 OLE 컨트롤 ID입니다.

*dispid*<br/>
컨트롤의 속성에 대한 디스패치 ID입니다.

*값*<br/>
데이터를 교환할 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수에 대한 참조입니다.

### <a name="remarks"></a>설명

DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

### <a name="requirements"></a>요구 사항

  **헤더** afxdisp.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
