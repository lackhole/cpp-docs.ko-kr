---
title: CDateTimeCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CloseMonthCal
- AFXDTCTL/CDateTimeCtrl::Create
- AFXDTCTL/CDateTimeCtrl::GetDateTimePickerInfo
- AFXDTCTL/CDateTimeCtrl::GetIdealSize
- AFXDTCTL/CDateTimeCtrl::GetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::GetMonthCalCtrl
- AFXDTCTL/CDateTimeCtrl::GetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::GetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::GetRange
- AFXDTCTL/CDateTimeCtrl::GetTime
- AFXDTCTL/CDateTimeCtrl::SetFormat
- AFXDTCTL/CDateTimeCtrl::SetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::SetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::SetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::SetRange
- AFXDTCTL/CDateTimeCtrl::SetTime
helpviewer_keywords:
- CDateTimeCtrl [MFC], CDateTimeCtrl
- CDateTimeCtrl [MFC], CloseMonthCal
- CDateTimeCtrl [MFC], Create
- CDateTimeCtrl [MFC], GetDateTimePickerInfo
- CDateTimeCtrl [MFC], GetIdealSize
- CDateTimeCtrl [MFC], GetMonthCalColor
- CDateTimeCtrl [MFC], GetMonthCalCtrl
- CDateTimeCtrl [MFC], GetMonthCalFont
- CDateTimeCtrl [MFC], GetMonthCalStyle
- CDateTimeCtrl [MFC], GetRange
- CDateTimeCtrl [MFC], GetTime
- CDateTimeCtrl [MFC], SetFormat
- CDateTimeCtrl [MFC], SetMonthCalColor
- CDateTimeCtrl [MFC], SetMonthCalFont
- CDateTimeCtrl [MFC], SetMonthCalStyle
- CDateTimeCtrl [MFC], SetRange
- CDateTimeCtrl [MFC], SetTime
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
ms.openlocfilehash: 8c69473ab813c2fa692044fddc406a74a5aeb197
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779822"
---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl 클래스

