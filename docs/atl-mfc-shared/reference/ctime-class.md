---
title: CTime 클래스
ms.date: 10/18/2018
f1_keywords:
- CTime
- ATLTIME/ATL::CTime
- ATLTIME/ATL::CTime::CTime
- ATLTIME/ATL::CTime::Format
- ATLTIME/ATL::CTime::FormatGmt
- ATLTIME/ATL::CTime::GetAsDBTIMESTAMP
- ATLTIME/ATL::CTime::GetAsSystemTime
- ATLTIME/ATL::CTime::GetCurrentTime
- ATLTIME/ATL::CTime::GetDay
- ATLTIME/ATL::CTime::GetDayOfWeek
- ATLTIME/ATL::CTime::GetGmtTm
- ATLTIME/ATL::CTime::GetHour
- ATLTIME/ATL::CTime::GetLocalTm
- ATLTIME/ATL::CTime::GetMinute
- ATLTIME/ATL::CTime::GetMonth
- ATLTIME/ATL::CTime::GetSecond
- ATLTIME/ATL::CTime::GetTime
- ATLTIME/ATL::CTime::GetYear
- ATLTIME/ATL::CTime::Serialize64
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
ms.openlocfilehash: df86d35e52ea386d2750a4af7357e66a8d08f79f
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744702"
---
# <a name="ctime-class"></a>CTime 클래스

절대 시간 및 날짜를 나타냅니다.

## <a name="syntax"></a>구문

