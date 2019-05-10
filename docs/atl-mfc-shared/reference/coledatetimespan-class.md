---
title: COleDateTimeSpan 클래스
ms.date: 03/27/2019
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
ms.openlocfilehash: b68a984488f37326f3b0c1249a5f17a3eb76548b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62198202"
---
# <a name="coledatetimespan-class"></a>COleDateTimeSpan 클래스

상대 시간을 시간 범위를 나타냅니다.

## <a name="syntax"></a>구문

```
class COleDateTimeSpan
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|`COleDateTimeSpan` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleDateTimeSpan::Format](#format)|형식이 지정 된 문자열 표현을 생성 한 `COleDateTimeSpan` 개체입니다.|
|[COleDateTimeSpan::GetDays](#getdays)|두 일 부분을 반환 `COleDateTimeSpan` 나타내는 개체입니다.|
|[COleDateTimeSpan::GetHours](#gethours)|이 범위를 시간 부분을 반환 `COleDateTimeSpan` 나타내는 개체입니다.|
|[COleDateTimeSpan::GetMinutes](#getminutes)|이 분 부분을 반환 합니다 `COleDateTimeSpan` 나타내는 개체입니다.|
|[COleDateTimeSpan::GetSeconds](#getseconds)|이 범위의 두 번째 부분을 반환 합니다 `COleDateTimeSpan` 나타내는 개체입니다.|
|[COleDateTimeSpan::GetStatus](#getstatus)|이 상태 (유효성)를 가져옵니다 `COleDateTimeSpan` 개체입니다.|
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|이 일 수가 반환 `COleDateTimeSpan` 나타내는 개체입니다.|
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|이 시간 수를 반환 합니다 `COleDateTimeSpan` 나타내는 개체입니다.|
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|이 시간 (분) 수를 반환 합니다 `COleDateTimeSpan` 나타내는 개체입니다.|
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|이 시간 (초) 수를 반환 합니다 `COleDateTimeSpan` 나타내는 개체입니다.|
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|이 값을 설정 `COleDateTimeSpan` 개체입니다.|
|[COleDateTimeSpan::SetStatus](#setstatus)|상태를 설정 합니다 (유효성)이 `COleDateTimeSpan` 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|||
|-|-|
|[operator +, -](#operator_add_-)|추가, 빼기, 및에 대 한 로그인을 변경할 `COleDateTimeSpan` 값입니다.|
|[operator +=, -=](#operator_add_eq_-_eq)|더하기 및 빼기는 `COleDateTimeSpan` 값이 `COleDateTimeSpan` 값입니다.|
|[operator =](#operator_eq)|복사본을 `COleDateTimeSpan` 값입니다.|
|[operator ==, <, <=](#coledatetimespan_relational_operators)|두 개를 비교 `COleDateTimeSpan` 값입니다.|
|[operator double](#operator_double)|이 변환 `COleDateTimeSpan` 값을 **double**합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[COleDateTimeSpan::m_span](#m_span)|기본 포함 **이중** 이 `COleDateTimeSpan` 개체입니다.|
|[COleDateTimeSpan::m_status](#m_status)|이 상태를 포함 `COleDateTimeSpan` 개체입니다.|

## <a name="remarks"></a>설명

`COleDateTimeSpan` 기본 클래스는 없습니다.

`COleDateTimeSpan` 일의 시간을 유지 합니다.

`COleDateTimeSpan` 해당 도우미 클래스가 사용 됩니다 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)합니다. `COleDateTime` 캡슐화 된 `DATE` OLE 자동화의 데이터 형식입니다. `COleDateTime` 절대 시간 값을 나타냅니다. 모든 `COleDateTime` 계산 관련 `COleDateTimeSpan` 값입니다. 이러한 클래스 간의 관계 간의 비슷합니다 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 하 고 [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)합니다.

에 대 한 자세한 합니다 `COleDateTime` 하 고 `COleDateTimeSpan` 클래스 문서를 참조 하세요. [날짜 및 시간: 자동화 지원을](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** ATLComTime.h

##  <a name="coledatetimespan_relational_operators"></a>  COleDateTimeSpan 관계형 연산자

비교 연산자입니다.

```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```

### <a name="parameters"></a>매개 변수

*dateSpan*<br/>
비교할 `COleDateTimeSpan`입니다.

### <a name="return-value"></a>반환 값

조건이 true 이면 두 날짜/시간 범위 값 및 TRUE가 반환 이러한 연산자 비교 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  ATLASSERT 피연산자 중 하나가 유효 하지 않은 경우 발생 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]

##  <a name="coledatetimespan"></a>  COleDateTimeSpan::COleDateTimeSpan

`COleDateTimeSpan` 개체를 생성합니다.

```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>매개 변수