날짜 및 시간 선택 컨트롤의 기능을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CDateTimeCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|`CDateTimeCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|현재 날짜 및 시간 선택 컨트롤을 닫습니다.|
|[CDateTimeCtrl::Create](#create)|날짜 및 시간 선택 컨트롤을 만들고이에 연결 된 `CDateTimeCtrl` 개체입니다.|
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|현재 날짜 및 시간 선택 컨트롤에 대 한 정보를 검색합니다.|
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|현재 날짜 또는 시간을 표시 하는 데 필요한 날짜 및 시간 선택 컨트롤의 이상적인 크기를 반환 합니다.|
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|월 달력 날짜 및 시간 선택 컨트롤 내에서 지정 된 부분에 대 한 색을 검색합니다.|
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|검색 된 `CMonthCalCtrl` 날짜 및 시간 선택 컨트롤을 사용 하 여 연결 된 개체입니다.|
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|현재 날짜 및 시간 선택 컨트롤의 자식 monthcalendar 컨트롤에서 사용 된 글꼴을 검색 합니다.|
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|현재 날짜 및 시간 선택 컨트롤의 스타일을 가져옵니다.|
|[CDateTimeCtrl::GetRange](#getrange)|날짜 및 시간 선택 컨트롤에 대 한 시스템 시간을 허용 하는 현재 최소 및 최대 검색 합니다.|
|[CDateTimeCtrl::GetTime](#gettime)|날짜 및 시간 선택 컨트롤에서 현재 선택한 시간을 검색 하 고 지정 된 배치 `SYSTEMTIME` 구조입니다.|
|[CDateTimeCtrl::SetFormat](#setformat)|지정 된 형식 문자열에 따라 날짜 및 시간 선택 컨트롤의 표시를 설정합니다.|
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|월 달력 날짜 및 시간 선택 컨트롤 내에서 지정 된 부분에 대 한 색을 설정합니다.|
|[CDateTimeCtrl::SetMonthCalFont](#setmonthcalfont)|날짜 및 시간 선택 컨트롤의 자식 monthcalendar 컨트롤에 사용할 글꼴을 설정 합니다.|
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|현재 날짜 및 시간 선택 컨트롤의 스타일을 설정 합니다.|
|[CDateTimeCtrl::SetRange](#setrange)|날짜 및 시간 선택 컨트롤에 대 한 최소 및 최대 허용된 시스템 시간을 설정합니다.|
|[CDateTimeCtrl::SetTime](#settime)|날짜 및 시간 선택 컨트롤에서 시간을 설정합니다.|

## <a name="remarks"></a>설명

날짜 및 시간 선택 컨트롤 (DTP 컨트롤)는 사용자를 사용 하 여 날짜 및 시간 정보를 교환 하기 위한 간단한 인터페이스를 제공 합니다. 이 인터페이스는 컨트롤에 저장 된 날짜 및 시간 정보 중 일부를 표시 하는 각 필드를 포함 합니다. 사용자 지정된 필드의 문자열의 내용을 변경 하 여 컨트롤에 저장 된 정보를 변경할 수 있습니다. 사용자는 마우스 또는 키보드 필드를 사용 하 여 이동할 수 있습니다.

만들 때 개체에 다양 한 스타일을 적용 하 여 날짜 및 시간 선택 컨트롤을 사용자 지정할 수 있습니다. 참조 [날짜 및 시간 선택 컨트롤 스타일](/windows/desktop/Controls/date-and-time-picker-control-styles) 스타일 특정 날짜 및 시간 선택 컨트롤에 대 한 자세한 내용은 Windows SDK에 있습니다. 형식 스타일을 사용 하 여 DTP 컨트롤의 표시 형식을 설정할 수 있습니다. Windows SDK 항목에서 이러한 형식 스타일 "형식 스타일" 아래에서 설명 [날짜 및 시간 선택 컨트롤 스타일](/windows/desktop/Controls/date-and-time-picker-control-styles)합니다.

날짜 및 시간 선택 컨트롤 또한 사용 하 여 알림 및 설명 하는 콜백을 [CDateTimeCtrl 사용 하 여](../../mfc/using-cdatetimectrl.md)입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDateTimeCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** 있는 afxdtctl.h

##  <a name="cdatetimectrl"></a>  CDateTimeCtrl::CDateTimeCtrl

`CDateTimeCtrl` 개체를 생성합니다.

```
CDateTimeCtrl();
```

##  <a name="closemonthcal"></a>  CDateTimeCtrl::CloseMonthCal

현재 날짜 및 시간 선택 컨트롤을 닫습니다.

```
void CloseMonthCal() const;
```

### <a name="remarks"></a>설명

이 메서드는 전송 된 [DTM_CLOSEMONTHCAL](/windows/desktop/Controls/dtm-closemonthcal) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 *m_dateTimeCtrl*즉, 날짜 및 시간 선택 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 현재 날짜 및 시간 선택 컨트롤에 대 한 드롭다운 달력을 닫습니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]

##  <a name="create"></a>  CDateTimeCtrl::Create

날짜 및 시간 선택 컨트롤을 만들고이에 연결 된 `CDateTimeCtrl` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
날짜 시간 컨트롤 스타일의 조합을 지정합니다. 참조 [날짜 및 시간 선택 컨트롤 스타일](/windows/desktop/Controls/date-and-time-picker-control-styles) 날짜 및 시간 선택 스타일에 대 한 자세한 내용은 Windows SDK에 있습니다.

*rect*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조는 위치와 날짜 및 시간 선택 컨트롤의 크기입니다.

*pParentWnd*<br/>
에 대 한 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) 개체의 날짜 및 시간 선택 컨트롤의 부모 창입니다. NULL이 아니어야 합니다.

*nID*<br/>
지정 된 날짜 및 시간 선택 컨트롤의 컨트롤 id입니다.

### <a name="return-value"></a>반환 값

만들기에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

##### <a name="to-create-a-date-and-time-picker-control"></a>날짜 및 시간 선택 컨트롤을 만들려면

1. 호출 [CDateTimeCtrl](#cdatetimectrl) 생성 하는 `CDateTimeCtrl` 개체입니다.

1. Windows 날짜 및 시간 선택 컨트롤을 만들고에 연결 하는이 멤버 함수를 호출 합니다 `CDateTimeCtrl` 개체입니다.

호출 하는 경우 `Create`, 공용 컨트롤 초기화 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]

##  <a name="getdatetimepickerinfo"></a>  CDateTimeCtrl::GetDateTimePickerInfo

현재 날짜 및 시간 선택 컨트롤에 대 한 정보를 검색합니다.

```
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*pDateTimePickerInfo*|[out] 에 대 한 포인터를 [DATETIMEPICKERINFO](/windows/desktop/api/commctrl/ns-commctrl-tagdatetimepickerinfo) 구조체의 현재 날짜 및 시간 선택 컨트롤의 설명입니다.<br /><br /> 호출자는이 구조를 할당 하는 일을 담당 합니다. 그러나이 메서드를 초기화 합니다 *cbSize* 구조체의 멤버입니다.|

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [DTM_GETDATETIMEPICKERINFO](/windows/desktop/Controls/dtm-getdatetimepickerinfo) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 *m_dateTimeCtrl*즉, 날짜 및 시간 선택 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 현재 날짜 및 시간 선택 컨트롤에 대 한 정보 성공적으로 검색 하는지 여부를 나타냅니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]

