---
title: CMonthCalCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::Create
- AFXDTCTL/CMonthCalCtrl::GetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::GetCalendarCount
- AFXDTCTL/CMonthCalCtrl::GetCalendarGridInfo
- AFXDTCTL/CMonthCalCtrl::GetCalID
- AFXDTCTL/CMonthCalCtrl::GetColor
- AFXDTCTL/CMonthCalCtrl::GetCurrentView
- AFXDTCTL/CMonthCalCtrl::GetCurSel
- AFXDTCTL/CMonthCalCtrl::GetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::GetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::GetMaxTodayWidth
- AFXDTCTL/CMonthCalCtrl::GetMinReqRect
- AFXDTCTL/CMonthCalCtrl::GetMonthDelta
- AFXDTCTL/CMonthCalCtrl::GetMonthRange
- AFXDTCTL/CMonthCalCtrl::GetRange
- AFXDTCTL/CMonthCalCtrl::GetSelRange
- AFXDTCTL/CMonthCalCtrl::GetToday
- AFXDTCTL/CMonthCalCtrl::HitTest
- AFXDTCTL/CMonthCalCtrl::IsCenturyView
- AFXDTCTL/CMonthCalCtrl::IsDecadeView
- AFXDTCTL/CMonthCalCtrl::IsMonthView
- AFXDTCTL/CMonthCalCtrl::IsYearView
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorderDefault
- AFXDTCTL/CMonthCalCtrl::SetCalID
- AFXDTCTL/CMonthCalCtrl::SetCenturyView
- AFXDTCTL/CMonthCalCtrl::SetColor
- AFXDTCTL/CMonthCalCtrl::SetCurrentView
- AFXDTCTL/CMonthCalCtrl::SetCurSel
- AFXDTCTL/CMonthCalCtrl::SetDayState
- AFXDTCTL/CMonthCalCtrl::SetDecadeView
- AFXDTCTL/CMonthCalCtrl::SetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::SetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::SetMonthDelta
- AFXDTCTL/CMonthCalCtrl::SetMonthView
- AFXDTCTL/CMonthCalCtrl::SetRange
- AFXDTCTL/CMonthCalCtrl::SetSelRange
- AFXDTCTL/CMonthCalCtrl::SetToday
- AFXDTCTL/CMonthCalCtrl::SetYearView
- AFXDTCTL/CMonthCalCtrl::SizeMinReq
- AFXDTCTL/CMonthCalCtrl::SizeRectToMin
helpviewer_keywords:
- CMonthCalCtrl [MFC], CMonthCalCtrl
- CMonthCalCtrl [MFC], Create
- CMonthCalCtrl [MFC], GetCalendarBorder
- CMonthCalCtrl [MFC], GetCalendarCount
- CMonthCalCtrl [MFC], GetCalendarGridInfo
- CMonthCalCtrl [MFC], GetCalID
- CMonthCalCtrl [MFC], GetColor
- CMonthCalCtrl [MFC], GetCurrentView
- CMonthCalCtrl [MFC], GetCurSel
- CMonthCalCtrl [MFC], GetFirstDayOfWeek
- CMonthCalCtrl [MFC], GetMaxSelCount
- CMonthCalCtrl [MFC], GetMaxTodayWidth
- CMonthCalCtrl [MFC], GetMinReqRect
- CMonthCalCtrl [MFC], GetMonthDelta
- CMonthCalCtrl [MFC], GetMonthRange
- CMonthCalCtrl [MFC], GetRange
- CMonthCalCtrl [MFC], GetSelRange
- CMonthCalCtrl [MFC], GetToday
- CMonthCalCtrl [MFC], HitTest
- CMonthCalCtrl [MFC], IsCenturyView
- CMonthCalCtrl [MFC], IsDecadeView
- CMonthCalCtrl [MFC], IsMonthView
- CMonthCalCtrl [MFC], IsYearView
- CMonthCalCtrl [MFC], SetCalendarBorder
- CMonthCalCtrl [MFC], SetCalendarBorderDefault
- CMonthCalCtrl [MFC], SetCalID
- CMonthCalCtrl [MFC], SetCenturyView
- CMonthCalCtrl [MFC], SetColor
- CMonthCalCtrl [MFC], SetCurrentView
- CMonthCalCtrl [MFC], SetCurSel
- CMonthCalCtrl [MFC], SetDayState
- CMonthCalCtrl [MFC], SetDecadeView
- CMonthCalCtrl [MFC], SetFirstDayOfWeek
- CMonthCalCtrl [MFC], SetMaxSelCount
- CMonthCalCtrl [MFC], SetMonthDelta
- CMonthCalCtrl [MFC], SetMonthView
- CMonthCalCtrl [MFC], SetRange
- CMonthCalCtrl [MFC], SetSelRange
- CMonthCalCtrl [MFC], SetToday
- CMonthCalCtrl [MFC], SetYearView
- CMonthCalCtrl [MFC], SizeMinReq
- CMonthCalCtrl [MFC], SizeRectToMin
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
ms.openlocfilehash: bd062a4e0d4db364c9cb628608c6af165dc0edc2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58777170"
---
# <a name="cmonthcalctrl-class"></a>CMonthCalCtrl 클래스

