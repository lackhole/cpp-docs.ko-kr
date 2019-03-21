---
title: CFileTime 클래스
ms.date: 10/18/2018
f1_keywords:
- CFileTime
- ATLTIME/ATL::CFileTime
- ATLTIME/ATL::CFileTime::CFileTime
- ATLTIME/ATL::CFileTime::GetCurrentTime
- ATLTIME/ATL::CFileTime::GetTime
- ATLTIME/ATL::CFileTime::LocalToUTC
- ATLTIME/ATL::CFileTime::SetTime
- ATLTIME/ATL::CFileTime::UTCToLocal
- ATLTIME/ATL::CFileTime::Day
- ATLTIME/ATL::CFileTime::Hour
- ATLTIME/ATL::CFileTime::Millisecond
- ATLTIME/ATL::CFileTime::Minute
- ATLTIME/ATL::CFileTime::Second
- ATLTIME/ATL::CFileTime::Week
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
ms.openlocfilehash: 07b888b031a38dc2f09404a14e729e26b3eaa019
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746099"
---
# <a name="cfiletime-class"></a>CFileTime 클래스

이 클래스는 파일과 연결 된 날짜 및 시간 값을 관리 하기 위한 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
class CFileTime :  public FILETIME
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CFileTime::CFileTime](#cfiletime)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CFileTime::GetCurrentTime](#getcurrenttime)|검색 하려면이 정적 함수 호출을 `CFileTime` 현재 시스템 날짜 및 시간을 나타내는 개체입니다.|
|[CFileTime::GetTime](#gettime)|시간을 검색 하려면이 메서드를 호출 합니다 `CFileTime` 개체입니다.|
|[CFileTime::LocalToUTC](#localtoutc)|로컬 파일에는 Utc (협정 세계시) 기준 파일 시간으로 변환 하 고이 메서드를 호출 합니다.|
|[CFileTime::SetTime](#settime)|이 메서드를 호출 하 여 저장 된 시간과 날짜를 설정 합니다 `CFileTime` 개체입니다.|
|[CFileTime::UTCToLocal](#utctolocal)|시간에는 Utc (협정 세계시) 로컬 파일 시간을 기반으로 변환 하려면이 메서드를 호출 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CFileTime::operator -](#operator_-)|이 연산자에 대해 빼기를 수행 되는 `CFileTime` 또는 `CFileTimeSpan` 개체입니다.|
|[CFileTime::operator !=](#operator_neq)|이 연산자는 두 비교 `CFileTime` 개체가 다른 지 합니다.|
|[CFileTime::operator +](#operator_add)|이 연산자는 `CFileTimeSpan` 개체에 대해 더하기를 수행하는 데 사용됩니다.|
|[CFileTime::operator +=](#operator_add_eq)|이 연산자는 `CFileTimeSpan` 개체에 대해 더하기를 수행하고 결과를 현재 개체에 할당하는 데 사용됩니다.|
|[CFileTime::operator &lt;](#operator_lt)|이 연산자는 두 `CFileTime` 개체를 비교하여 더 작은 값을 확인합니다.|
|[CFileTime::operator &lt;=](#operator_lt_eq)|이 연산자는 두 `CFileTime` 개체를 비교하여 더 작거나 같은 값을 확인합니다.|
|[CFileTime::operator =](#operator_eq)|대입 연산자입니다.|
|[CFileTime::operator -=](#operator_-_eq)|이 연산자에 대해 빼기를 수행 되는 `CFileTimeSpan` 개체 및 현재 개체에 결과 할당 합니다.|
|[CFileTime::operator ==](#operator_eq_eq)|이 연산자는 두 `CFileTime` 개체가 같은지 비교합니다.|
|[CFileTime::operator &gt;](#operator_gt)|이 연산자는 두 `CFileTime` 개체를 비교하여 더 큰 값을 확인합니다.|
|[CFileTime::operator &gt;=](#operator_gt_eq)|이 연산자는 두 `CFileTime` 개체를 비교하여 더 크거나 같은 값을 확인합니다.|

### <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|[CFileTime::Day](#day)|정적 데이터 멤버가 하루를 구성 하는 100 나노초 간격의 수를 저장 합니다.|
|[CFileTime::Hour](#hour)|정적 데이터 멤버 1 시간을 구성 하는 100 나노초 간격의 수를 저장 합니다.|
|[CFileTime::Millisecond](#millisecond)|정적 데이터 멤버 1 밀리초를 구성 하는 100 나노초 간격의 수를 저장 합니다.|
|[CFileTime::Minute](#minute)|정적 데이터 멤버 1 분을 구성 하는 100 나노초 간격의 수를 저장 합니다.|
|[CFileTime::Second](#second)|정적 데이터 멤버 1 초를 구성 하는 100 나노초 간격의 수를 저장 합니다.|
|[CFileTime::Week](#week)|정적 데이터 멤버 1 주일을 구성 하는 100 나노초 간격의 수를 저장 합니다.|

## <a name="remarks"></a>설명

이 클래스는 연결 생성, 액세스 및 파일을 수정 된 날짜 및 시간 값을 관리 하기 위한 메서드를 제공 합니다. 메서드 및이 클래스의 데이터를 자주 함께에서 `CFileTimeSpan` 된 상대 시간 값을 처리 하는 개체입니다.

날짜 및 시간 값은 1601 년 1 월 1 일 이후 100 나노초 간격의 수를 나타내는 64 비트 값으로 저장 됩니다. Utc (협정 세계시) 형식입니다.

다음 정적 const 멤버 변수는 계산을 단순화 하기 위해 제공 됩니다.

|멤버 변수|100 나노초 간격의 수|
|---------------------|-----------------------------------------|
|Millisecond|10,000|
|Second|밀리초 \* 1,000|
|Minute|두 번째 \* 60|
|Hour|분 \* 60|
|Day|시간 \* 24|
|주|일 \* 7|

**참고** 일부 파일 시스템 만들기를 기록할 수 및 마지막 액세스 시간 및 모든 파일 시스템에 동일한 방식으로 기록 합니다. 예제에서는 Windows NT FAT 파일 시스템 만들기에 대 한 10 밀리초 해상도 포함 하는 시간, 쓰기 시간 2 초의 해상도 가진 및 액세스 시간 1 일 (액세스 날짜)의 해상도 합니다. NTFS 액세스 시간에 1 시간의 확인을 기능이 있습니다. 또한 FAT 현지 시간으로 디스크에 대 한 번이 기록 되지만 NTFS utc에서 시간 디스크에 기록 합니다. 자세한 내용은 [파일을 시간](/windows/desktop/SysInfo/file-times)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`FILETIME`

`CFileTime`

## <a name="requirements"></a>요구 사항

**헤더:** atltime.h

##  <a name="cfiletime"></a>  CFileTime::CFileTime

생성자입니다.

```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>매개 변수

*ft*<br/>
A [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) 구조입니다.

*nTime*<br/>
날짜 및 64 비트 값으로 표현 된 시간입니다.

### <a name="remarks"></a>설명

합니다 `CFileTime` 기존 날짜 및 시간을 사용 하 여 개체를 만들 수는 `FILETIME` 구조체 또는 (로컬 또는 utc (협정 세계시) 시간 형식)에서 64 비트 값으로 표현 합니다. 시간을 0으로 설정 하는 기본 생성자입니다.

##  <a name="day"></a>  CFileTime::Day

정적 데이터 멤버가 하루를 구성 하는 100 나노초 간격의 수를 저장 합니다.

```
static const ULONGLONG Day = Hour* 24;
```

### <a name="example"></a>예제

예를 참조 하세요 [CFileTime::Millisecond](#millisecond)합니다.

##  <a name="getcurrenttime"></a>  CFileTime::GetCurrentTime

검색 하려면이 정적 함수 호출을 `CFileTime` 현재 시스템 날짜 및 시간을 나타내는 개체입니다.

```
static CFileTime GetCurrentTime() throw();
```

### <a name="return-value"></a>반환 값

현재 시스템 날짜 및 시간을 utc (협정 세계시) 형식으로 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]

##  <a name="gettime"></a>  CFileTime::GetTime

시간을 검색 하려면이 메서드를 호출 합니다 `CFileTime` 개체입니다.

```
ULONGLONG GetTime() const throw();
```

### <a name="return-value"></a>반환 값

날짜 및 시간으로 로컬 또는 utc (협정 세계시) 형식에 있을 수 있는 64 비트 숫자를 반환 합니다.

##  <a name="hour"></a>  CFileTime::Hour

정적 데이터 멤버 1 시간을 구성 하는 100 나노초 간격의 수를 저장 합니다.

```
static const ULONGLONG Hour = Minute* 60;
```

### <a name="example"></a>예제

예를 참조 하세요 [CFileTime::Millisecond](#millisecond)합니다.

##  <a name="localtoutc"></a>  CFileTime::LocalToUTC

로컬 파일에는 Utc (협정 세계시) 기준 파일 시간으로 변환 하 고이 메서드를 호출 합니다.

```
CFileTime LocalToUTC() const throw();
```

### <a name="return-value"></a>반환 값

반환 된 `CFileTime` UTC 형식의 시간을 포함 하는 개체입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CFileTime::UTCToLocal](#utctolocal)합니다.

##  <a name="millisecond"></a>  CFileTime::Millisecond

정적 데이터 멤버 1 밀리초를 구성 하는 100 나노초 간격의 수를 저장 합니다.

```
static const ULONGLONG Millisecond = 10000;
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]

##  <a name="minute"></a>  CFileTime::Minute

정적 데이터 멤버 1 분을 구성 하는 100 나노초 간격의 수를 저장 합니다.

```
static const ULONGLONG Minute = Second* 60;
```

### <a name="example"></a>예제

예를 참조 하세요 [CFileTime::Millisecond](#millisecond)합니다.

##  <a name="operator_-"></a>  CFileTime::operator -

이 연산자에 대해 빼기를 수행 되는 `CFileTime` 또는 `CFileTimeSpan` 개체입니다.

```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

*ft*<br/>
`CFileTime` 개체입니다.

### <a name="return-value"></a>반환 값

반환 된 `CFileTime` 개체 또는 `CFileTimeSpan` 두 개체 사이의 시간 차이의 결과 나타내는 개체입니다.

##  <a name="operator_neq"></a>  CFileTime::operator !=

이 연산자는 두 비교 `CFileTime` 개체가 다른 지 합니다.

```
bool operator!=(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*ft*<br/>
비교할 `CFileTime` 개체입니다.

### <a name="return-value"></a>반환 값

비교할 항목 같지 않은 경우 TRUE를 반환 합니다 `CFileTime` 개체, 그렇지 않으면 FALSE입니다.

##  <a name="operator_add"></a>  CFileTime::operator +

이 연산자는 `CFileTimeSpan` 개체에 대해 더하기를 수행하는 데 사용됩니다.

```
CFileTime operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

반환 된 `CFileTime` 원래 시간 상대적 시간을 합한 결과 나타내는 개체입니다.

##  <a name="operator_add_eq"></a>  CFileTime::operator +=

이 연산자는 `CFileTimeSpan` 개체에 대해 더하기를 수행하고 결과를 현재 개체에 할당하는 데 사용됩니다.

```
CFileTime& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 된 반환 `CFileTime` 원래 시간 상대적 시간을 합한 결과 나타내는 개체입니다.

##  <a name="operator_lt"></a>  CFileTime::operator &lt;

이 연산자는 두 `CFileTime` 개체를 비교하여 더 작은 값을 확인합니다.

```
bool operator<(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*ft*<br/>
비교할 `CFileTime` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체 미만인 경우 (이전 시간)의 두 번째 FALSE 그렇지 않은 경우 TRUE를 반환 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]

##  <a name="operator_lt_eq"></a>  CFileTime::operator &lt;=

이 연산자는 두 `CFileTime` 개체를 비교하여 더 작거나 같은 값을 확인합니다.

```
bool operator<=(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*ft*<br/>
비교할 `CFileTime` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체 앞에 있는 시간 보다 작거나 같은 두 번째 경우 TRUE를 반환 합니다. 그렇지 않으면 FALSE입니다.

##  <a name="operator_eq"></a>  CFileTime::operator =

대입 연산자입니다.

```
CFileTime& operator=(const FILETIME& ft) throw();
```

### <a name="parameters"></a>매개 변수

*ft*<br/>
`CFileTime` 새 시간 및 날짜를 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 된 반환 `CFileTime` 개체입니다.

##  <a name="operator_-_eq"></a>  CFileTime::operator -=

이 연산자에 대해 빼기를 수행 되는 `CFileTimeSpan` 개체 및 현재 개체에 결과 할당 합니다.

```
CFileTime& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
`CFileTimeSpan` 뺄 상대 시간을 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 된 반환 `CFileTime` 개체입니다.

##  <a name="operator_eq_eq"></a>  CFileTime::operator ==

이 연산자는 두 `CFileTime` 개체가 같은지 비교합니다.

```
bool operator==(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*ft*<br/>
`CFileTime` 비교할 개체입니다.

### <a name="return-value"></a>반환 값

개체가 같으면이 고, 그렇지 않으면 FALSE 경우 TRUE를 반환 합니다.

##  <a name="operator_gt"></a>  CFileTime::operator &gt;

이 연산자는 두 `CFileTime` 개체를 비교하여 더 큰 값을 확인합니다.

```
bool operator>(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*ft*<br/>
비교할 `CFileTime` 개체입니다.

### <a name="return-value"></a>반환 값

(나중에 시간)에 첫 번째 개체 보다 큰 경우 TRUE를 반환 합니다. 두 번째 보다 그렇지 않으면 FALSE입니다.

##  <a name="operator_gt_eq"></a>  CFileTime::operator &gt;=

이 연산자는 두 `CFileTime` 개체를 비교하여 더 크거나 같은 값을 확인합니다.

```
bool operator>=(CFileTime ft) const throw();
```

### <a name="parameters"></a>매개 변수

*ft*<br/>
비교할 `CFileTime` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 개체가 두 번째 (나중에 시간) 보다 높거나 경우 TRUE를 반환 합니다. 그렇지 않으면 FALSE입니다.

##  <a name="second"></a>  CFileTime::Second

정적 데이터 멤버가 하루를 구성 하는 100 나노초 간격의 수를 저장 합니다.

```
static const ULONGLONG Second = Millisecond* 1000;
```

### <a name="example"></a>예제

예를 참조 하세요 [CFileTime::Millisecond](#millisecond)합니다.

##  <a name="settime"></a>  CFileTime::SetTime

이 메서드를 호출 하 여 저장 된 시간과 날짜를 설정 합니다 `CFileTime` 개체입니다.

```
void SetTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>매개 변수

*nTime*<br/>
날짜 및 시간, 현지 또는 utc (협정 세계시) 형식 중 하나를 나타내는 64 비트 값입니다.

##  <a name="utctolocal"></a>  CFileTime::UTCToLocal

시간에는 Utc (협정 세계시) 로컬 파일 시간을 기반으로 변환 하려면이 메서드를 호출 합니다.

```
CFileTime UTCToLocal() const throw();
```

### <a name="return-value"></a>반환 값

반환 된 `CFileTime` 로컬 파일 시간 형식의 시간을 포함 하는 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]

##  <a name="week"></a>  CFileTime::Week

정적 데이터 멤버 1 주일을 구성 하는 100 나노초 간격의 수를 저장 합니다.

```
static const ULONGLONG Week = Day* 7;
```

### <a name="example"></a>예제

예를 참조 하세요 [CFileTime::Millisecond](#millisecond)합니다.

## <a name="see-also"></a>참고자료

[FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFileTimeSpan 클래스](../../atl-mfc-shared/reference/cfiletimespan-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