##  <a name="getmonthcalcolor"></a>  CDateTimeCtrl::GetMonthCalColor

월 달력 날짜 및 시간 선택 컨트롤 내에서 지정 된 부분에 대 한 색을 검색합니다.

```
COLORREF GetMonthCalColor(int iColor) const;
```

### <a name="parameters"></a>매개 변수

*iColor*<br/>
**int** 색 영역 검색할 달력을 지정 하는 값입니다. 값의 목록을 참조 하세요. 합니다 *iColor* 에 대 한 매개 변수 [SetMonthCalColor](#setmonthcalcolor)합니다.

### <a name="return-value"></a>반환 값

성공할 경우 달력 컨트롤의 지정된 된 부분에 대 한 색 설정을 나타내는 COLORREF 값입니다. 실패 한 경우-1이 반환 됩니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_GETMCCOLOR](/windows/desktop/Controls/dtm-getmccolor)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]

##  <a name="getmonthcalctrl"></a>  CDateTimeCtrl::GetMonthCalCtrl

검색 된 `CMonthCalCtrl` 날짜 및 시간 선택 컨트롤을 사용 하 여 연결 된 개체입니다.

```
CMonthCalCtrl* GetMonthCalCtrl() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) 개체 또는 실패 한 경우 또는 창이 표시 되지 않으면 NULL입니다.

### <a name="remarks"></a>설명

날짜 및 시간 선택 컨트롤에서 드롭다운 화살표를 클릭할 때 자식 monthcalendar 컨트롤을 만듭니다. 경우는 `CMonthCalCtrl` 제거 되기, 응용 프로그램 날짜 시간 선택 컨트롤의 자식 달력을 나타내는 개체를 저장에 사용할 수 있어야 하므로, 개체가 더 이상 필요 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]

##  <a name="getmonthcalfont"></a>  CDateTimeCtrl::GetMonthCalFont

날짜 및 시간 선택 컨트롤의 monthcalendar 컨트롤에서 현재 사용 하는 글꼴을 가져옵니다.

```
CFont* GetMonthCalFont() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CFont](../../mfc/reference/cfont-class.md) 개체 또는 실패 한 경우 NULL입니다.

### <a name="remarks"></a>설명

`CFont` 반환 값에서 가리키는 개체는 임시 개체 이며 다음 유휴 처리 시간 동안 제거 됩니다.

