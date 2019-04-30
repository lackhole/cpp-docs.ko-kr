---
title: 표준 대화 상자 데이터 유효성 검사 루틴
ms.date: 11/04/2016
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
ms.openlocfilehash: 77b08945c99b9e9e2652a40e5710d8c4e89846b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309995"
---
# <a name="standard-dialog-data-validation-routines"></a>표준 대화 상자 데이터 유효성 검사 루틴

이 항목에서는 일반적인 MFC 대화 상자 컨트롤에 사용 되는 표준 대화 상자 데이터 유효성 검사 (DDV) 루틴을 나열 합니다.

> [!NOTE]
>  표준 대화 상자 데이터 교환 루틴은 헤더 파일 afxdd_.h에 정의 됩니다. 그러나 응용 프로그램에는 afxwin.h를 포함 되어야 합니다.

### <a name="ddv-functions"></a>DDV 함수

|||
|-|-|
|[DDV_MaxChars](#ddv_maxchars)|지정 된 컨트롤 값의 문자 수가 지정된 된 최대 초과 하지 확인 합니다.|
|[DDV_MinMaxByte](#ddv_minmaxbyte)|지정 된 컨트롤 값을 초과 하지 확인을 주어진 **바이트** 범위입니다.|
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|지정 된 컨트롤을 지정 된 시간 범위를 초과 하지 확인 합니다.|
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|지정 된 컨트롤 값을 초과 하지 확인을 지정 **이중** 범위입니다.|
|[DDV_MinMaxDWord](#ddv_minmaxdword)|지정 된 컨트롤 값을 초과 하지 확인을 주어진 **DWORD** 범위입니다.|
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|지정 된 컨트롤 값을 초과 하지 확인을 주어진 **float** 범위입니다.|
|[DDV_MinMaxInt](#ddv_minmaxint)|지정 된 컨트롤 값을 초과 하지 확인을 주어진 **int** 범위입니다.|
|[DDV_MinMaxLong](#ddv_minmaxlong)|지정 된 컨트롤 값을 초과 하지 확인을 주어진 **긴** 범위.|
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|지정 된 컨트롤 값을 초과 하지 확인을 주어진 **LONGLONG** 범위입니다.|
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|지정 된 컨트롤을 지정 된 날짜 범위를 초과 하지 확인 합니다.|
|[DDV_MinMaxShort](#ddv_minmaxshort)|지정 된 컨트롤 값을 초과 하지 확인을 주어진 **짧은** 범위입니다.|
|[DDV_MinMaxSlider](#ddv_minmaxslider)|지정 된 범위에 속하는 지정 된 슬라이더 컨트롤을 확인 합니다.|
|[DDV_MinMaxUInt](#ddv_minmaxuint)|지정 된 컨트롤 값을 초과 하지 확인을 주어진 **UINT** 범위입니다.|
|[DDV_MinMaxUnsigned](#ddv_minmaxuint)|지정 된 컨트롤을 지정 된 두 값 사이 확인 합니다.|
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|지정 된 컨트롤 값을 초과 하지 확인을 주어진 **ULONGLONG** 범위입니다.|

##  <a name="ddv_maxchars"></a>  DDV_MaxChars

호출 `DDV_MaxChars` 컨트롤에 있는 문자의 크기 연관 확인 하려면 *값* 넘지 *nChars*합니다.

```
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,
    CString const& value,
    int nChars);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체는 데이터의 유효성이 검사의 멤버 변수 참조입니다.

*nChars*<br/>
최대 허용 문자 수입니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxbyte"></a>  DDV_MinMaxByte

호출 `DDV_MinMaxByte` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이가 *minVal* 하 고 *maxVal*합니다.

```
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,
    BYTE value,
    BYTE minVal,
    BYTE maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체는 데이터의 유효성이 검사의 멤버 변수 참조입니다.

*minVal*<br/>
최소값 (BYTE 형식의)입니다.

*maxVal*<br/>
(BYTE 형식의) 허용 되는 최대값입니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxdatetime"></a>  DDV_MinMaxDateTime

호출 `DDV_MinMaxDateTime` 컨트롤에서 날짜 및 시간 선택 날짜/시간 값을 확인 하려면 ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md))와 연결 된 *refValue* 사이가 *refMinRange*하 고 *refMaxRange*합니다.

```
void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다. 이 개체를 삭제할 필요가 없습니다.

*refValue*<br/>
에 대 한 참조를 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 하거나 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 대화 상자, 폼 뷰 또는 컨트롤 뷰 개체의 멤버 변수를 사용 하 여 연결 된 개체입니다. 이 개체의 유효성을 검사 데이터를 포함 합니다.

*refMinRange*<br/>
최소 날짜/시간 값을 허용 합니다.

*refMaxRange*<br/>
허용 되는 최대 날짜/시간 값입니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxdouble"></a>  DDV_MinMaxDouble

호출 `DDV_MinMaxDouble` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이가 *minVal* 하 고 *maxVal*합니다.

```
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,
    double const& value,
    double minVal,
    double maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체는 데이터의 유효성이 검사의 멤버 변수 참조입니다.

*minVal*<br/>
최 솟 값 (형식 **이중**) 허용 합니다.

*maxVal*<br/>
최 댓 값 (형식 **이중**) 허용 합니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxdword"></a>  DDV_MinMaxDWord

호출 `DDV_MinMaxDWord` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이가 *minVal* 하 고 *maxVal*합니다.

```
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,
    DWORD const& value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체는 데이터의 유효성이 검사의 멤버 변수 참조입니다.

*minVal*<br/>
최소값 (DWORD 유형의)입니다.

*maxVal*<br/>
(DWORD 유형의) 허용 되는 최대값입니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxfloat"></a>  DDV_MinMaxFloat

호출 `DDV_MinMaxFloat` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이가 *minVal* 하 고 *maxVal*합니다.

```
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,
    float value,
    float minVal,
    float maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체는 데이터의 유효성이 검사의 멤버 변수 참조입니다.

*minVal*<br/>
최 솟 값 (형식 **float**) 허용 합니다.

*maxVal*<br/>
최 댓 값 (형식 **float**) 허용 합니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxint"></a>  DDV_MinMaxInt

호출 `DDV_MinMaxInt` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이가 *minVal* 하 고 *maxVal*합니다.

```
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,
    int value,
    int minVal,
    int maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체는 데이터의 유효성이 검사의 멤버 변수 참조입니다.

*minVal*<br/>
최 솟 값 (형식 **int**) 허용 합니다.

*maxVal*<br/>
최 댓 값 (형식 **int**) 허용 합니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxlong"></a>  DDV_MinMaxLong

호출 `DDV_MinMaxLong` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이가 *minVal* 하 고 *maxVal*합니다.

```
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,
    long value,
    long minVal,
    long maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체는 데이터의 유효성이 검사의 멤버 변수 참조입니다.

*minVal*<br/>
최 솟 값 (형식 **긴**) 허용 합니다.

*maxVal*<br/>
최 댓 값 (형식 **긴**) 허용 합니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxlonglong"></a>  DDV_MinMaxLongLong

호출 `DDV_MinMaxLongLong` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이가 *minVal* 하 고 *maxVal*합니다.

```
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,
    LONGLONG value,
    LONGLONG minVal,
    LONGLONG maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체는 데이터의 유효성이 검사의 멤버 변수 참조입니다.

*minVal*<br/>
최소값 (LONGLONG 유형)의 수입니다.

*maxVal*<br/>
최대 값 (형식 LONGLONG) 허용 합니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxmonth"></a>  DDV_MinMaxMonth

호출 `DDV_MinMaxMonth` 컨트롤 월 달력에서 날짜/시간 값을 확인 하려면 ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md))와 연결 된 *refValue* 사이가 *refMinRange* 및 *refMaxRange*합니다.

```
void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    CTime& refValue,
    const CTime* refMinRange,
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,
    COleDateTime& refValue,
    const COleDateTime* refMinRange,
    const COleDateTime* refMaxRange);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*refValue*<br/>
형식의 개체에 대 한 참조가 `CTime` 또는 `COleDateTime` 폼 보기에서 대화 상자의 멤버 변수를 사용 하 여 연결 하거나 뷰 개체를 제어 합니다. 이 개체의 유효성을 검사 데이터를 포함 합니다. 이 참조의 경우 MFC 전달 `DDV_MinMaxMonth` 라고 합니다.

*refMinRange*<br/>
최소 날짜/시간 값을 허용 합니다.

*refMaxRange*<br/>
허용 되는 최대 날짜/시간 값입니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxshort"></a>  DDV_MinMaxShort

호출 `DDV_MinMaxShort` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이가 *minVal* 하 고 *maxVal*합니다.

```
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,
    short value,
    short minVal,
    short maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체는 데이터의 유효성이 검사의 멤버 변수 참조입니다.

*minVal*<br/>
최 솟 값 (형식 **짧은**) 허용 합니다.

*maxVal*<br/>
최 댓 값 (형식 **짧은**) 허용 합니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxslider"></a>  DDV_MinMaxSlider

호출 `DDV_MinMaxSlider` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이가 *minVal* 하 고 *maxVal*합니다.

```
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,
    DWORD value,
    DWORD minVal,
    DWORD maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
유효성을 검사할 값에 대 한 참조입니다. 이 매개 변수를 보유 하거나 슬라이더 컨트롤의 현재 위치를 설정 합니다.

*minVal*<br/>
허용 되는 최소값입니다.

*maxVal*<br/>
허용 되는 최대값입니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다. 슬라이더 컨트롤에 대 한 자세한 내용은 [CSliderCtrl 사용 하 여](../../mfc/using-csliderctrl.md)입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxuint"></a>  DDV_MinMaxUInt

호출 `DDV_MinMaxUInt` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이가 *minVal* 하 고 *maxVal*합니다.

```
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,
    UINT value,
    UINT minVal,
    UINT maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체는 데이터의 유효성이 검사의 멤버 변수 참조입니다.

*minVal*<br/>
최소값 (of 형식 UINT)입니다.

*maxVal*<br/>
최대 값 (형식 UINT) 허용 합니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

##  <a name="ddv_minmaxulonglong"></a>  DDV_MinMaxULongLong

호출 `DDV_MinMaxULongLong` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이가 *minVal* 하 고 *maxVal*합니다.

```
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,
    ULONGLONG value,
    ULONGLONG  minVal ,
    ULONGLONG  maxVal);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체는 데이터의 유효성이 검사의 멤버 변수 참조입니다.

*minVal*<br/>
최소값 (of ULONGLONG 형식)입니다.

*maxVal*<br/>
유형의 ULONGLONG 허용 되는 최대값입니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdd_.h

## <a name="ddvminmaxunsigned"></a>DDV_MinMaxUnsigned

호출 `DDV_MinMaxUnsigned` 연결 된 컨트롤의 값을 확인 하려면 *값* 사이가 *minVal* 하 고 *maxVal*합니다.

### <a name="syntax"></a>구문

```
   void AFXAPI DDV_MinMaxUnsigned(
       CDataExchange* pDX,
       unsigned value,
       unsigned minVal,
       unsigned maxVal );
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
`CDataExchange` 개체에 대한 포인터입니다. 프레임워크는 해당 방향을 포함해서 데이터 교환의 컨텍스트를 설정하기 위해 이 개체를 제공합니다.

*값*<br/>
대화 상자, 폼 뷰 또는 컨트롤 뷰 개체는 데이터의 유효성이 검사의 멤버 변수 참조입니다.

*minVal*<br/>
최 솟 값 (형식 **부호 없는** ) 허용 합니다.

*maxVal*<br/>
최 댓 값 (형식 **부호 없는** ) 허용 합니다.

### <a name="remarks"></a>설명

DDV에 대 한 자세한 내용은 참조 하세요. [대화 상자 데이터 교환 및 유효성 검사](../dialog-data-exchange-and-validation.md)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdd_.h

## <a name="see-also"></a>참고자료

[표준 대화 상자 데이터 교환 루틴](standard-dialog-data-exchange-routines.md)<br/>
[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[DDX_Slider](standard-dialog-data-exchange-routines.md#ddx_slider)<br/>
[DDX_FieldSlider](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md#ddx_fieldslider)