*dblSpanSrc*<br/>
복사할 새 일 수가 `COleDateTimeSpan` 개체입니다.

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
복사할 새 날짜 및 시간 값을 나타내며 `COleDateTimeSpan` 개체입니다.

### <a name="remarks"></a>설명

이 생성자의 모든 새로 만들기 `COleDateTimeSpan` 개체를 지정된 된 값으로 초기화 합니다. 이 생성자의 각 간략 한 설명은 다음과 같습니다.

- **COleDateTimeSpan ()** 생성을 `COleDateTimeSpan` 0으로 초기화 하는 개체입니다.

- **COleDateTimeSpan (** `dblSpanSrc` **)** 생성을 `COleDateTimeSpan` 부동 소수점 값 개체입니다.

- **COleDateTimeSpan (** `lDays` **하십시오** `nHours` **하십시오** `nMins` **하십시오** `nSecs` **)**  생성 된 `COleDateTimeSpan` 개체가 지정된 된 숫자 값으로 초기화 합니다.

새 상태 `COleDateTimeSpan` 개체에 잘못 설정 됩니다.

에 대 한 범위에 대 한 자세한 내용은 `COleDateTimeSpan` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원을](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]

##  <a name="format"></a>  COleDateTimeSpan::Format

형식이 지정 된 문자열 표현을 생성 한 `COleDateTimeSpan` 개체입니다.

```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>매개 변수

*pFormat*<br/>
유사한 문자열 서식의 `printf` 문자열 서식을 지정 합니다. 서식 코드 앞에 백분율 (`%`)에 서명, 해당 바뀝니다 `COleDateTimeSpan` 구성 요소입니다. 반환된 된 문자열에 형식 문자열에 다른 문자 변경 되지 않고 복사 됩니다. 값 및 서식 지정 코드의 의미를 `Format` 다음과 같습니다.

- **%H** 현재 날짜 시간

- **%M** 현재 시간에서 분

- **%S** 현재 분의 시간 (초)

- **%%** 백분율 기호

위에 나열 된 4 개의 코드 형식을 허용 하는 유일한 코드는 합니다.

-

*nID*<br/>
형식 컨트롤 문자열에 대 한 리소스 ID입니다.

### <a name="return-value"></a>반환 값

`CString` 서식이 지정 된 날짜/시간 범위 값이 들어 있는입니다.

### <a name="remarks"></a>설명

시간 범위 값의 서식이 지정 된 표현을 만들려면 이러한 함수를 호출 합니다. 하는 경우이 상태의 `COleDateTimeSpan` 개체가 null 이면 반환 값은 빈 문자열입니다. 상태가 올바르지 않은 경우 반환 문자열 IDS_INVALID_DATETIMESPAN 문자열 리소스에 의해 지정 됩니다.

이 함수에 대 한 폼에 대 한 간단한 설명은 다음과 같습니다.

**Format(** *pFormat* **)**<br/>
이 폼에서와 같이 백분율 기호 (%) 뒤에 나오는 특별 한 서식 지정 코드를 포함 하는 형식 문자열을 사용 하 여 값의 서식을 지정 `printf`합니다. 서식 문자열은 함수에 매개 변수로 전달 됩니다.

**Format(** *nID* **)**<br/>
이 폼에서와 같이 백분율 기호 (%) 뒤에 나오는 특별 한 서식 지정 코드를 포함 하는 형식 문자열을 사용 하 여 값의 서식을 지정 `printf`합니다. 서식 문자열 리소스입니다. 이 문자열 리소스의 ID 매개 변수로 전달 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]

##  <a name="getdays"></a>  COleDateTimeSpan::GetDays

이 날짜/시간 범위 값의 일 부분을 검색합니다.

```
LONG GetDays() const throw();
```

### <a name="return-value"></a>반환 값

이 날짜/시간 범위 값의 일 부분입니다.

### <a name="remarks"></a>설명

반환 값이 함수 사이에서 약-3,615,000 및 3,615,000 합니다.

값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체 멤버 함수는 다음을 참조 하세요.

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]

##  <a name="gethours"></a>  COleDateTimeSpan::GetHours

이 날짜/시간 범위 값의 시간 부분을 검색합니다.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>반환 값

이 날짜/시간 범위 값의 시간 부분입니다.

### <a name="remarks"></a>설명

이 함수 범위-23에서 23 사이에서 반환 하는 값입니다.

값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체 멤버 함수는 다음을 참조 하세요.

- [GetDays](#getdays)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]

##  <a name="getminutes"></a>  COleDateTimeSpan::GetMinutes

이 날짜/시간 범위 값의 분 부분을 검색합니다.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>반환 값

이 날짜/시간 범위 값의 분 부분입니다.

### <a name="remarks"></a>설명

-59에서 59 사이의이 함수 범위에서 반환 하는 값입니다.

값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체 멤버 함수는 다음을 참조 하세요.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]

##  <a name="getseconds"></a>  COleDateTimeSpan::GetSeconds

이 날짜/시간 범위 값의 두 번째 부분을 검색 합니다.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>반환 값

이 날짜/시간 범위 값의 초 부분입니다.

### <a name="remarks"></a>설명

-59에서 59 사이의이 함수 범위에서 반환 하는 값입니다.

값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체 멤버 함수는 다음을 참조 하세요.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]

##  <a name="getstatus"></a>  COleDateTimeSpan::GetStatus

이 상태 (유효성)를 가져옵니다 `COleDateTimeSpan` 개체입니다.

```
DateTimeSpanStatus GetStatus() const throw();
```

### <a name="return-value"></a>반환 값

이 상태의 `COleDateTimeSpan` 값입니다.

### <a name="remarks"></a>설명

반환 값으로 정의 됩니다는 `DateTimeSpanStatus` 내에 정의 된 형식 열거는 `COleDateTimeSpan` 클래스.

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
};
```