```
class CTime
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CTime::CTime](#ctime)|생성 `CTime` 다양 한 방법으로 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CTime::Format](#format)|변환는 `CTime` 서식이 지정 된 문자열 개체로-현지 표준 시간대에 따라 합니다.|
|[CTime::FormatGmt](#formatgmt)|변환는 `CTime` 서식이 지정 된 문자열 개체로-UTC를 기반으로 합니다.|
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|저장 된 시간 정보를 변환 합니다 `CTime` Win32 호환 DBTIMESTAMP 구조에는 개체입니다.|
|[CTime::GetAsSystemTime](#getassystemtime)|저장 된 시간 정보를 변환 합니다 `CTime` Win32 호환 개체 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 구조입니다.|
|[CTime::GetCurrentTime](#getcurrenttime)|만듭니다는 `CTime` 현재 (정적 멤버 함수)를 나타내는 개체입니다.|
|[CTime::GetDay](#getday)|일 나타내는 반환 합니다 `CTime` 개체입니다.|
|[CTime::GetDayOfWeek](#getdayofweek)|나타내는 요일 반환을 `CTime` 개체입니다.|
|[CTime::GetGmtTm](#getgmttm)|세분화는 `CTime` 개체로 구성 요소-UTC를 기반으로 합니다.|
|[CTime::GetHour](#gethour)|가 나타내는 시간을 반환 합니다 `CTime` 개체입니다.|
|[CTime::GetLocalTm](#getlocaltm)|세분화는 `CTime` 개체로 구성 요소-현지 표준 시간대에 따라 합니다.|
|[CTime::GetMinute](#getminute)|가 나타내는 분을 반환 합니다 `CTime` 개체입니다.|
|[CTime::GetMonth](#getmonth)|가 나타내는 월을 반환 합니다 `CTime` 개체입니다.|
|[CTime::GetSecond](#getsecond)|두 번째 표시를 반환 합니다 `CTime` 개체입니다.|
|[CTime::GetTime](#gettime)|반환을 **__time64_t** 에 대 한 값을 지정 `CTime` 개체입니다.|
|[CTime::GetYear](#getyear)|가 나타내는 연도 반환 합니다 `CTime` 개체입니다.|
|[CTime::Serialize64](#serialize64)|보관 파일에서 데이터를 serialize합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator + -](#operator_add_-)|이러한 연산자는 더하기 및 빼기 `CTimeSpan` 고 `CTime` 개체입니다.|
|[operator +=, -=](#operator_add_eq_-_eq)|이러한 연산자는 더하기 및 빼기는 `CTimeSpan` 개체를이 `CTime` 개체입니다.|
|[operator =](#operator_eq)|대입 연산자입니다.|
|[operator ==, < , etc.](#ctime_comparison_operators)|비교 연산자입니다.|

## <a name="remarks"></a>설명

`CTime` 기본 클래스는 없습니다.

`CTime` 값은 협정 세계시 (그리니치 표준시, GMT) 값은 UTC (coordinated universal time)를 기반으로 합니다. 참조 [시간 관리](../../c-runtime-library/time-management.md) 표준 시간대를 확인 하는 방법에 대 한 정보에 대 한 합니다.

만들 때를 `CTime` 개체, 설정 된 `nDST` 는 표준시 사실 인지 나타내기 위해 0 보다 큰 값으로는 일광 절약 시간 적용을 나타내기 위해 0 또는 C 런타임 라이브러리 코드 계산 해야 하는 0 보다 작은 값으로 매개 변수 e 표준 시간이 나 일광 절약 시간 인지 적용 합니다. `tm_isdst`는 필수 필드입니다. 설정 되지 않은 값 정의 되지 않습니다 및 반환 값 [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) 는 예측할 수 없습니다. 하는 경우 `timeptr` 에 대 한 이전 호출에서 반환 된 tm 구조체를 가리키는 [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)를 [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), 또는 [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), `tm_isdst` 필드에는 올바른 값입니다.

도우미 클래스인 [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), 시간 간격을 나타냅니다.

합니다 `CTime` 고 `CTimeSpan` 파생 클래스 설계 되지 않았습니다. 크기 가상 함수가 없는 되므로 `CTime` 및 `CTimeSpan` 개체는 8 바이트 정확 하 게 합니다. 대부분의 멤버 함수는 인라인입니다.

> [!NOTE]
>  위 날짜 제한은 12/31/3000입니다. 하한값은 1970 년 1/1/12시: 00 AM GMT입니다.

사용에 대 한 자세한 내용은 `CTime`, 문서를 참조 하세요 [날짜 및 시간](../../atl-mfc-shared/date-and-time.md), 및 [시간 관리](../../c-runtime-library/time-management.md) 런타임 라이브러리 참조에서 합니다.

> [!NOTE]
>  `CTime` 구조가 MFC 7.1에서 MFC 8.0으로 변경 합니다. Serialize 하는 경우는 `CTime` 구조를 사용 하 여 합니다 **연산자 <<** MFC 8.0 또는 이후 버전에서 결과 파일을 읽을 수 없습니다 MFC의 이전 버전입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atltime.h

##  <a name="ctime_comparison_operators"></a>  CTime 비교 연산자

비교 연산자입니다.

```
bool operator==(CTime time) const throw();
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw();
```

### <a name="parameters"></a>매개 변수

*time*<br/>
비교할 `CTime` 개체입니다.

### <a name="return-value"></a>반환 값

조건이 true 이면 두 절대 시간 및 TRUE가 반환 이러한 연산자 비교 그렇지 않으면 FALSE입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

##  <a name="ctime"></a>  CTime::CTime

새 `CTime` 지정된 된 시간을 사용 하 여 초기화 하는 개체입니다.

```
CTime() throw();
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts, int nDST = -1) throw();
```

### <a name="parameters"></a>매개 변수

*timeSrc*<br/>
나타냅니다는 `CTime` 이미 존재 하는 개체입니다.

*time*<br/>
`__time64_t` 시간 값은 1970 년 1 월 1 일 UTC 이후의 초 수입니다. 현지 시간으로 조정 됩니다이 note 합니다. 예를 들어, 뉴욕에 만들려는 경우는 `CTime` 자릿수가 0 인 매개 변수를 전달 하 여 개체 [CTime::GetMonth](#getmonth) 12를 반환 합니다.

*nYear*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
복사할 새 날짜 및 시간 값을 나타내는 `CTime` 개체입니다.

*nDST*<br/>
일광 절약 시간이 적용 되는지 나타냅니다. 세 가지 값 중 하나일 수 있습니다.

- *nDST* 0Standard 시간으로 적용 됩니다.

- *nDST* 절약 시간이 적용 되는 0Daylight 보다 큰 값으로 설정 합니다.

- *nDST* 0The 기본값 보다 작은 값으로 설정 합니다. 자동으로 표준 시간이 나 일광 절약 시간이 적용 되는지 계산 합니다.

*wDosDate*, *wDosTime*<br/>
MS-DOS 날짜 및 시간 값을 날짜/시간 값으로 변환 되어 새 복사 `CTime` 개체입니다.

*st*<br/>
A [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 하는 날짜/시간 값으로 변환 하 고 새 복사 구조 `CTime` 개체입니다.

*ft*<br/>
A [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) 하는 날짜/시간 값으로 변환 하 고 새 복사 구조 `CTime` 개체입니다.

*dbts*<br/>
현재 현지 시간을 포함 하는 DBTIMESTAMP 구조체에 대 한 참조입니다.

### <a name="remarks"></a>설명

각 생성자에 대 한 설명은 다음과 같습니다.

- `CTime();` 초기화 되지 않은 생성 `CTime` 개체입니다. 이 생성자를 정의할 수 있습니다 `CTime` 배열 개체입니다. 사용 하기 전에 유효한 시간을 사용 하 여 이러한 배열을 초기화 해야 합니다.

- `CTime( const CTime& );` 생성 된 `CTime` 개체에서 다른 `CTime` 값입니다.

- `CTime( __time64_t );` 생성 된 `CTime` 에서 개체를 **__time64_t** 형식. 이 생성자는 UTC 시간을 예상 하 고 결과 저장 하기 전에 결과 현지 시간으로 변환.

- `CTime( int, int, ...);` 생성 된 `CTime` 각 구성 요소와 현지 시간 구성 요소에서 개체를 다음 범위로 제한 합니다.

   |구성 요소|범위|
   |---------------|-----------|
   |*nYear*|1970-3000|
   |*nMonth*|1-12|
   |*nDay*|1-31|
   |*nHour*|0-23|
   |*nMin*|0-59|
   |*nSec*|0-59|

   이 생성자가 적절 한 UTC로 변환 합니다. Microsoft Foundation Class 라이브러리의 디버그 버전 경우 어설션 또는 범위를 벗어났습니다. 시간 구성 요소입니다. 인수를 호출 하기 전에 확인 해야 합니다. 이 생성자는 현지 시간을 필요합니다.

- `CTime( WORD, WORD );` 생성 된 `CTime` 개체는 지정 된 MS-DOS 날짜 및 시간 값에서입니다. 이 생성자는 현지 시간을 필요합니다.

- `CTime( const SYSTEMTIME& );` 생성 된 `CTime` 에서 개체를 `SYSTEMTIME` 구조입니다. 이 생성자는 현지 시간을 필요합니다.

- `CTime( const FILETIME& );` 생성 된 `CTime` 에서 개체를 `FILETIME` 구조입니다. 대부분의 경우 사용 하지 것입니다 `CTime FILETIME` 직접 초기화 합니다. 사용 하는 경우는 `CFile` 파일을 조작 하는 개체 `CFile::GetStatus` 을 통해 파일 타임 스탬프를 검색 합니다.는 `CTime` 사용 하 여 개체 초기화는 `FILETIME` 구조입니다. 이 생성자는 UTC 기준으로 하는 시간으로 간주 하 고 자동으로 결과 저장 하기 전에 현지 시간으로 값을 변환 합니다.

   > [!NOTE]
   > 생성자를 통해 `DBTIMESTAMP` OLEDB.h 포함 되는 경우 매개 변수는만 사용할 수 있습니다.

자세한 내용은 참조는 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 및 [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) Windows SDK에는 구조입니다. 참조를 [MS-DOS 날짜 및 시간](/windows/desktop/SysInfo/ms-dos-date-and-time) Windows SDK에는 항목입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

##  <a name="format"></a>  CTime::Format

날짜-시간 값의 서식이 지정 된 표현을 만들려면이 멤버 함수를 호출 합니다.

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>매개 변수

*pszFormat*<br/>
유사한 문자열 서식의 `printf` 문자열 서식을 지정 합니다. 서식 코드 앞에 백분율 (`%`)에 서명, 해당 바뀝니다 `CTime` 구성 요소입니다. 반환된 된 문자열에 형식 문자열에 다른 문자 변경 되지 않고 복사 됩니다. 런타임 함수를 참조 하세요 [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) 서식 코드의 목록은 합니다.

*nFormatID*<br/>
이 형식을 식별 하는 문자열의 ID입니다.

### <a name="return-value"></a>반환 값

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 서식이 지정 된 시간을 포함 하는 합니다.

### <a name="remarks"></a>설명

하는 경우이 상태의 `CTime` 개체가 null 이면 반환 값은 빈 문자열입니다.

이 메서드는 날짜-시간 값 형식을 지정 하려면 범위를 벗어난 3000 년 12 월 31 일을 통해 1970 년 1 월 1 일 자정에서 경우 예외를 throw 협정 세계시 (UTC)입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

##  <a name="formatgmt"></a>  CTime::FormatGmt

이에 해당 하는 서식이 지정 된 문자열을 생성 `CTime` 개체입니다.

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>매개 변수

*pszFormat*<br/>
유사한 서식 문자열을 지정 합니다 `printf` 문자열 서식을 지정 합니다. 런타임 함수를 참조 하세요 [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) 세부 정보에 대 한 합니다.

*nFormatID*<br/>
이 형식을 식별 하는 문자열의 ID입니다.

### <a name="return-value"></a>반환 값

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 서식이 지정 된 시간을 포함 하는 합니다.

### <a name="remarks"></a>설명

시간 값은 변환 되지 않습니다 및 따라서 UTC를 반영 합니다.

이 메서드는 날짜-시간 값 형식을 지정 하려면 범위를 벗어난 3000 년 12 월 31 일을 통해 1970 년 1 월 1 일 자정에서 경우 예외를 throw 협정 세계시 (UTC)입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CTime::Format](#format)합니다.

##  <a name="getasdbtimestamp"></a>  CTime::GetAsDBTIMESTAMP

저장 된 시간 정보를 변환 하려면이 멤버 함수를 호출 합니다 `CTime` Win32 호환 DBTIMESTAMP 구조에는 개체입니다.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>매개 변수

*dbts*<br/>
현재 현지 시간을 포함 하는 DBTIMESTAMP 구조체에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

참조 된 결과 시간을 저장 *dbts* 구조입니다. 합니다 `DBTIMESTAMP` 이 함수에 의해 초기화 되는 데이터 구조를 갖습니다. 해당 `fraction` 멤버가 0으로 설정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

##  <a name="getassystemtime"></a>  CTime::GetAsSystemTime

저장 된 시간 정보를 변환 하려면이 멤버 함수를 호출 합니다 `CTime` Win32 호환 개체 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 구조입니다.

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>매개 변수

*timeDest*<br/>
에 대 한 참조를 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 의 변환 된 날짜/시간 값을 포함 하는 구조는 `CTime` 개체입니다.

### <a name="return-value"></a>반환 값

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

`GetAsSystemTime` 참조 된 결과 시간을 저장 *timeDest* 구조입니다. 합니다 `SYSTEMTIME` 이 함수에 의해 초기화 되는 데이터 구조를 갖습니다. 해당 `wMilliseconds` 멤버가 0으로 설정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

##  <a name="getcurrenttime"></a>  CTime::GetCurrentTime

반환 된 `CTime` 현재 시간을 나타내는 개체입니다.

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>설명

현재 시스템 날짜 및 시간을 utc (협정 세계시)로 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

##  <a name="getday"></a>  CTime::GetDay

일 나타내는 반환 합니다 `CTime` 개체입니다.

```
int GetDay() const throw();
```

### <a name="return-value"></a>반환 값

1 ~ 31 범위의 로컬 시간을 기준으로 해당 월의 일을 반환 합니다.

### <a name="remarks"></a>설명

이 함수 호출 `GetLocalTm`, 내부, 정적으로 할당 된 버퍼를 사용 합니다. 이 버퍼의 데이터를 다른 호출으로 인해 덮어씁니다 `CTime` 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

##  <a name="getdayofweek"></a>  CTime::GetDayOfWeek

나타내는 요일 반환을 `CTime` 개체입니다.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>반환 값

로컬 시간에 따라 요일을 반환 합니다. 1 = 일요일, 2 = 월요일, 7 = 토요일.

### <a name="remarks"></a>설명

이 함수 호출 `GetLocalTm`를 사용 하는 내부 정적 버퍼를 할당 합니다. 이 버퍼의 데이터를 다른 호출으로 인해 덮어씁니다 `CTime` 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

##  <a name="getgmttm"></a>  CTime::GetGmtTm

가져옵니다를 **struct tm** 이 포함 된 시간의 분해를 포함 하는 `CTime` 개체입니다.

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>매개 변수

*ptm*<br/>
데이터를 받을 버퍼를 가리킵니다. 이 포인터가 NULL 이면 예외가 throw 됩니다.

### <a name="return-value"></a>반환 값

입력 기능에 대 한 포인터 **struct tm** 시간 포함 파일에 정의 된 대로 합니다. 8. 참조 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) 구조 레이아웃에 대 한 합니다.

### <a name="remarks"></a>설명

`GetGmtTm` UTC를 반환합니다.

*ptm* NULL 일 수 없습니다. 이전 동작으로 되돌리려면 원하면 *ptm* _SECURE_ATL을 해제 한 다음, 정적으로 할당 된 버퍼를 사용할 내부 나타내기 위해 NULL이 될 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

##  <a name="gethour"></a>  CTime::GetHour

가 나타내는 시간을 반환 합니다 `CTime` 개체입니다.

```
int GetHour() const throw();
```

### <a name="return-value"></a>반환 값

0부터 23 까지의 범위에 현지 시간을 기준으로 시간을 반환 합니다.

### <a name="remarks"></a>설명

이 함수 호출 `GetLocalTm`를 사용 하는 내부 정적 버퍼를 할당 합니다. 이 버퍼의 데이터를 다른 호출으로 인해 덮어씁니다 `CTime` 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

##  <a name="getlocaltm"></a>  CTime::GetLocalTm

가져옵니다를 **struct tm** 이 포함 된 시간의 분해 포함 `CTime` 개체입니다.

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>매개 변수

*ptm*<br/>
데이터를 받을 버퍼를 가리킵니다. 이 포인터가 NULL 이면 예외가 throw 됩니다.

### <a name="return-value"></a>반환 값

입력 기능에 대 한 포인터 **struct tm** 시간 포함 파일에 정의 된 대로 합니다. 8. 참조 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) 구조 레이아웃에 대 한 합니다.

### <a name="remarks"></a>설명

`GetLocalTm` 현지 시간을 반환합니다.

*ptm* NULL 일 수 없습니다. 이전 동작으로 되돌리려면 원하면 *ptm* _SECURE_ATL을 해제 한 다음, 정적으로 할당 된 버퍼를 사용할 내부 나타내기 위해 NULL이 될 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

##  <a name="getminute"></a>  CTime::GetMinute

가 나타내는 분을 반환 합니다 `CTime` 개체입니다.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>반환 값

0부터 59 까지의 범위에 현지 시간을 기준으로 분을 반환 합니다.

### <a name="remarks"></a>설명

이 함수 호출 `GetLocalTm`를 사용 하는 내부 정적 버퍼를 할당 합니다. 이 버퍼의 데이터를 다른 호출으로 인해 덮어씁니다 `CTime` 멤버 함수입니다.

### <a name="example"></a>예제

예를 참조 하세요 [GetHour](#gethour)합니다.

##  <a name="getmonth"></a>  CTime::GetMonth

가 나타내는 월을 반환 합니다 `CTime` 개체입니다.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>반환 값

범위는 1 ~ 12의 로컬 시간을 기준으로 월 단위 (1 년 1 월 =) 합니다.

### <a name="remarks"></a>설명

이 함수 호출 `GetLocalTm`를 사용 하는 내부 정적 버퍼를 할당 합니다. 이 버퍼의 데이터를 다른 호출으로 인해 덮어씁니다 `CTime` 멤버 함수입니다.

### <a name="example"></a>예제

예를 참조 하세요 [GetDay](#getday)합니다.

##  <a name="getsecond"></a>  CTime::GetSecond

두 번째 표시를 반환 합니다 `CTime` 개체입니다.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>반환 값

두 번째 반환 범위의 0부터 59까지 로컬 시간을 기준으로 합니다.

### <a name="remarks"></a>설명

이 함수 호출 `GetLocalTm`를 사용 하는 내부 정적 버퍼를 할당 합니다. 이 버퍼의 데이터를 다른 호출으로 인해 덮어씁니다 `CTime` 멤버 함수입니다.

### <a name="example"></a>예제

예를 참조 하세요 [GetHour](#gethour)합니다.

##  <a name="gettime"></a>  CTime::GetTime

반환을 **__time64_t** 에 대 한 값을 지정 `CTime` 개체입니다.

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>반환 값

`GetTime` 현재 까지의 시간 (초) 수를 반환 `CTime` 개체와 1970 년 1 월 1 일입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

##  <a name="getyear"></a>  CTime::GetYear

가 나타내는 연도 반환 합니다 `CTime` 개체입니다.

```
int GetYear();
```

### <a name="return-value"></a>반환 값

연도, 월 범위에서의 로컬 시간을 기준으로 반환 2038 년 1 월 18 일 (포함)에 1,1970입니다.

### <a name="remarks"></a>설명

이 함수 호출 `GetLocalTm`를 사용 하는 내부 정적 버퍼를 할당 합니다. 이 버퍼의 데이터를 다른 호출으로 인해 덮어씁니다 `CTime` 멤버 함수입니다.

### <a name="example"></a>예제

예를 참조 하세요 [GetDay](#getday)합니다.

##  <a name="operator_eq"></a>  CTime::operator =

대입 연산자입니다.

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>매개 변수

*time*<br/>
새 날짜/시간 값입니다.

### <a name="return-value"></a>반환 값

업데이트 된 `CTime` 개체입니다.

### <a name="remarks"></a>설명

이 오버 로드 된 할당 연산자 복사 원본에 `CTime` 개체입니다. 내부 시간 저장소에는 `CTime` 개체가 표준 시간대와 무관 합니다. 표준 시간대 변환 할당 하는 동안 필요 하지 않습니다.

##  <a name="operator_add_-"></a>  CTime::operator +, -

이러한 연산자는 더하기 및 빼기 `CTimeSpan` 고 `CTime` 개체입니다.

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>매개 변수

*timeSpan*<br/>
`CTimeSpan` 개체를 추가 하거나 뺄 수 있습니다.

*time*<br/>
`CTime` 뺄 개체입니다.

### <a name="return-value"></a>반환 값

A `CTime` 또는 `CTimeSpan` 작업의 결과 나타내는 개체입니다.

### <a name="remarks"></a>설명

`CTime` 개체가 나타내는 절대 시간 `CTimeSpan` 개체 상대 시간을 나타냅니다. 처음 두 연산자 수 더하기 및 빼기 `CTimeSpan` 에서 개체 `CTime` 개체입니다. 세 번째 연산자를 사용 하면 하나를 뺄 `CTime` 개체를 생성 하기 위해 서로 `CTimeSpan` 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  CTime::operator +=, -=

이러한 연산자는 더하기 및 빼기는 `CTimeSpan` 개체를이 `CTime` 개체입니다.

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CTimeSpan` 개체를 추가 하거나 뺄 수 있습니다.

### <a name="return-value"></a>반환 값

업데이트 된 `CTime` 개체입니다.

### <a name="remarks"></a>설명

이러한 연산자를 사용 하면 더하기 및 빼기에 `CTimeSpan` 개체를이 `CTime` 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

##  <a name="serialize64"></a>  CTime::Serialize64

> [!NOTE]
> 이 메서드는 MFC 프로젝트에서 사용할 수만 있습니다.

보관에서 멤버 변수를 사용 하 여 연결 된 데이터를 serialize 합니다.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
`CArchive` 업데이트 하려는 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 된 `CArchive` 개체입니다.

## <a name="see-also"></a>참고자료

[asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)<br/>
[_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[CTimeSpan 클래스](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