달력 컨트롤의 기능을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CMonthCalCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMonthCalCtrl::CMonthCalCtrl](#cmonthcalctrl)|`CMonthCalCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMonthCalCtrl::Create](#create)|Monthcalendar 컨트롤을 만들고에 연결 된 `CMonthCalCtrl` 개체입니다.|
|[CMonthCalCtrl::GetCalendarBorder](#getcalendarborder)|현재 달력 컨트롤의 테두리의 너비를 검색합니다.|
|[CMonthCalCtrl::GetCalendarCount](#getcalendarcount)|현재 달력 컨트롤에 표시 되는 일정을 검색 합니다.|
|[CMonthCalCtrl::GetCalendarGridInfo](#getcalendargridinfo)|현재 달력 컨트롤에 대 한 정보를 검색합니다.|
|[CMonthCalCtrl::GetCalID](#getcalid)|현재 달력 컨트롤에 대 한 일정 식별자를 검색합니다.|
|[CMonthCalCtrl::GetColor](#getcolor)|Monthcalendar 컨트롤의 지정 된 영역의 색을 가져옵니다.|
|[CMonthCalCtrl::GetCurrentView](#getcurrentview)|현재 달력 컨트롤에 현재 표시 되는 뷰를 검색 합니다.|
|[CMonthCalCtrl::GetCurSel](#getcursel)|현재 선택한 날짜에 표시 된 대로 시스템 시간을 검색 합니다.|
|[CMonthCalCtrl::GetFirstDayOfWeek](#getfirstdayofweek)|달력의 맨 왼쪽 열에 표시할 첫 번째 요일을 가져옵니다.|
|[CMonthCalCtrl::GetMaxSelCount](#getmaxselcount)|Monthcalendar 컨트롤에서 선택할 수 있는 일 현재 최대 수를 검색 합니다.|
|[CMonthCalCtrl::GetMaxTodayWidth](#getmaxtodaywidth)|현재 달력 컨트롤에 대 한 "현재" 문자열의 최대 너비를 검색합니다.|
|[CMonthCalCtrl::GetMinReqRect](#getminreqrect)|Monthcalendar 컨트롤에서 달을 표시 하는 데 필요한 최소 크기를 검색 합니다.|
|[CMonthCalCtrl::GetMonthDelta](#getmonthdelta)|Monthcalendar 컨트롤에 대 한 스크롤 비율을 검색합니다.|
|[CMonthCalCtrl::GetMonthRange](#getmonthrange)|검색 날짜 높음 및 낮음 제한 monthcalendar 컨트롤의 표시를 나타내는 정보입니다.|
|[CMonthCalCtrl::GetRange](#getrange)|Monthcalendar 컨트롤에서 설정할 현재 최소 및 최대 날짜를 검색 합니다.|
|[CMonthCalCtrl::GetSelRange](#getselrange)|현재 사용자가 선택한 날짜 범위의 상한 및 하 한 제한을 나타내는 날짜 정보를 검색 합니다.|
|[CMonthCalCtrl::GetToday](#gettoday)|Monthcalendar 컨트롤에 대 한 "현재"로 지정 된 날짜의 날짜 정보를 검색 합니다.|
|[CMonthCalCtrl::HitTest](#hittest)|화면의 지정 된 시점 monthcalendar 컨트롤의 어떤 부분 인지 확인 합니다.|
|[CMonthCalCtrl::IsCenturyView](#iscenturyview)|현재 달력 컨트롤의 현재 보기는 세기 뷰인지 여부를 나타냅니다.|
|[CMonthCalCtrl::IsDecadeView](#isdecadeview)|현재 달력 컨트롤의 현재 보기는 10 년 동안 뷰인지 여부를 나타냅니다.|
|[CMonthCalCtrl::IsMonthView](#ismonthview)|현재 달력 컨트롤의 현재 보기는 월 뷰인지 여부를 나타냅니다.|
|[CMonthCalCtrl::IsYearView](#isyearview)|현재 달력 컨트롤의 현재 보기는 연도 뷰인지 여부를 나타냅니다.|
|[CMonthCalCtrl::SetCalendarBorder](#setcalendarborder)|현재 달력 컨트롤의 테두리의 너비를 설정합니다.|
|[CMonthCalCtrl::SetCalendarBorderDefault](#setcalendarborderdefault)|현재 달력 컨트롤의 테두리의 기본 너비를 설정합니다.|
|[CMonthCalCtrl::SetCalID](#setcalid)|현재 달력 컨트롤에 대 한 일정 식별자를 설정합니다.|
|[CMonthCalCtrl::SetCenturyView](#setcenturyview)|세기 보기를 표시 하려면 현재 달력 컨트롤을 설정 합니다.|
|[CMonthCalCtrl::SetColor](#setcolor)|Monthcalendar 컨트롤의 지정 된 영역의 색을 설정합니다.|
|[CMonthCalCtrl::SetCurrentView](#setcurrentview)|지정된 된 뷰를 표시 하려면 현재 달력 컨트롤을 설정 합니다.|
|[CMonthCalCtrl::SetCurSel](#setcursel)|Monthcalendar 컨트롤에 대 한 현재 선택한 날짜를 설정합니다.|
|[CMonthCalCtrl::SetDayState](#setdaystate)|Monthcalendar 컨트롤의 일에 대 한 표시를 설정합니다.|
|[CMonthCalCtrl::SetDecadeView](#setdecadeview)|현재 달력 제어 10 년 동안 보기를 설정 합니다.|
|[CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)|달력의 맨 왼쪽 열에 표시할 요일을 설정 합니다.|
|[CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)|Monthcalendar 컨트롤에서 선택할 수 있는 일의 최대 수를 설정 합니다.|
|[CMonthCalCtrl::SetMonthDelta](#setmonthdelta)|Monthcalendar 컨트롤에 대 한 스크롤 비율을 설정합니다.|
|[CMonthCalCtrl::SetMonthView](#setmonthview)|월 보기를 표시 하려면 현재 달력 컨트롤을 설정 합니다.|
|[CMonthCalCtrl::SetRange](#setrange)|최소 및 최대 monthcalendar 컨트롤에 대 한 날짜를 설정 합니다.|
|[CMonthCalCtrl::SetSelRange](#setselrange)|집합 monthcalendar에 대 한 선택이 지정된 된 날짜 범위를 제어 합니다.|
|[CMonthCalCtrl::SetToday](#settoday)|현재 날짜에 대 한 달력 컨트롤을 설정합니다.|
|[CMonthCalCtrl::SetYearView](#setyearview)|현재 달력 제어 연도 보기를 설정 합니다.|
|[CMonthCalCtrl::SizeMinReq](#sizeminreq)|월 달력 제어 최소, 1 개월 크기를 표시 합니다.|
|[CMonthCalCtrl::SizeRectToMin](#sizerecttomin)|현재 month calendar 컨트롤에 대해 지정 된 사각형 크기에 맞는 모든 달력을 포함할 수 있는 가장 작은 사각형을 계산 합니다.|

## <a name="remarks"></a>설명

Month calendar 컨트롤 사용자 날짜를 선택할 수 있는 간단한 일정 인터페이스를 사용 하 여 사용자를 제공 합니다. 사용자에서 표시를 변경할 수 있습니다.

- 월 달의 뒤로 및 앞 스크롤입니다.

- 현재 텍스트 (MCS_NOTODAY 스타일은 사용 되지 않음) 하는 경우 현재 날짜를 표시 하려면 클릭 합니다.

- 한 달 또는 팝업 메뉴에서 연도 선택 합니다.

월을 사용자 지정할 수 있습니다 calendar 컨트롤을 만들 때 개체에 다양 한 스타일을 적용 하 여 합니다. 이러한 스타일에 설명 되어 있습니다 [Month Calendar 컨트롤 스타일](/windows/desktop/Controls/month-calendar-control-styles) Windows SDK에 있습니다.

Month calendar 컨트롤에는 1 개월 이상 표시할 수 있으며 굵게 표시 하 여 (예: 공휴일) 특수 한 일을 나타낼 수 있습니다 날짜입니다.

Month calendar 컨트롤 사용에 대 한 자세한 내용은 참조 하세요. [를 사용 하 여 CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CMonthCalCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** 있는 afxdtctl.h

##  <a name="cmonthcalctrl"></a>  CMonthCalCtrl::CMonthCalCtrl

`CMonthCalCtrl` 개체를 생성합니다.

```
CMonthCalCtrl();
```

### <a name="remarks"></a>설명

호출 해야 `Create` 개체를 생성 합니다.

##  <a name="create"></a>  CMonthCalCtrl::Create

Monthcalendar 컨트롤을 만들고에 연결 된 `CMonthCalCtrl` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(
    DWORD dwStyle,
    const POINT& pt,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
Month calendar 컨트롤에 적용 되는 Windows 스타일의 조합을 지정 합니다. 참조 [Month Calendar 컨트롤 스타일](/windows/desktop/Controls/month-calendar-control-styles) 스타일에 대 한 자세한 내용은 Windows SDK에 있습니다.

*rect*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조입니다. Month calendar 컨트롤의 크기와 위치를 포함합니다.

*pt*<br/>
에 대 한 참조를 [지점](/previous-versions/dd162805\(v=vs.85\)) month calendar 컨트롤의 위치를 식별 하는 구조입니다.

*pParentWnd*<br/>
에 대 한 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) 개체 month calendar 컨트롤의 부모 창입니다. NULL이 아니어야 합니다.

*nID*<br/>
Month calendar 컨트롤의 컨트롤 ID를 지정 합니다.

### <a name="return-value"></a>반환 값

초기화에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

달 calendar 컨트롤 두 단계에서:

1. 호출 [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) 생성 하는 `CMonthCalCtrl` 개체입니다.

1. Monthcalendar 컨트롤을 만들고에 연결 하는이 멤버 함수를 호출 합니다 `CMonthCalCtrl` 개체입니다.

호출 하는 경우 `Create`, 공용 컨트롤 초기화 됩니다. 버전 `Create` 있습니다 호출 크기가 어떻게 결정 합니다.

- 한 달 동안 컨트롤의 크기를 자동으로 조정 하는 MFC가 사용 하는 재정의 호출 합니다 *pt* 매개 변수입니다.

- 직접 컨트롤의 크기를 재정의 사용 하는이 함수를 호출 합니다 *rect* 매개 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]

##  <a name="getcalendarborder"></a>  CMonthCalCtrl::GetCalendarBorder

현재 달력 컨트롤의 테두리의 너비를 검색합니다.

```
int GetCalendarBorder() const;
```

### <a name="return-value"></a>반환 값

픽셀 단위의 컨트롤 테두리의 너비입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [MCM_GETCALENDARBORDER](/windows/desktop/Controls/mcm-getcalendarborder) Windows SDK에 설명 된 메시지입니다.

##  <a name="getcalendarcount"></a>  CMonthCalCtrl::GetCalendarCount

현재 달력 컨트롤에 표시 되는 일정을 검색 합니다.

```
int GetCalendarCount() const;
```

### <a name="return-value"></a>반환 값

Month calendar 컨트롤에 현재 표시 된 달력의 수입니다. 일정 수가 최대 허용된은 12입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [MCM_GETCALENDARCOUNT](/windows/desktop/Controls/mcm-getcalendarcount) Windows SDK에 설명 된 메시지입니다.

##  <a name="getcalendargridinfo"></a>  CMonthCalCtrl::GetCalendarGridInfo

현재 달력 컨트롤에 대 한 정보를 검색합니다.

```
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*pmcGridInfo*|[out] 에 대 한 포인터를 [MCGRIDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagmcgridinfo) 현재 month calendar 컨트롤에 대 한 정보를 수신 하는 구조입니다. 호출자가 할당 하 고이 구조체를 초기화 합니다.|

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [MCM_GETCALENDARGRIDINFO](/windows/desktop/Controls/mcm-getcalendargridinfo) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_monthCalCtrl`되는 달력 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 `GetCalendarGridInfo` 현재 month calendar 컨트롤에 표시 되는 달력 날짜를 검색 하는 방법입니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]

##  <a name="getcalid"></a>  CMonthCalCtrl::GetCalID

현재 달력 컨트롤에 대 한 일정 식별자를 검색합니다.

```
CALID GetCalID() const;
```

### <a name="return-value"></a>반환 값

중 하나는 [달력 식별자](/windows/desktop/Intl/calendar-identifiers) 상수입니다.

### <a name="remarks"></a>설명

일정 식별자를 나타내는 지역별 달력, 회교식 양력 (지역화) 또는 일본어와 같은 달력입니다. 응용 프로그램에 함수를 지원 되는 다양 한 언어를 가진 일정 식별자를 사용 수 있습니다.

이 메서드는 전송 된 [MCM_GETCALID](/windows/desktop/Controls/mcm-getcalid) Windows SDK에 설명 된 메시지입니다.

##  <a name="getcolor"></a>  CMonthCalCtrl::GetColor

이달의 영역의 색 calendar 컨트롤에서 지정 된 검색 *nRegion*합니다.

```
COLORREF GetColor(int nRegion) const;
```

### <a name="parameters"></a>매개 변수

*nRegion*<br/>
색 검색 되는 달력 컨트롤의 영역입니다. 값의 목록을 참조 하세요. 합니다 *nRegion* 의 매개 변수 [SetColor](#setcolor)합니다.

### <a name="return-value"></a>반환 값

A [COLORREF](/windows/desktop/gdi/colorref) 성공 month calendar 컨트롤의 부분을 사용 하 여 연결 된 색을 지정 하는 값입니다. 그렇지 않은 경우이 멤버 함수는-1을 반환 합니다.

##  <a name="getcurrentview"></a>  CMonthCalCtrl::GetCurrentView

현재 달력 컨트롤에 현재 표시 되는 뷰를 검색 합니다.

```
DWORD GetCurrentView() const;
```

### <a name="return-value"></a>반환 값

현재 뷰를 다음 값 중 하나에 의해 표시 됩니다.

|값|의미|
|-----------|-------------|
|MCMV_MONTH|월별 보기|
|MCMV_YEAR|연간 보기|
|MCMV_DECADE|10 년 동안 보기|
|MCMV_CENTURY|세기 보기|

### <a name="remarks"></a>설명

이 메서드는 전송 된 [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_monthCalCtrl`되는 달력 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

월 달력 보기는 다음 코드 예제에서는 보고서 컨트롤이 현재 표시 합니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]

##  <a name="getcursel"></a>  CMonthCalCtrl::GetCurSel

현재 선택한 날짜에 표시 된 대로 시스템 시간을 검색 합니다.

```
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;

BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>매개 변수

*refDateTime*<br/>
에 대 한 참조를 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 개체 또는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체입니다. 현재 시간을 받습니다.

*pDateTime*<br/>
에 대 한 포인터를 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 구조는 현재 선택 된 날짜 정보를 받게 됩니다. 이 매개 변수는 유효한 주소 여야 하며 NULL 일 수 없습니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 otherwize 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETCURSEL](/windows/desktop/Controls/mcm-getcursel)Windows SDK에 설명 된 대로 합니다.

> [!NOTE]
>  이 멤버 함수 스타일 MCS_MULTISELECT 설정 된 경우 실패 합니다.

MFC의 구현에서 `GetCurSel`를 지정할 수 있습니다를 `COleDateTime` 사용을 `CTime` 사용 또는 `SYSTEMTIME` 구조체 사용 합니다.

##  <a name="getfirstdayofweek"></a>  CMonthCalCtrl::GetFirstDayOfWeek

달력의 맨 왼쪽 열에 표시할 첫 번째 요일을 가져옵니다.

```
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;
```

### <a name="parameters"></a>매개 변수

*pbLocal*<br/>
부울 값에 대 한 포인터입니다. 값 0이 아닌 경우 컨트롤의 설정에는 제어판에서 설정이 일치 하지 않습니다.

### <a name="return-value"></a>반환 값

첫 번째 요일을 나타내는 정수 값입니다. 참조 **주의** 이러한 정수 나타내는 의미에 대 한 자세한 내용은 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETFIRSTDAYOFWEEK](/windows/desktop/Controls/mcm-getfirstdayofweek)Windows SDK에 설명 된 대로 합니다. 요일을 일 같이 정수로 표현 됩니다.

|값|요일|
|-----------|---------------------|
|0|Monday|
|1|화요일|
|2|수요일|
|3|목요일|
|4|금요일|
|5|토요일|
|6|일요일|

### <a name="example"></a>예제

  예를 참조 하세요 [CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)합니다.

##  <a name="getmaxselcount"></a>  CMonthCalCtrl::GetMaxSelCount

Monthcalendar 컨트롤에서 선택할 수 있는 일 현재 최대 수를 검색 합니다.

```
int GetMaxSelCount() const;
```

### <a name="return-value"></a>반환 값

컨트롤에 대해 선택할 수 있는 일의 총 수를 나타내는 정수 값입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETMAXSELCOUNT](/windows/desktop/Controls/mcm-getmaxselcount)Windows SDK에 설명 된 대로 합니다. 이 멤버 함수를 사용 하 여 MCS_MULTISELECT 스타일 집합을 사용 하 여 컨트롤에 대 한 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)합니다.

##  <a name="getmaxtodaywidth"></a>  CMonthCalCtrl::GetMaxTodayWidth

현재 달력 컨트롤에 대 한 "현재" 문자열의 최대 너비를 검색합니다.

```
DWORD GetMaxTodayWidth() const;
```

### <a name="return-value"></a>반환 값

"현재" 문자열 픽셀 너비입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_monthCalCtrl`되는 달력 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제는 `GetMaxTodayWidth` 메서드.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]

### <a name="remarks"></a>설명

사용자는 "현재" 문자열을 month calendar 컨트롤의 맨 아래에 표시 되는 클릭 하 여 현재 날짜를 반환할 수 있습니다. "현재" 문자열에는 레이블 텍스트 및 날짜 텍스트 포함 됩니다.

이 메서드는 전송 된 [MCM_GETMAXTODAYWIDTH](/windows/desktop/Controls/mcm-getmaxtodaywidth) Windows SDK에 설명 된 메시지입니다.

##  <a name="getminreqrect"></a>  CMonthCalCtrl::GetMinReqRect

Monthcalendar 컨트롤에서 달을 표시 하는 데 필요한 최소 크기를 검색 합니다.

```
BOOL GetMinReqRect(RECT* pRect) const;
```

### <a name="parameters"></a>매개 변수

*pRect*<br/>
에 대 한 포인터를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 경계 사각형 정보를 받는 구조체입니다. 이 매개 변수는 유효한 주소 여야 하며 NULL 일 수 없습니다.

### <a name="return-value"></a>반환 값

성공 하면이 멤버 함수 반환 0이 아닌 및 `lpRect` 해당 경계 정보를 수신 합니다. 실패할 경우 멤버 함수는 0을 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETMINREQRECT](/windows/desktop/Controls/mcm-getminreqrect)Windows SDK에 설명 된 대로 합니다.

##  <a name="getmonthdelta"></a>  CMonthCalCtrl::GetMonthDelta

Monthcalendar 컨트롤에 대 한 스크롤 비율을 검색합니다.

```
int GetMonthDelta() const;
```

### <a name="return-value"></a>반환 값

Month calendar 컨트롤에 대 한 스크롤 비율을 지정 합니다. 스크롤 비율 개월 사용자 스크롤 단추를 두 번 클릭할 때 컨트롤에서 표시를 이동 하는 것입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETMONTHDELTA](/windows/desktop/Controls/mcm-getmonthdelta)Windows SDK에 설명 된 대로 합니다.

##  <a name="getmonthrange"></a>  CMonthCalCtrl::GetMonthRange

검색 날짜 높음 및 낮음 제한 monthcalendar 컨트롤의 표시를 나타내는 정보입니다.

```
int GetMonthRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    CTime& refMinRange,
    CTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange,
    DWORD dwFlags) const;
```

### <a name="parameters"></a>매개 변수

*refMinRange*<br/>
에 대 한 참조를 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 하거나 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 사용할 수 있는 최소 날짜를 포함 하는 개체입니다.

*refMaxRange*<br/>
에 대 한 참조를 `COleDateTime` 또는 `CTime` 사용할 수 있는 최대 날짜를 포함 하는 개체입니다.

*pMinRange*<br/>
에 대 한 포인터를 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 범위의 가장 낮은 끝 날짜를 포함 하는 구조입니다.

*pMaxRange*<br/>
에 대 한 포인터를 `SYSTEMTIME` 범위의 가장 높은 끝 날짜를 포함 하는 구조입니다.

*dwFlags*<br/>
검색할 범위 제한의 범위를 지정 하는 값입니다. 이 값에는 다음 중 하나 여야 합니다.

|값|의미|
|-----------|-------------|
|GMR_DAYSTATE|선행 및 후행 표시 영역의 부분적 으로만 표시 되는 월을 포함 합니다.|
|GMR_VISIBLE|완전히 표시 되는 해당 월만 포함 됩니다.|

### <a name="return-value"></a>반환 값

나타내는 정수 범위를 몇 달 동안에서 두 제한에 의해 확장 되 나타난 *refMinRange* 하 고 *refMaxRange* 첫 번째와 두 번째 버전에서는 또는 *pMinRange* 및 *pMaxRange* 세 번째 버전에서입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETMONTHRANGE](/windows/desktop/Controls/mcm-getmonthrange)Windows SDK에 설명 된 대로 합니다. MFC의 구현에서 `GetMonthRange`를 지정할 수 있습니다 `COleDateTime` 사용을 `CTime` 사용 또는 `SYSTEMTIME` 구조체 사용 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMonthCalCtrl::SetDayState](#setdaystate)합니다.

##  <a name="getrange"></a>  CMonthCalCtrl::GetRange

Monthcalendar 컨트롤에서 설정할 현재 최소 및 최대 날짜를 검색 합니다.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;

DWORD GetRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>매개 변수

*pMinRange*<br/>
에 대 한 포인터를 `COleDateTime` 개체를 `CTime` 개체 또는 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 범위의 가장 낮은 끝 날짜를 포함 하는 구조입니다.

*pMaxRange*<br/>
에 대 한 포인터를 `COleDateTime` 개체를 `CTime` 개체 또는 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 범위의 가장 높은 끝 날짜를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

DWORD 0 일 수 있습니다 (제한이 설정 되어 있음) 또는 제한 정보를 지정 하는 다음 값의 조합입니다.

|값|의미|
|-----------|-------------|
|GDTR_MAX|컨트롤에 대 한 최대 한도 설정 됩니다. *pMaxRange* 유효 하 고 해당 날짜 정보를 포함 합니다.|
|GDTR_MIN|컨트롤에 대 한 최소 한도 설정 됩니다. *pMinRange* 유효 하 고 해당 날짜 정보를 포함 합니다.|

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETRANGE](/windows/desktop/Controls/mcm-getrange)Windows SDK에 설명 된 대로 합니다. MFC의 구현에서 `GetRange`를 지정할 수 있습니다를 `COleDateTime` 사용을 `CTime` 사용 또는 `SYSTEMTIME` 구조체 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]

##  <a name="getselrange"></a>  CMonthCalCtrl::GetSelRange

현재 사용자가 선택한 날짜 범위의 상한 및 하 한 제한을 나타내는 날짜 정보를 검색 합니다.

```
BOOL GetSelRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange) const;

BOOL GetSelRange(
    CTime& refMinRange,
    CTime& refMaxRange) const;

BOOL GetSelRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>매개 변수

*refMinRange*<br/>
에 대 한 참조를 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 하거나 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 사용할 수 있는 최소 날짜를 포함 하는 개체입니다.

*refMaxRange*<br/>
에 대 한 참조를 `COleDateTime` 또는 `CTime` 사용할 수 있는 최대 날짜를 포함 하는 개체입니다.

*pMinRange*<br/>
에 대 한 포인터를 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 범위의 가장 낮은 끝 날짜를 포함 하는 구조입니다.

*pMaxRange*<br/>
에 대 한 포인터를 `SYSTEMTIME` 범위의 가장 높은 끝 날짜를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETSELRANGE](/windows/desktop/Controls/mcm-getselrange)Windows SDK에 설명 된 대로 합니다. `GetSelRange` MCS_MULTISELECT 스타일을 사용 하지 않는 month calendar 컨트롤에 적용 하는 경우 실패 합니다.

MFC의 구현에서 `GetSelRange`를 지정할 수 있습니다 `COleDateTime` 사용을 `CTime` 사용 또는 `SYSTEMTIME` 구조체 사용 합니다.

##  <a name="gettoday"></a>  CMonthCalCtrl::GetToday

Monthcalendar 컨트롤에 대 한 "현재"로 지정 된 날짜의 날짜 정보를 검색 합니다.

```
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;

BOOL GetToday(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>매개 변수

*refDateTime*<br/>
에 대 한 참조를 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 하거나 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 현재 날짜를 나타내는 개체입니다.

*pDateTime*<br/>
에 대 한 포인터를 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 날짜 정보를 받는 구조체입니다. 이 매개 변수는 유효한 주소 여야 하며 NULL 일 수 없습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_GETTODAY](/windows/desktop/Controls/mcm-gettoday)Windows SDK에 설명 된 대로 합니다. MFC의 구현에서 `GetToday`를 지정할 수 있습니다를 `COleDateTime` 사용을 `CTime` 사용 또는 `SYSTEMTIME` 구조체 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]

##  <a name="hittest"></a>  CMonthCalCtrl::HitTest

지정된 된 위치에 있는 경우는 month calendar 컨트롤을 결정 합니다.

```
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```

### <a name="parameters"></a>매개 변수

*pMCHitTest*<br/>
에 대 한 포인터를 [MCHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-mchittestinfo) month calendar 컨트롤에 대 한 적중 횟수 테스트를 포함 하는 구조체를 가리킵니다.

### <a name="return-value"></a>반환 값

DWORD 값입니다. 같음 합니다 **uHit** 의 멤버는 `MCHITTESTINFO` 구조입니다.

### <a name="remarks"></a>설명

`HitTest` 사용 된 `MCHITTESTINFO` 적중 횟수 테스트에 대 한 정보를 포함 하는 구조입니다.

##  <a name="iscenturyview"></a>  CMonthCalCtrl::IsCenturyView

현재 달력 컨트롤의 현재 보기는 세기 뷰인지 여부를 나타냅니다.

```
BOOL IsCenturyView() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 현재 보기 세기 뷰입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) Windows SDK에 설명 된 메시지입니다. 메시지 MCMV_CENTURY 반환 하는 경우이 메서드는 TRUE를 반환 합니다.

##  <a name="isdecadeview"></a>  CMonthCalCtrl::IsDecadeView

현재 달력 컨트롤의 현재 보기는 10 년 동안 뷰인지 여부를 나타냅니다.

```
BOOL IsDecadeView() const;
```

### <a name="return-value"></a>반환 값

현재 보기는 10 년 동안 보기; 경우 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) Windows SDK에 설명 된 메시지입니다. 메시지 MCMV_DECADE 반환 하는 경우이 메서드는 TRUE를 반환 합니다.

##  <a name="ismonthview"></a>  CMonthCalCtrl::IsMonthView

현재 달력 컨트롤의 현재 보기는 월 뷰인지 여부를 나타냅니다.

```
BOOL IsMonthView() const;
```

### <a name="return-value"></a>반환 값

현재 보기 월 보기; 이면 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) Windows SDK에 설명 된 메시지입니다. 메시지 MCMV_MONTH 반환 하는 경우이 메서드는 TRUE를 반환 합니다.

##  <a name="isyearview"></a>  CMonthCalCtrl::IsYearView

현재 달력 컨트롤의 현재 보기는 연도 뷰인지 여부를 나타냅니다.

```
BOOL IsYearView() const;
```

### <a name="return-value"></a>반환 값

현재 연도 뷰가; 된 경우 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [MCM_GETCURRENTVIEW](/windows/desktop/Controls/mcm-getcurrentview) Windows SDK에 설명 된 메시지입니다. 메시지 MCMV_YEAR 반환 하는 경우이 메서드는 TRUE를 반환 합니다.

##  <a name="setcalendarborder"></a>  CMonthCalCtrl::SetCalendarBorder

현재 달력 컨트롤의 테두리의 너비를 설정합니다.

```
void SetCalendarBorder(int cxyBorder);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*cxyBorder*|[in] 픽셀에서 테두리의 너비입니다.|

### <a name="remarks"></a>설명

이 메서드가 성공 하면 테두리 너비를로 설정 됩니다는 *cxyBorder* 매개 변수입니다. 테두리 두께입니다. 현재 지정 된 기본 값으로 다시 설정 됩니다이 고, 그렇지 [테마](/windows/desktop/Controls/visual-styles-overview), 또는 테마 사용 되지 않는 경우 0입니다.

이 메서드는 전송 된 [MCM_SETCALENDARBORDER](/windows/desktop/Controls/mcm-setcalendarborder) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_monthCalCtrl`되는 달력 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

달력의 테두리 너비를 8 픽셀 제어는 다음 코드 예제에서는 설정입니다. 사용 된 [CMonthCalCtrl::GetCalendarBorder](#getcalendarborder) 이 메서드가 성공 했는지 여부를 결정 하는 방법입니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]

##  <a name="setcalendarborderdefault"></a>  CMonthCalCtrl::SetCalendarBorderDefault

현재 달력 컨트롤의 테두리의 기본 너비를 설정합니다.

```
void SetCalendarBorderDefault();
```

### <a name="remarks"></a>설명

테두리 너비를 현재 지정 된 기본값으로 설정 되어 [테마](/windows/desktop/Controls/visual-styles-overview), 또는 테마 사용 되지 않는 경우 0입니다.

이 메서드는 전송 된 [MCM_SETCALENDARBORDER](/windows/desktop/Controls/mcm-setcalendarborder) Windows SDK에 설명 된 메시지입니다.

##  <a name="setcalid"></a>  CMonthCalCtrl::SetCalID

현재 달력 컨트롤에 대 한 일정 식별자를 설정합니다.

```
BOOL SetCalID(CALID calid);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*calid*|[in] 중 하나는 [달력 식별자](/windows/desktop/Intl/calendar-identifiers) 상수입니다.|

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

일정 식별자 지정 지역별 달력, 회교식 양력 (지역화) 또는 일본어와 같은 달력입니다. 사용 하 여는 `SetCalID` 으로 지정 된 일정을 표시 하는 메서드를 *calid* 달력을 포함 하는 로캘이 컴퓨터에 설치 된 경우 매개 변수.

이 메서드는 전송 된 [MCM_SETCALID](/windows/desktop/Controls/mcm-setcalid) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_monthCalCtrl`되는 달력 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 일본 천황 력 달력에 표시할 month calendar 컨트롤을 설정 합니다. `SetCalID` 메서드는 일정에는 컴퓨터에 설치 하는 경우에 성공 합니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]

##  <a name="setcenturyview"></a>  CMonthCalCtrl::SetCenturyView

세기 보기를 표시 하려면 현재 달력 컨트롤을 설정 합니다.

```
BOOL SetCenturyView();
```

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 사용 합니다 [CMonthCalCtrl::SetCurrentView](#setcurrentview) 보기 설정 하는 방법 `MCMV_CENTURY`, 세기 뷰를 나타내는입니다.

##  <a name="setcolor"></a>  CMonthCalCtrl::SetColor

Monthcalendar 컨트롤의 지정 된 영역의 색을 설정합니다.

```
COLORREF SetColor(
    int nRegion,
    COLORREF ref);
```

### <a name="parameters"></a>매개 변수

*nRegion*<br/>
설정 하는 월 달력 색을 지정 하는 정수 값입니다. 이 값 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|MCSC_BACKGROUND|월 사이 표시 되는 배경색입니다.|
|MCSC_MONTHBK|월 내에 표시 되는 배경색입니다.|
|MCSC_TEXT|한 달이 내의 텍스트를 표시 하는 데 사용 된 색입니다.|
|MCSC_TITLEBK|표시 된 달력의 제목 배경색입니다.|
|MCSC_TITLETEXT|달력 제목의 내의 텍스트를 표시 하는 데 색입니다.|
|MCSC_TRAILINGTEXT|헤더 및 후행 일 텍스트를 표시 하는 데 사용 된 색입니다. 헤더 후행 날짜와 현재 달력에 표시 되는 이전 및 다음 달의 날짜입니다.|

*ref*<br/>
Month calendar 컨트롤의 지정된 된 부분에 대 한 새 색 설정에 대 한 COLORREF 값입니다.

### <a name="return-value"></a>반환 값

COLORREF 값을 나타내는 month calendar 컨트롤의 지정된 된 부분에 대 한 이전 색 설정을 성공 하는 경우입니다. 그렇지 않은 경우이 메시지는-1을 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETCOLOR](/windows/desktop/Controls/mcm-setcolor)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]

##  <a name="setcurrentview"></a>  CMonthCalCtrl::SetCurrentView

지정된 된 뷰를 표시 하려면 현재 달력 컨트롤을 설정 합니다.

```
BOOL SetCurrentView(DWORD dwNewView);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*dwNewView*|[in] 월간, 연간, 10 년 동안 또는 세기 뷰를 지정 하는 다음 값 중 하나입니다.<br /><br /> MCMV_MONTH: 월별 보기<br /><br /> MCMV_YEAR: 연간 보기<br /><br /> MCMV_DECADE: 10 년 동안 보기<br /><br /> MCMV_CENTURY: 세기 보기|

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [MCM_SETCURRENTVIEW](/windows/desktop/Controls/mcm-setcurrentview) Windows SDK에 설명 된 메시지입니다.

##  <a name="setcursel"></a>  CMonthCalCtrl::SetCurSel

Monthcalendar 컨트롤에 대 한 현재 선택한 날짜를 설정합니다.

```
BOOL SetCurSel(const COleDateTime& refDateTime);
BOOL SetCurSel(const CTime& refDateTime);
  BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>매개 변수

*refDateTime*<br/>
에 대 한 참조를 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 하거나 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 현재 선택 된 month calendar 컨트롤을 나타내는 개체입니다.

*pDateTime*<br/>
에 대 한 포인터를 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 현재 선택 항목으로 설정할 날짜를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETCURSEL](/windows/desktop/Controls/mcm-setcursel)Windows SDK에 설명 된 대로 합니다. MFC의 구현에서 `SetCurSel`를 지정할 수 있습니다를 `COleDateTime` 사용을 `CTime` 사용 또는 `SYSTEMTIME` 구조체 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]

##  <a name="setdaystate"></a>  CMonthCalCtrl::SetDayState

Monthcalendar 컨트롤의 일에 대 한 표시를 설정합니다.

```
BOOL SetDayState(
    int nMonths,
    LPMONTHDAYSTATE pStates);
```

### <a name="parameters"></a>매개 변수

*nMonths*<br/>
배열의 요소 수를 나타내는 값을 *pStates* 가리킵니다.

*pStates*<br/>
에 대 한 포인터를 [MONTHDAYSTATE](/windows/desktop/Controls/monthdaystate) month calendar 컨트롤에서 표시에서 매일은 그리는 방법을 정의 하는 값의 배열입니다. MONTHDAYSTATE 데이터 형식은 비트 필드, 여기서 각 비트 (1 ~ 31) 하루에 한 달의 상태를 나타냅니다. 해당 날짜를 표시할 잠시에 있으면 굵게; 그렇지 않은 경우 없음 강조를 사용 하 여 표시 됩니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETDAYSTATE](/windows/desktop/Controls/mcm-setdaystate)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]

##  <a name="setdecadeview"></a>  CMonthCalCtrl::SetDecadeView

현재 달력 제어 10 년 동안 보기를 설정 합니다.

```
BOOL SetDecadeView();
```

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 사용 합니다 [CMonthCalCtrl::SetCurrentView](#setcurrentview) 보기 설정 하는 방법 `MCMV_DECADE`, 10 년 동안 보기를 나타내는입니다.

##  <a name="setfirstdayofweek"></a>  CMonthCalCtrl::SetFirstDayOfWeek

달력의 맨 왼쪽 열에 표시할 요일을 설정 합니다.

```
BOOL SetFirstDayOfWeek(
    int iDay,
    int* lpnOld = NULL);
```

### <a name="parameters"></a>매개 변수

*iDay*<br/>
주의 첫째 요일로 설정할 날짜를 나타내는 정수 값입니다. 두이 일 숫자 중 하나 여야 합니다. 참조 [GetFirstDayOfWeek](#getfirstdayofweek) 일 숫자에 대 한 합니다.

*lpnOld*<br/>
이전에 주 첫 번째 요일을 나타내는 정수에 대 한 포인터를 설정 합니다.

### <a name="return-value"></a>반환 값

컨트롤 패널 설정에 지정 된 일입니다는 주의 첫 번째 전날 LOCALE_IFIRSTDAYOFWEEK의 이외의 값으로 설정 된 경우에 0이 아닌 경우. 그렇지 않은 경우이 함수는 0을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETFIRSTDAYOFWEEK](/windows/desktop/Controls/mcm-setfirstdayofweek)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]

##  <a name="setmaxselcount"></a>  CMonthCalCtrl::SetMaxSelCount

Monthcalendar 컨트롤에서 선택할 수 있는 일의 최대 수를 설정 합니다.

```
BOOL SetMaxSelCount(int nMax);
```

### <a name="parameters"></a>매개 변수

*nMax*<br/>
최대 개수를 선택할 수 있는 일에 설정 될 값입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETMAXSELCOUNT](/windows/desktop/Controls/mcm-setmaxselcount)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]

##  <a name="setmonthdelta"></a>  CMonthCalCtrl::SetMonthDelta

Monthcalendar 컨트롤에 대 한 스크롤 비율을 설정합니다.

```
int SetMonthDelta(int iDelta);
```

### <a name="parameters"></a>매개 변수

*iDelta*<br/>
컨트롤의 스크롤 비율을 설정할 개월 수입니다. 이 값이 0 이면 월 델타 컨트롤에 표시 된 개월 수를 기본값으로 다시 설정 됩니다.

### <a name="return-value"></a>반환 값

이전 스크롤 비율입니다. 스크롤 비율 이전에 설정 되지 않은 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETMONTHDELTA](/windows/desktop/Controls/mcm-setmonthdelta)Windows SDK에 설명 된 대로 합니다.

##  <a name="setmonthview"></a>  CMonthCalCtrl::SetMonthView

월 보기를 표시 하려면 현재 달력 컨트롤을 설정 합니다.

```
BOOL SetMonthView();
```

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 합니다 [CMonthCalCtrl::SetCurrentView](#setcurrentview) 월 보기를 나타내는 MCMV_MONTH로 뷰를 설정 하는 방법입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_monthCalCtrl`되는 달력 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 월, 년, 10 년 간 및 세기 뷰를 표시 하려면 month calendar 컨트롤을 설정 합니다.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]

##  <a name="setrange"></a>  CMonthCalCtrl::SetRange

Monthcalendar 컨트롤에 대 한 최소 및 최대 허용 되는 날짜를 설정합니다.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);

BOOL SetRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>매개 변수

*pMinRange*<br/>
에 대 한 포인터를 `COleDateTime` 개체를 `CTime` 개체 또는 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 범위의 가장 낮은 끝 날짜를 포함 하는 구조입니다.

*pMaxRange*<br/>
에 대 한 포인터를 `COleDateTime` 개체를 `CTime` 개체 또는 `SYSTEMTIME` 범위의 가장 높은 끝 날짜를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETRANGE](/windows/desktop/Controls/mcm-setrange)Windows SDK에 설명 된 대로 합니다. MFC의 구현에서 `SetRange`를 지정할 수 있습니다 `COleDateTime` 사용을 `CTime` 사용 또는 `SYSTEMTIME` 구조체 사용 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMonthCalCtrl::GetRange](#getrange)합니다.

##  <a name="setselrange"></a>  CMonthCalCtrl::SetSelRange

집합 monthcalendar에 대 한 선택이 지정된 된 날짜 범위를 제어 합니다.

```
BOOL SetSelRange(
    const COleDateTime& pMinRange,
    const COleDateTime& pMaxRange);

BOOL SetSelRange(
    const CTime& pMinRange,
    const CTime& pMaxRange);

BOOL SetSelRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>매개 변수

*pMinRange*<br/>
에 대 한 포인터를 `COleDateTime` 개체를 `CTime` 개체 또는 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 범위의 가장 낮은 끝 날짜를 포함 하는 구조입니다.

*pMaxRange*<br/>
에 대 한 포인터를 `COleDateTime` 개체를 `CTime` 개체 또는 `SYSTEMTIME` 범위의 가장 높은 끝 날짜를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETSELRANGE](/windows/desktop/Controls/mcm-setselrange)Windows SDK에 설명 된 대로 합니다. MFC의 구현에서 `SetSelRange`를 지정할 수 있습니다 `COleDateTime` 사용을 `CTime` 사용 또는 `SYSTEMTIME` 구조체 사용 합니다.

##  <a name="settoday"></a>  CMonthCalCtrl::SetToday

현재 날짜에 대 한 달력 컨트롤을 설정합니다.

```
void SetToday(const COleDateTime& refDateTime);
void SetToday(const CTime* pDateTime);
  void SetToday(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>매개 변수

*refDateTime*<br/>
에 대 한 참조를 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 현재 날짜를 포함 하는 개체입니다.

*pDateTime*<br/>
두 번째 버전에서는에 대 한 포인터를 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 현재 날짜 정보를 포함 하는 개체입니다. 세 번째 버전에서는에 대 한 포인터를 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 현재 날짜 정보를 포함 하는 구조입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [MCM_SETTODAY](/windows/desktop/Controls/mcm-settoday)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CMonthCalCtrl::GetToday](#gettoday)합니다.

##  <a name="setyearview"></a>  CMonthCalCtrl::SetYearView

현재 달력 제어 연도 보기를 설정 합니다.

```
BOOL SetYearView();
```

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 합니다 [CMonthCalCtrl::SetCurrentView](#setcurrentview) 연간 뷰를 나타내는 MCMV_YEAR로 뷰를 설정 하는 방법입니다.

##  <a name="sizeminreq"></a>  CMonthCalCtrl::SizeMinReq

표시 월 달력 컨트롤의 최소 크기는 1 개월을 표시 합니다.

```
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```

### <a name="parameters"></a>매개 변수

*bRepaint*<br/>
컨트롤 다시 그려져 야 하는지 여부를 지정 합니다. 기본적으로 TRUE입니다. FALSE 이면 발생 다시 표시 되지 않습니다.

### <a name="return-value"></a>반환 값

Month calendar 컨트롤을 최소값; 크기가 0이 아닌 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출 `SizeMinReq` 성공적으로 한 달의 일정에 대 한 전체 month calendar 컨트롤을 표시 합니다.

##  <a name="sizerecttomin"></a>  CMonthCalCtrl::SizeRectToMin

현재 month calendar 컨트롤에 대해 지정 된 사각형 크기에 맞는 모든 달력을 포함할 수 있는 가장 작은 사각형을 계산 합니다.

```
LPRECT SizeRectToMin(LPRECT lpRect);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*lpRect*|[in] 에 대 한 포인터를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 원하는 일정 수를 포함 하는 사각형을 정의 하는 구조입니다.|

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 보다 작거나 사각형에 크기가 사각형을 정의 하는 구조를 정의한 합니다 *lpRect* 매개 변수입니다.

### <a name="remarks"></a>설명

이 메서드는 얼마나 많은 달력으로 지정 된 사각형에 맞출 수 있는 계산 된 *lpRect* 매개 변수를 일정 수를 포함할 수 있는 가장 작은 사각형을 반환 합니다. 실제로이 메서드는 원하는 수의 일정에 정확히 맞게 지정된 된 사각형을 축소 합니다.

이 메서드는 전송 된 [MCM_SIZERECTTOMIN](/windows/desktop/Controls/mcm-sizerecttomin) Windows SDK에 설명 된 메시지입니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDateTimeCtrl 클래스](../../mfc/reference/cdatetimectrl-class.md)