##  <a name="getmonthcalstyle"></a>  CDateTimeCtrl::GetMonthCalStyle

현재 날짜 및 시간 선택 컨트롤을 사용 하 여 연결 된 드롭다운 month calendar 컨트롤의 스타일을 가져옵니다.

```
DWORD GetMonthCalStyle() const;
```

### <a name="return-value"></a>반환 값

드롭다운 달력 컨트롤, 비트 결합 된 (또는) 날짜 및 시간 선택 컨트롤 스타일의 스타일입니다. 자세한 내용은 [Month Calendar 컨트롤 스타일](/windows/desktop/Controls/month-calendar-control-styles)합니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [DTM_GETMCSTYLE](/windows/desktop/Controls/dtm-getmcstyle) Windows SDK에 설명 된 메시지입니다.

##  <a name="getrange"></a>  CDateTimeCtrl::GetRange

날짜 및 시간 선택 컨트롤에 대 한 시스템 시간을 허용 하는 현재 최소 및 최대 검색 합니다.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;
```

### <a name="parameters"></a>매개 변수

*pMinRange*<br/>
에 대 한 포인터를 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 허용 되는 가장 이른 시간을 포함 하는 `CDateTimeCtrl` 개체입니다.

*pMaxRange*<br/>
에 대 한 포인터를 `COleDateTime` 개체 또는 `CTime` 개체에서 허용 된 가장 늦은 시간을 포함 하는 `CDateTimeCtrl` 개체입니다.

### <a name="return-value"></a>반환 값

범위가 설정 된 플래그를 포함 하는 DWORD 값입니다. 조건

`return value & GDTR_MAX` == 0

두 번째 매개 변수는 유효 합니다. 마찬가지로, 하는 경우

`return value & GDTR_MIN` == 0

첫 번째 매개 변수는 유효 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_GETRANGE](/windows/desktop/Controls/dtm-getrange)Windows SDK에 설명 된 대로 합니다. MFC의 구현에 지정할 수 있습니다 `COleDateTime` 또는 `CTime` 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]

##  <a name="gettime"></a>  CDateTimeCtrl::GetTime

날짜 및 시간 선택 컨트롤에서 현재 선택한 시간을 검색 하 고 지정 된 배치 `SYSTEMTIME` 구조입니다.

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>매개 변수

*timeDest*<br/>
첫 번째 버전에서는에 대 한 참조를 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 시스템 시간 정보를 받게 될 개체입니다. 두 번째 버전에서는에 대 한 참조를 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 시스템 시간 정보를 받게 될 개체입니다.

*pTimeDest*<br/>
에 대 한 포인터를 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 시스템 시간 정보를 받는 구조체입니다. NULL이 아니어야 합니다.

### <a name="return-value"></a>반환 값

시간에 성공적으로 작성 되는 경우 0이 아닌 첫 번째 버전에서은 `COleDateTime` 개체 그렇지 않으면 0입니다. 두 번째와 세 번째 버전에서는 DWORD 값 같음 합니다 *dwFlag* 집합의 구성원을 [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) 구조입니다. 참조 된 **주의** 자세한 내용은 아래 섹션입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_GETSYSTEMTIME](/windows/desktop/Controls/dtm-getsystemtime)Windows SDK에 설명 된 대로 합니다. MFC 구현에서 `GetTime`를 사용할 수 있습니다 `COleDateTime` 또는 `CTime` 클래스를 사용할 수 있습니다를 `SYSTEMTIME` 시간 정보를 저장할 구조입니다.

반환 값은 DWORD 두 번째와 세 번째 버전에서는 위의 나타냅니다 "날짜 없음" 상태에 날짜 및 시간 선택 컨트롤을 설정할지 여부에 표시 된 대로 합니다 [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) 구조체 멤버 *dwFlags* . 반환 되는 값 같음 GDT_NONE, 컨트롤 "날짜 없음" 상태에 설정 되 고 DTS_SHOWNONE 스타일을 사용 합니다. 반환 된 값 GDT_VALID 같으면 시스템 시간 대상 위치에 성공적으로 저장 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]

##  <a name="getidealsize"></a>  CDateTimeCtrl::GetIdealSize

현재 날짜 또는 시간을 표시 하는 데 필요한 날짜 및 시간 선택 컨트롤의 이상적인 크기를 반환 합니다.

```
BOOL GetIdealSize(LPSIZE psize) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*psize*|[out] 에 대 한 포인터를 [크기](/windows/desktop/api/windef/ns-windef-tagsize) 컨트롤에 대 한 이상적인 크기를 포함 하는 구조입니다.|

