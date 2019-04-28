---
title: CTimeSpan 클래스
ms.date: 10/18/2018
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
ms.openlocfilehash: 3c80260c1f57e49a34b4e9f3331f4d0d69ab30ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252535"
---
# <a name="ctimespan-class"></a>CTimeSpan 클래스

되는 시간 기간 시간 (초)의 숫자와 내부적으로 저장 됩니다.

## <a name="syntax"></a>구문

```
class CTimeSpan
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CTimeSpan::CTimeSpan](#ctimespan)|생성 `CTimeSpan` 다양 한 방법으로 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CTimeSpan::Format](#format)|변환 된 `CTimeSpan` 서식이 지정 된 문자열로 합니다.|
|[CTimeSpan::GetDays](#getdays)|두 일 수를 나타내는 값을 반환 `CTimeSpan`합니다.|
|[CTimeSpan::GetHours](#gethours)|현재 날짜 (23 23 까지입니다)의 시간 수를 나타내는 값을 반환 합니다.|
|[CTimeSpan::GetMinutes](#getminutes)|현재 시간 (-59에서 59 사이)에 분 수를 나타내는 값을 반환 합니다.|
|[CTimeSpan::GetSeconds](#getseconds)|현재 분 (-59에서 59 사이)에 시간 (초) 수를 나타내는 값을 반환 합니다.|
|[CTimeSpan::GetTimeSpan](#gettimespan)|값을 반환 합니다 `CTimeSpan` 개체입니다.|
|[CTimeSpan::GetTotalHours](#gettotalhours)|이 전체 시간의 총 수를 나타내는 값을 반환 `CTimeSpan`합니다.|
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|이 분의 총 수를 나타내는 값을 반환 `CTimeSpan`합니다.|
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|이 전체 시간 (초)의 총 수를 나타내는 값을 반환 `CTimeSpan`합니다.|
|[CTimeSpan::Serialize64](#serialize64)|보관 파일에서 데이터를 serialize합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator + -](#operator_add_-)|더하고 빼는 `CTimeSpan` 개체입니다.|
|[operator += -=](#operator_add_eq_-_eq)|더하고 빼는 `CTimeSpan` 개체를이 `CTimeSpan`합니다.|
|[operator == < etc.](#ctimespan_comparison_operators)|두 개의 상대 시간 값을 비교합니다.|

## <a name="remarks"></a>설명

`CTimeSpan` 기본 클래스는 없습니다.

`CTimeSpan` 함수에는 다양 한 일, 시, 분, 초 및 시간 (초)로 변환 합니다.

합니다 `CTimeSpan` 개체에 저장 됩니다는 **__time64_t** 구조를 8 바이트입니다.

도우미 클래스인 [CTime](../../atl-mfc-shared/reference/ctime-class.md), 절대 시간을 나타냅니다.

합니다 `CTime` 고 `CTimeSpan` 파생 클래스 설계 되지 않았습니다. 둘 다의 크기 가상 함수가 없는 되므로 `CTime` 및 `CTimeSpan` 개체는 8 바이트 정확 하 게 합니다. 대부분의 멤버 함수는 인라인입니다.

사용 하 여 대 한 자세한 내용은 `CTimeSpan`, 문서를 참조 하세요 [날짜 및 시간](../../atl-mfc-shared/date-and-time.md), 및 [시간 관리](../../c-runtime-library/time-management.md) 에 *런타임 라이브러리 참조*합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atltime.h

##  <a name="ctimespan_comparison_operators"></a>  CTimeSpan 비교 연산자

비교 연산자입니다.

```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
비교할 개체입니다.

### <a name="return-value"></a>반환 값

이러한 연산자는 두 개의 상대 시간 값을 비교합니다. 조건이 true 이면 TRUE 반환 그렇지 않으면 FALSE입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]

##  <a name="ctimespan"></a>  CTimeSpan::CTimeSpan

생성 `CTimeSpan` 다양 한 방법으로 개체입니다.

```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(
    LONG lDays,
    int nHours,
    int nMins,
    int nSecs) throw();
```

### <a name="parameters"></a>매개 변수

*timeSpanSrc*<br/>
`CTimeSpan` 이미 존재 하는 개체입니다.

*time*<br/>
A **__time64_t** 시간 값에서 시간 범위를 시간 (초)입니다.

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
일, 시간, 분 및 초, 각각.

### <a name="remarks"></a>설명

이러한 모든 생성자를 만듭니다 `CTimeSpan` 지정된 된 상대 시간을 사용 하 여 초기화 하는 개체입니다. 각 생성자에 대 한 설명은 다음과 같습니다.

- `CTimeSpan( );` 초기화 되지 않은 생성 `CTimeSpan` 개체입니다.

- `CTimeSpan( const CTimeSpan& );` 생성 된 `CTimeSpan` 개체에서 다른 `CTimeSpan` 값입니다.

- `CTimeSpan( __time64_t );` 생성 된 `CTimeSpan` 에서 개체를 **__time64_t** 형식.

- `CTimeSpan( LONG, int, int, int );` 생성 된 `CTimeSpan` 각 구성 요소를 사용 하 여 구성 요소에서 개체를 다음 범위로 제한 합니다.

   |구성 요소|범위|
   |---------------|-----------|
   |*lDays*|0-25,000 (약)|
   |*nHours*|0-23|
   |*nMins*|0-59|
   |*nSecs*|0-59|

Microsoft Foundation Class 라이브러리의 디버그 버전 경우 어설션 또는 시간 구성 요소 범위를 벗어났습니다. 호출 하기 전에 인수의 유효성을 검사 해야 하는 것입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]

##  <a name="format"></a>  CTimeSpan::Format

이에 해당 하는 서식이 지정 된 문자열을 생성 `CTimeSpan`합니다.