이러한 상태 값의 간략 한 설명을 다음 목록을 참조 합니다.

- `COleDateTimeSpan::valid` 나타냅니다이 `COleDateTimeSpan` 개체는 유효 합니다.

- `COleDateTimeSpan::invalid` 나타냅니다이 `COleDateTimeSpan` 개체가 잘못 되었습니다. 즉, 해당 값 잘못 되었을 수 있습니다.

- `COleDateTimeSpan::null` 나타냅니다이 `COleDateTimeSpan` 개체가 null 인 경우 즉,이 개체에 대해 제공 된 값입니다. (이 값이 "null" 의"값 없음."와 반대로 데이터베이스 점에서 C++ NULL입니다.)

상태를 `COleDateTimeSpan` 개체가 같은 경우에 유효 하지 않습니다.

- 발생 한 경우이 개체에는 오버플로 또는 언더플로 산술 할당 작업 중 namely `+=` 또는 `-=`합니다.

- 잘못 된 값이이 개체에 할당 되었습니다 하는 경우.

- 이 개체의 상태를 사용 하 여 잘못 된 명시적으로 설정한 경우 `SetStatus`합니다.

에 잘못 된 상태를 설정할 수 있는 작업에 대 한 자세한 내용은 참조 하세요. [COleDateTimeSpan::operator +,-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) 하 고 [COleDateTimeSpan::operator + =,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)합니다.

에 대 한 범위에 대 한 자세한 내용은 `COleDateTimeSpan` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원을](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.

##  <a name="gettotaldays"></a>  COleDateTimeSpan::GetTotalDays

일 단위로이 날짜/시간 범위 값을 검색 합니다.

```
double GetTotalDays() const throw();
```

### <a name="return-value"></a>반환 값

일 단위로이 날짜/시간 범위 값입니다. 이 함수는 double 값을 반환할 프로토타입화 경우에 항상 정수 값을 반환 합니다.

### <a name="remarks"></a>설명

이 함수 범위 사이의 약-3.65e6 3.65e6에서에서 반환 값입니다.

값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체 멤버 함수는 다음을 참조 하세요.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]

##  <a name="gettotalhours"></a>  COleDateTimeSpan::GetTotalHours

시간 단위로이 날짜/시간 범위 값을 검색 합니다.

```
double GetTotalHours() const throw();
```

### <a name="return-value"></a>반환 값

시간 단위로이 날짜/시간 범위 값입니다. 이 함수는 double 값을 반환할 프로토타입화 경우에 항상 정수 값을 반환 합니다.

### <a name="remarks"></a>설명

이 함수 범위 사이의 약-8.77e7 8.77e7에서에서 반환 값입니다.

값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체 멤버 함수는 다음을 참조 하세요.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>예제