### <a name="return-value"></a>반환 값

반환 값은 항상 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [DTM_GETIDEALSIZE](/windows/desktop/Controls/dtm-getidealsize) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 *m_dateTimeCtrl*즉, 날짜 및 시간 선택 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 날짜 및 시간 선택 컨트롤을 표시 하 여 이상적인 크기를 검색 합니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]

##  <a name="setformat"></a>  CDateTimeCtrl::SetFormat

지정 된 형식 문자열에 따라 날짜 및 시간 선택 컨트롤의 표시를 설정합니다.

```
BOOL SetFormat(LPCTSTR pstrFormat);
```

### <a name="parameters"></a>매개 변수

*pstrFormat*<br/>
원하는 표시를 정의 하는 0으로 끝나는 형식 문자열에 대 한 포인터입니다. 이 매개 변수를 NULL로 설정 하면 컨트롤 현재 스타일에 대 한 기본 형식 문자열을 다시 설정 됩니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

> [!NOTE]
>  사용자 입력이이 호출의 성공 또는 실패를 확인 하지 않습니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETFORMAT](/windows/desktop/Controls/dtm-setformat)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]

##  <a name="setmonthcalcolor"></a>  CDateTimeCtrl::SetMonthCalColor

월 달력 날짜 및 시간 선택 컨트롤 내에서 지정 된 부분에 대 한 색을 설정합니다.

```
COLORREF SetMonthCalColor(
    int iColor,
    COLORREF ref);
```

### <a name="parameters"></a>매개 변수

*iColor*<br/>
**int** month calendar 컨트롤을 설정 하는 영역을 지정 하는 값입니다. 이 값 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|MCSC_BACKGROUND|월 사이 표시 되는 배경색을 설정 합니다.|
|MCSC_MONTHBK|한 달 내에 표시 되는 배경색을 설정 합니다.|
|MCSC_TEXT|한 달이 내의 텍스트를 표시 하는데 사용 된 색을 설정 합니다.|
|MCSC_TITLEBK|달력의 제목에 표시 되는 배경 색을 설정 합니다.|
|MCSC_TITLETEXT|달력 제목의 내의 텍스트를 표시 하는데 사용 된 색을 설정 합니다.|
|MCSC_TRAILINGTEXT|헤더 및 후행 일 텍스트를 표시 하는데 사용 된 색을 설정 합니다. 헤더 후행 날짜와 현재 달력에 표시 되는 이전 및 다음 달의 날짜입니다.|

*ref*<br/>
월 달력의 지정된 된 영역에 대해 설정할 색을 나타내는 COLORREF 값입니다.

### <a name="return-value"></a>반환 값

성공할 경우 달력 컨트롤의 지정된 된 부분에 대 한 이전 색 설정을 나타내는 COLORREF 값입니다. 그렇지 않으면 메시지는-1을 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETMCCOLOR](/windows/desktop/Controls/dtm-setmccolor)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)합니다.

##  <a name="setmonthcalfont"></a>  CDateTimeCtrl::SetMonthCalFont

날짜 및 시간 선택 컨트롤의 자식 monthcalendar 컨트롤에 사용할 글꼴을 설정 합니다.