```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>매개 변수

*pFormat*, *pszFormat*<br/>
유사한 문자열 서식의 `printf` 문자열 서식을 지정 합니다. 서식 코드 앞에 백분율 (`%`)에 서명, 해당 바뀝니다 `CTimeSpan` 구성 요소입니다. 반환된 된 문자열에 형식 문자열에 다른 문자 변경 되지 않고 복사 됩니다. 값 및 서식 지정 코드의 의미를 `Format` 다음과 같습니다.

- **%D** 총이 일 수 `CTimeSpan`

- **%H** 현재 날짜 시간

- **%M** 현재 시간에서 분

- **%S** 현재 분의 시간 (초)

- **%%** 백분율 기호

*nID*<br/>
이 형식을 식별 하는 문자열의 ID입니다.

### <a name="return-value"></a>반환 값

`CString` 서식이 지정 된 시간을 포함 하는 개체입니다.

### <a name="remarks"></a>설명

형식 지정 코드를 확인 하 고 코드는 위 목록에 없으면 어설션 하는 라이브러리의 디버그 버전입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]

##  <a name="getdays"></a>  CTimeSpan::GetDays

두 일 수를 나타내는 값을 반환 `CTimeSpan`합니다.

```
LONGLONG GetDays() const throw();
```

### <a name="return-value"></a>반환 값

시간 범위에서 전체 24 일 수를 반환합니다. 이 값은 시간 범위에 좋지 않은 경우에 음수일 수 있습니다.

### <a name="remarks"></a>설명

일광 절약 시간을 일으킬 수 있는 참고 `GetDays` 잠재적으로 놀라운 결과 반환 합니다. 예를 들어 DST 경우 실제로 `GetDays` 4 월에서 1 일을 시간으로 단축 됩니다 및 완료 일으로 계산 되지 않습니다 때문에 29, 30이 아닌으로 사이의 년 4 월 1 월 1 일 수를 보고 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]

##  <a name="gethours"></a>  CTimeSpan::GetHours

현재 날짜 (23 23 까지입니다)의 시간 수를 나타내는 값을 반환 합니다.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>반환 값

현재 날짜에 시간을 반환합니다. 범위는 23 23 까지입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]

##  <a name="getminutes"></a>  CTimeSpan::GetMinutes

현재 시간 (-59에서 59 사이)에 분 수를 나타내는 값을 반환 합니다.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>반환 값

현재 시간에서 분 수를 반환합니다. 범위는-59에서 59 사이입니다.

### <a name="example"></a>예제

예를 참조 하세요 [GetHours](#gethours)합니다.

##  <a name="getseconds"></a>  CTimeSpan::GetSeconds

현재 분 (-59에서 59 사이)에 시간 (초) 수를 나타내는 값을 반환 합니다.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>반환 값

현재 분의 시간 (초) 수를 반환합니다. 범위는-59에서 59 사이입니다.

### <a name="example"></a>예제

예를 참조 하세요 [GetHours](#gethours)합니다.

##  <a name="gettimespan"></a>  CTimeSpan::GetTimeSpan

값을 반환 합니다 `CTimeSpan` 개체입니다.

```
__ time64_t GetTimeSpan() const throw();
```

### <a name="return-value"></a>반환 값

현재 값을 반환 합니다 `CTimeSpan` 개체입니다.

##  <a name="gettotalhours"></a>  CTimeSpan::GetTotalHours

이 전체 시간의 총 수를 나타내는 값을 반환 `CTimeSpan`합니다.

```
LONGLONG GetTotalHours() const throw();
```

### <a name="return-value"></a>반환 값

이 전체 시간의 총 수를 반환 합니다. `CTimeSpan`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]

##  <a name="gettotalminutes"></a>  CTimeSpan::GetTotalMinutes

이 분의 총 수를 나타내는 값을 반환 `CTimeSpan`합니다.

```
LONGLONG GetTotalMinutes() const throw();
```

### <a name="return-value"></a>반환 값

이 분의 총 수를 반환 합니다. `CTimeSpan`합니다.

### <a name="example"></a>예제

예를 참조 하세요 [GetTotalHours](#gettotalhours)합니다.

##  <a name="gettotalseconds"></a>  CTimeSpan::GetTotalSeconds

이 전체 시간 (초)의 총 수를 나타내는 값을 반환 `CTimeSpan`합니다.

```
LONGLONG GetTotalSeconds() const throw();
```

### <a name="return-value"></a>반환 값

이 전체 시간 (초)의 총 수를 반환 합니다. `CTimeSpan`합니다.

### <a name="example"></a>예제

예를 참조 하세요 [GetTotalHours](#gettotalhours)합니다.

##  <a name="operator_add_-"></a>  CTimeSpan::operator +, -

더하고 빼는 `CTimeSpan` 개체입니다.

```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
에 추가할 값을 `CTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

`CTimeSpan` 작업의 결과 나타내는 개체입니다.

### <a name="remarks"></a>설명

이러한 두 연산자를 사용 하면 더하기 및 빼기를 `CTimeSpan` 개체와 서로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  CTimeSpan::operator +=, -=

더하고 빼는 `CTimeSpan` 개체를이 `CTimeSpan`합니다.

```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>매개 변수

*span*<br/>
에 추가할 값을 `CTimeSpan` 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 된 `CTimeSpan` 개체입니다.

### <a name="remarks"></a>설명

이러한 연산자를 사용 하면 더하기 및 빼기에 `CTimeSpan` 개체를이 `CTimeSpan`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]

##  <a name="serialize64"></a>  CTimeSpan::Serialize64

> [!NOTE]
>  이 메서드는 MFC 프로젝트에서 사용할 수만 있습니다.

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

[asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
