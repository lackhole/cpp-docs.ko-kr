---
title: mktime, _mktime32, _mktime64
ms.date: 11/04/2016
apiname:
- _mktime32
- mktime
- _mktime64
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mktime
- _mktime64
helpviewer_keywords:
- _mktime32 function
- mktime function
- time functions
- mktime64 function
- converting times
- mktime32 function
- _mktime64 function
- time, converting
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
ms.openlocfilehash: 8e9524249d6c90323bdcfc0b92ecf2dad281c79b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499907"
---
# <a name="mktime-mktime32-mktime64"></a>mktime, _mktime32, _mktime64

현지 시간을 달력 값으로 변환합니다.

## <a name="syntax"></a>구문

```C
time_t mktime(
   struct tm *timeptr
);
__time32_t _mktime32(
   struct tm *timeptr
);
__time64_t _mktime64(
   struct tm *timeptr
);
```

### <a name="parameters"></a>매개 변수

*timeptr*<br/>
시간 구조에 대한 포인터입니다. [asctime](asctime-wasctime.md)을 참조하세요.

## <a name="return-value"></a>반환 값

**_mktime32** 형식의 값으로 인코딩된 지정한 달력 시간을 반환 [time_t](../../c-runtime-library/standard-types.md)합니다. 하는 경우 *timeptr* 1970 년 1 월 1 일 자정 이전의 날짜를 참조 하거나 해당 달력 시간을 표현할 수 없는 경우 **_mktime32** 형식으로 캐스팅 하는-1을 반환 **time_t**합니다. 사용 하는 경우 **_mktime32** 경우에 *timeptr* 23시 59분: 59 2038 년 1 월 18 일 utc (협정 세계시) 이후 날짜를 참조 형식으로 캐스팅 하는-1을 반환 합니다 **time_t**합니다.

**_mktime64** 형식으로 캐스팅 하는-1을 반환 합니다 **__time64_t** 하는 경우 *timeptr* 23시 59분: 59, 3000 년 12 월 31 일, UTC 이후 날짜를 참조 합니다.

## <a name="remarks"></a>설명

합니다 **mktime**를 **_mktime32** 하 고 **_mktime64** 함수 변환로 가리키는 제공 된 시간 구조 (불완전할 수 있음) *timeptr*정규화 된 값을 사용 하 여 완벽 하 게 정의 된 구조로 및 다음으로 변환 하는 **time_t** 달력 시간 값입니다. 변환된 시간은 [time](time-time32-time64.md) 함수가 반환한 값과 인코딩이 동일합니다. 원래 값을 **tm_wday** 하 고 **tm_yday** 의 구성 요소를 *timeptr* 구조 무시 되 고 다른 구성 요소의 원래 값이 제한 됩니다. 정상 범위로 합니다.

**mktime** 에 해당 하는 인라인 함수 이며 **_mktime64**경우가 아니면 **_USE_32BIT_TIME_T** 경우에서에 해당 하는 정의 된 **_mktime32** .

UTC로 조정 후 **_mktime32** 에서 날짜를 처리 1970 년 1 월 1 일 자정부터 23시 59분: 59 2038 년 1 월 18 일 UTC입니다. **_mktime64** 핸들 날짜부터 23시 59분: 59 1970 년 1 월 1 일 자정에서 3000 년 12 월 31 일입니다. 이러한 조정은-1을 반환 하기 위해 이러한 함수를 발생할 수 있습니다 (캐스팅할 **time_t**를 **__time32_t** 또는 **__time64_t**) 지정한 날짜가 범위 내에 합니다. 예를 들어 UTC보다 2시간 빠른 이집트의 카이로에 있으면 *timeptr*에 지정한 날짜에서 먼저 2시간을 뺍니다. 그러면 해당 날짜가 범위를 벗어날 수 있습니다.

이러한 함수는 tm 구조의 유효성을 검사하고 시간 구조를 채우는 데 사용할 수 있습니다. 경우 성공 하면 이러한 함수 값을 설정할 **tm_wday** 하 고 **tm_yday** 적절 하 게 하 고, 지정한 달력 시간을 나타내는 다른 구성 요소를 설정 하지만 해당 값을 사용 하 여 일반 강제 범위입니다. 최종 값 **tm_mday** 까지 설정 되지 않은 **tm_mon** 하 고 **tm_year** 결정 됩니다. 지정 하는 경우는 **tm** 구조 시간을 설정 합니다 **tm_isdst** 필드:

- 0은 표준 시간이 적용 중임을 나타냅니다.

- 0보다 큰 값은 일광 절약 시간이 적용 중임을 나타냅니다.

- 0보다 작은 값은 C 런타임 라이브러리 코드가 표준 시간 또는 일광 절약 시간이 적용 중인지 여부를 컴퓨팅하도록 합니다.

C 런타임 라이브러리는 [TZ](tzset.md) 환경 변수에서 일광 절약 시간 동작을 결정합니다. 하는 경우 **TZ** 을 설정 하지 않으면 Win32 API 호출인 [GetTimeZoneInformation](/windows/desktop/api/timezoneapi/nf-timezoneapi-gettimezoneinformation) 운영 체제에서 일광 절약 시간 정보를 가져오는 데 사용 됩니다. 이러한 정보를 가져오지 못하면 라이브러리에서는 일광 절약 시간 계산 구현을 위한 미국의 규칙이 사용된다고 가정합니다. **tm_isdst** 필수 필드입니다. 이 필드를 설정하지 않으면 해당 값이 정의되지 않고 이러한 함수의 반환 값을 예측할 수 없습니다. 경우 *timeptr* 가리키는 **tm** 에 대 한 이전 호출에서 반환 된 구조 [asctime](asctime-wasctime.md)를 [gmtime](gmtime-gmtime32-gmtime64.md), 또는 [localtime](localtime-localtime32-localtime64.md) (또는 이러한 함수의 변형)는 **tm_isdst** 필드에 올바른 값을 포함 합니다.

유의 **gmtime** 하 고 **localtime** (및 **_gmtime32**, **_gmtime64**를 **_localtime32**, 및 **_localtime64**) 변환을 위해 스레드당 단일 버퍼를 사용 합니다. 이 버퍼를 제공 하는 경우 **mktime**를 **_mktime32** 하거나 **_mktime64**, 이전 내용이 소멸 됩니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. *timeptr*이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 함수는 계속 실행 하도록 허용,-1을 반환 하 고 설정 **errno** 하 **EINVAL**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**mktime**|\<time.h>|
|**_mktime32**|\<time.h>|
|**_mktime64**|\<time.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_mktime.c
/* The example takes a number of days
* as input and returns the time, the current
* date, and the specified number of days.
*/

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm  when;
   __time64_t now, result;
   int        days;
   char       buff[80];

   time( &now );
   _localtime64_s( &when, &now );
   asctime_s( buff, sizeof(buff), &when );
   printf( "Current time is %s\n", buff );
   days = 20;
   when.tm_mday = when.tm_mday + days;
   if( (result = mktime( &when )) != (time_t)-1 ) {
      asctime_s( buff, sizeof(buff), &when );
      printf( "In %d days the time will be %s\n", days, buff );
   } else
      perror( "mktime failed" );
}
```

### <a name="sample-output"></a>샘플 출력

```Output
Current time is Fri Apr 25 13:34:07 2003

In 20 days the time will be Thu May 15 13:34:07 2003
```

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