```
void SetMonthCalFont(
    HFONT hFont,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>매개 변수

*hFont*<br/>
설정 될 글꼴에 대 한 핸들입니다.

*bRedraw*<br/>
글꼴 설정 시 컨트롤을 즉시 그려야 하는지 여부를 지정 합니다. 이 매개 변수를 TRUE로 설정 하면 컨트롤을 다시 그리도록 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETMCFONT](/windows/desktop/Controls/dtm-setmcfont)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]

> [!NOTE]
>  멤버를 확인 하려는 경우이 코드를 사용 하 여 `CDialog`-라는 클래스를 파생 *m_MonthFont* 형식의 `CFont`합니다.

##  <a name="setmonthcalstyle"></a>  CDateTimeCtrl::SetMonthCalStyle

현재 날짜 및 시간 선택 컨트롤을 사용 하 여 연결 된 드롭다운 month calendar 컨트롤의 스타일을 설정 합니다.

```
DWORD SetMonthCalStyle(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*dwStyle*|[in] 새로운 달 calendar month calendar 컨트롤 스타일의 비트 조합 (OR) 컨트롤 스타일입니다. 자세한 내용은 [Month Calendar 컨트롤 스타일](/windows/desktop/Controls/month-calendar-control-styles)합니다.|

### <a name="return-value"></a>반환 값

이전 스타일 드롭다운 달력 컨트롤입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [DTM_SETMCSTYLE](/windows/desktop/Controls/dtm-setmcstyle) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 *m_dateTimeCtrl*즉, 날짜 및 시간 선택 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 주 번호, 요일, 그리고 없습니다 오늘 표시기의 약식된 이름을 표시할 날짜 및 시간 선택 컨트롤을 설정 합니다.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]

##  <a name="setrange"></a>  CDateTimeCtrl::SetRange

날짜 및 시간 선택 컨트롤에 대 한 최소 및 최대 허용된 시스템 시간을 설정합니다.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);
```

### <a name="parameters"></a>매개 변수

*pMinRange*<br/>
에 대 한 포인터를 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체에 허용 되는 가장 이른 시간을 포함 하는 `CDateTimeCtrl` 개체입니다.

*pMaxRange*<br/>
에 대 한 포인터를 `COleDateTime` 개체 또는 `CTime` 개체에서 허용 된 가장 늦은 시간을 포함 하는 `CDateTimeCtrl` 개체입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETRANGE](/windows/desktop/Controls/dtm-setrange)Windows SDK에 설명 된 대로 합니다. MFC의 구현에 지정할 수 있습니다 `COleDateTime` 또는 `CTime` 사용 합니다. 경우는 `COleDateTime` 개체에 NULL 상태, 범위 제거 됩니다. 경우는 `CTime` 포인터 또는 `COleDateTime` 포인터가 NULL 이면 범위 제거 됩니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CDateTimeCtrl::GetRange](#getrange)합니다.

##  <a name="settime"></a>  CDateTimeCtrl::SetTime

날짜 및 시간 선택 컨트롤에서 시간을 설정합니다.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* pTimeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```

### <a name="parameters"></a>매개 변수

*timeNew*<br/>
에 대 한 참조를 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체를 포함 하는 컨트롤을 설정 해야 합니다.

*pTimeNew*<br/>
에 대 한 포인터 위의 두 번째 버전을 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 컨트롤은 설정할 시간을 포함 하는 개체입니다. 에 대 한 포인터 위의 세 번째 버전에는 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 컨트롤은 설정할 시간을 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [DTM_SETSYSTEMTIME](/windows/desktop/Controls/dtm-setsystemtime)Windows SDK에 설명 된 대로 합니다. MFC 구현에서 `SetTime`를 사용할 수는 `COleDateTime` 또는 `CTime` 클래스를 사용할 수 있습니다를 `SYSTEMTIME` 시간 정보를 설정 하려면 구조를 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CMonthCalCtrl 클래스](../../mfc/reference/cmonthcalctrl-class.md)