예를 참조 하세요 [GetTotalDays](#gettotaldays)합니다.

##  <a name="gettotalminutes"></a>  COleDateTimeSpan::GetTotalMinutes

분 단위로 표현 된이 날짜/시간 범위 값을 검색 합니다.

```
double GetTotalMinutes() const throw();
```

### <a name="return-value"></a>반환 값

분 단위로 표현 된이 날짜/시간 범위 값입니다. 이 함수는 double 값을 반환할 프로토타입화 경우에 항상 정수 값을 반환 합니다.

### <a name="remarks"></a>설명

이 함수 범위 사이의 약-5.26e9 5.26e9에서에서 반환 값입니다.

값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체 멤버 함수는 다음을 참조 하세요.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>예제

예를 참조 하세요 [GetTotalDays](#gettotaldays)합니다.

##  <a name="gettotalseconds"></a>  COleDateTimeSpan::GetTotalSeconds

초 단위로 표현 된이 날짜/시간 범위 값을 검색 합니다.

```
double GetTotalSeconds() const throw();
```

### <a name="return-value"></a>반환 값

초 단위로이 날짜/시간 범위 값입니다. 이 함수는 double 값을 반환할 프로토타입화 경우에 항상 정수 값을 반환 합니다.

### <a name="remarks"></a>설명

이 함수에서 반환 값을 약-3.16e11를 3.16e11 사이입니다.

값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체 멤버 함수는 다음을 참조 하세요.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

### <a name="example"></a>예제

예를 참조 하세요 [GetTotalDays](#gettotaldays)합니다.

##  <a name="m_span"></a>  COleDateTimeSpan::m_span

내부 **이중** 값이 `COleDateTime` 개체입니다.

```
double m_span;
```

### <a name="remarks"></a>설명

이 값을 날짜/시간 범위 (일)을 표현합니다.

> [!CAUTION]
>  값을 변경 합니다 **이중** 데이터 멤버의 값이 바뀝니다 `COleDateTimeSpan` 개체입니다. 이 상태는 변경 되지 않습니다 `COleDateTimeSpan` 개체입니다.

##  <a name="m_status"></a>  COleDateTimeSpan::m_status

이 데이터 멤버에 대 한 형식은 열거형된 형식 `DateTimeSpanStatus`, 내에서 정의 되는 `COleDateTimeSpan` 클래스입니다.

```
DateTimeSpanStatus m_status;
```

### <a name="remarks"></a>설명

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

이러한 상태 값의 간략 한 설명을 다음 목록을 참조 합니다.

- `COleDateTimeSpan::valid` 나타냅니다이 `COleDateTimeSpan` 개체는 유효 합니다.

- `COleDateTimeSpan::invalid` 나타냅니다이 `COleDateTimeSpan` 개체가 잘못 되었습니다. 즉, 해당 값 잘못 되었을 수 있습니다.

- `COleDateTimeSpan::null` 나타냅니다이 `COleDateTimeSpan` 개체가 null 인 경우 즉,이 개체에 대해 제공 된 값입니다. (이 값이 "null" 의"값 없음."와 반대로 데이터베이스 점에서 C++ NULL입니다.)

상태를 `COleDateTimeSpan` 개체가 같은 경우에 유효 하지 않습니다.

- 발생 한 경우이 개체에는 오버플로 또는 언더플로 산술 할당 작업 중 namely `+=` 또는 `-=`합니다.

- 잘못 된 값이이 개체에 할당 되었습니다 하는 경우.

- 이 개체의 상태를 사용 하 여 잘못 된 명시적으로 설정 되었는지 여부 [SetStatus](#setstatus)합니다.

에 잘못 된 상태를 설정할 수 있는 작업에 대 한 자세한 내용은 참조 하세요. [COleDateTimeSpan::operator +,-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) 하 고 [COleDateTimeSpan::operator + =,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)합니다.

> [!CAUTION]
>  이 데이터 멤버는 고급 프로그래밍 시나리오입니다. 인라인 멤버 함수를 사용 해야 [GetStatus](#getstatus) 하 고 [SetStatus](#setstatus)합니다. 참조 `SetStatus` 이 데이터 멤버를 명시적으로 설정 하는 것에 대 한 추가 주의 사항에 대 한 합니다.

에 대 한 범위에 대 한 자세한 내용은 `COleDateTimeSpan` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원을](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.

##  <a name="operator_eq"></a>  COleDateTimeSpan::operator =

복사본을 `COleDateTimeSpan` 값입니다.

```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```

### <a name="remarks"></a>설명

이 오버 로드 된 할당 연산자 복사 원본 날짜/시간 범위 값이 `COleDateTimeSpan` 개체입니다.

##  <a name="operator_add_-"></a>  COleDateTimeSpan::operator +, -

추가, 빼기, 및에 대 한 로그인을 변경할 `COleDateTimeSpan` 값입니다.

```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```

### <a name="remarks"></a>설명

처음 두 연산자를 사용 하 여 추가 하 고 날짜/시간 범위 값을 뺄 수 있습니다. 세 번째 날짜/시간 범위 값의 부호를 변경할 수 있습니다.

Null이 고, 결과의 상태를 피연산자 중 하나 이면 `COleDateTimeSpan` 값은 null입니다.

피연산자 중 하나가 올바르지 않습니다. null이 아니면 다른 경우 결과의 상태 `COleDateTimeSpan` 값이 잘못 되었습니다.

유효 하 고, 잘못 된 경우 null 상태 값에 대 한 자세한 내용은 참조는 [m_status](#m_status) 멤버 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  COleDateTimeSpan::operator +=, -=

더하기 및 빼기는 `COleDateTimeSpan` 값이 `COleDateTimeSpan` 값입니다.

```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>설명

이러한 연산자를 사용 하면 더하기 및 빼기에서 날짜/시간 범위 값 `COleDateTimeSpan` 개체입니다. Null이 고, 결과의 상태를 피연산자 중 하나 이면 `COleDateTimeSpan` 값은 null입니다.

피연산자 중 하나가 올바르지 않습니다. null이 아니면 다른 경우 결과의 상태 `COleDateTimeSpan` 값이 잘못 되었습니다.

유효 하 고, 잘못 된 경우 null 상태 값에 대 한 자세한 내용은 참조는 [m_status](#m_status) 멤버 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]

##  <a name="operator_double"></a>  COleDateTimeSpan::operator double

이 변환 `COleDateTimeSpan` 값을 **double**합니다.

```
operator double() const throw();
```

### <a name="remarks"></a>설명

이 값을 반환 하는이 연산자 `COleDateTimeSpan` 일의 부동 소수점 숫자 값입니다.

##  <a name="setdatetimespan"></a>  COleDateTimeSpan::SetDateTimeSpan

이 날짜/시간 범위 값의 값을 설정 합니다.

```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>매개 변수

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
이에 복사할 날짜 범위 및 시간 범위 값을 나타내는 `COleDateTimeSpan` 개체입니다.

### <a name="remarks"></a>설명

값을 쿼리 하는 함수에 대 한는 `COleDateTimeSpan` 개체 멤버 함수는 다음을 참조 하세요.

- [GetDays](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [GetTotalDays](#gettotaldays)

- [GetTotalHours](#gettotalhours)

- [GetTotalMinutes](#gettotalminutes)

- [GetTotalSeconds](#gettotalseconds)

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]

##  <a name="setstatus"></a>  COleDateTimeSpan::SetStatus

상태를 설정 합니다 (유효성)이 `COleDateTimeSpan` 개체입니다.

```
void SetStatus(DateTimeSpanStatus status) throw();
```

### <a name="parameters"></a>매개 변수

*status*<br/>
이 대 한 새 상태 값을 `COleDateTimeSpan` 개체입니다.

### <a name="remarks"></a>설명

합니다 *상태* 매개 변수 값으로 정의 됩니다 합니다 `DateTimeSpanStatus` 열거 형식 내에 정의 된를 `COleDateTimeSpan` 클래스입니다.

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

이러한 상태 값의 간략 한 설명을 다음 목록을 참조 합니다.

- `COleDateTimeSpan::valid` 나타냅니다이 `COleDateTimeSpan` 개체는 유효 합니다.

- `COleDateTimeSpan::invalid` 나타냅니다이 `COleDateTimeSpan` 개체가 잘못 되었습니다. 즉, 해당 값 잘못 되었을 수 있습니다.

- `COleDateTimeSpan::null` 나타냅니다이 `COleDateTimeSpan` 개체가 null 인 경우 즉,이 개체에 대해 제공 된 값입니다. (이 값이 "null" 의"값 없음."와 반대로 데이터베이스 점에서 C++ NULL입니다.)

   > [!CAUTION]
   > 이 기능은 고급 프로그래밍 시나리오에 대 한 합니다. 이 함수는이 개체의 데이터를 변경 하지 않습니다. 상태를 설정 하는 데 사용 될 가장 자주 됩니다 **null** 하거나 **잘못 된**합니다. 대입 연산자 ([연산자 =](#operator_eq)) 및 [SetDateTimeSpan](#setdatetimespan) 원본 값에 따라 개체의 상태를 설정 하려면.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]

## <a name="see-also"></a>참고자료

[COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md)<br/>
[CTime 클래스](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[CTimeSpan 클래스](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
