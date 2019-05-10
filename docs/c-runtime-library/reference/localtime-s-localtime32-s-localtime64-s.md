---
title: localtime_s, _localtime32_s, _localtime64_s
ms.date: 11/04/2016
apiname:
- _localtime64_s
- _localtime32_s
- localtime_s
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
- _localtime32_s
- localtime32_s
- localtime_s
- localtime64_s
- _localtime64_s
helpviewer_keywords:
- _localtime64_s function
- localtime32_s function
- _localtime32_s function
- localtime64_s function
- time, converting values
- localtime_s function
ms.assetid: 842d1dc7-d6f8-41d3-b340-108d4b90df54
ms.openlocfilehash: 44b2eb2515035d56143a2aab251437a92515e652
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157292"
---
# <a name="localtimes-localtime32s-localtime64s"></a>localtime_s, _localtime32_s, _localtime64_s

변환를 **time_t** 시간 값을 **tm** 구조체 및 현지 표준 시간대에 맞게 수정 합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t localtime_s(
   struct tm* const tmDest,
   time_t const* const sourceTime
);
errno_t _localtime32_s(
   struct tm* tmDest,
   __time32_t const* sourceTime
);
errno_t _localtime64_s(
   struct tm* tmDest,
   __time64_t const* sourceTime
);
```

### <a name="parameters"></a>매개 변수

*tmDest*<br/>
입력할 시간 구조체에 대한 포인터입니다.

*sourceTime*<br/>
저장된 시간에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되는 경우 0입니다. 오류가 있을 경우 반환 값은 오류 코드입니다. 오류 코드는 Errno.h에서 정의됩니다. 이러한 오류의 목록은 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

### <a name="error-conditions"></a>오류 조건

|*tmDest*|*sourceTime*|반환 값|값 *tmDest*|잘못된 매개 변수 처리기 호출|
|-----------|------------|------------------|--------------------|---------------------------------------|
|**NULL**|any|**EINVAL**|수정 안 됨|예|
|되지 **NULL** (유효한 메모리를 가리킴)|**NULL**|**EINVAL**|모든 필드가 -1로 설정됨|예|
|되지 **NULL** (유효한 메모리를 가리킴)|보다 작거나 0 보다 크거나 **_MAX__TIME64_T**|**EINVAL**|모든 필드가 -1로 설정됨|아니요|

처음 두 오류 조건의 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 돌아와 **EINVAL**합니다.

## <a name="remarks"></a>설명

합니다 **_localtime32_s** 함수 변환으로 저장 된 시간을 [time_t](../../c-runtime-library/standard-types.md) 형식의 구조체에 결과 가져와 값 [tm](../../c-runtime-library/standard-types.md)합니다. 합니다 **긴** 값 *sourceTime* 자정 이후 경과 된 초를 나타냅니다 (00: 00:00) 1970 년 1 월 1, UTC입니다. 이 값에서 가져온 일반적으로 [시간](time-time32-time64.md) 함수입니다.

**_localtime32_s** 사용자는 먼저 전역 환경 변수를 설정 하는 경우 현지 표준 시간대에 맞게 수정 **TZ**합니다. 때 **TZ** 설정 되어 다른 세 가지 환경 변수 (**_timezone**에 **_daylight**, 및 **_tzname**)도 자동으로 설정 됩니다. 경우는 **TZ** 변수를 설정 하지 않으면 **localtime32_s** 제어판의 날짜/시간 응용 프로그램에서 지정한 표준 시간대 정보를 사용 하려고 합니다. 이 정보를 가져올 수 없으면 기본적으로 태평양 표준 시간대를 의미하는 PST8PDT가 사용됩니다. 이러한 변수에 대한 설명은 [_tzset](tzset.md)을 참조하세요. **TZ** 는 Microsoft 확장 이며 ANSI 표준 정의의 일부가 아닌 **localtime**합니다.

> [!NOTE]
> 대상 환경에서는 일광 절약 시간이 적용되는지 확인해야 합니다.

**_localtime64_s**를 사용 합니다 **__time64_t** 구조에 날짜를 23시 59분: 59를 1 월 18 일, 3001, UTC (coordinated universal time)를 통해 표현할 수 있습니다. 반면 **_localtime32_s** 23시 59분: 59 까지의 2038 년 1 월 18 일 UTC 날짜를 나타냅니다.

**localtime_s** 계산 되는 인라인 함수 이며 **_localtime64_s**, 및 **time_t** 동일 **__time64_t**합니다. 해석 하도록 컴파일러에 게 해야 하는 경우 **time_t** 이전 32 비트로 **time_t**를 정의할 수 있습니다 **_USE_32BIT_TIME_T**합니다. 이렇게 하면 **localtime_s** 로 평가 **_localtime32_s**합니다. 2038년 1월 18일 이후에는 애플리케이션에서 오류가 발생할 수 있으므로 이 방식은 사용하지 않는 것이 좋으며, 64비트 플랫폼에서는 이러한 방식이 허용되지 않습니다.

구조체 형식의 필드 [tm](../../c-runtime-library/standard-types.md) 있으며 각각 다음 값을 저장 한 **int**.

|필드|설명|
|-|-|
|**tm_sec**|분 이후의 초 (0-59).|
|**tm_min**|시간 이후의 분 (0-59).|
|**tm_hour**|자정 이후의 시간 (0-23).|
|**tm_mday**|일 (1-31)입니다.|
|**tm_mon**|월 (0 ~ 11; 1 월 = 0).|
|**tm_year**|연도(현재 연도 - 1900).|
|**tm_wday**|요일 (0-6; 일요일 = 0).|
|**tm_yday**|연간 일자 (0-365; 1 월 1 일 = 0).|
|**tm_isdst**|일광 절약 시간이 적용되면 양수, 일광 절약 시간이 적용되지 않으면 0, 일광 절약 시간의 상태를 알 수 없으면 음수입니다.|

경우는 **TZ** 환경 변수가 설정 되어, C 런타임 라이브러리 가정 규칙 미국에 적절 한 일광 절약 시간 (DST) 계산 구현을 위한 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 C 헤더|필수 C++ 헤더|
|-------------|---------------------|-|
|**localtime_s**, **_localtime32_s**, **_localtime64_s**|\<time.h>|\<ctime > 또는 \<time.h >|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_localtime_s.c
// This program uses _time64 to get the current time
// and then uses _localtime64_s() to convert this time to a structure
// representing the local time. The program converts the result
// from a 24-hour clock to a 12-hour clock and determines the
// proper extension (AM or PM).

#include <stdio.h>
#include <string.h>
#include <time.h>

int main( void )
{
    struct tm newtime;
    char am_pm[] = "AM";
    __time64_t long_time;
    char timebuf[26];
    errno_t err;

    // Get time as 64-bit integer.
    _time64( &long_time );
    // Convert to local time.
    err = _localtime64_s( &newtime, &long_time );
    if (err)
    {
        printf("Invalid argument to _localtime64_s.");
        exit(1);
    }
    if( newtime.tm_hour > 12 )        // Set up extension.
        strcpy_s( am_pm, sizeof(am_pm), "PM" );
    if( newtime.tm_hour > 12 )        // Convert from 24-hour
        newtime.tm_hour -= 12;        // to 12-hour clock.
    if( newtime.tm_hour == 0 )        // Set hour to 12 if midnight.
        newtime.tm_hour = 12;

    // Convert to an ASCII representation.
    err = asctime_s(timebuf, 26, &newtime);
    if (err)
    {
        printf("Invalid argument to asctime_s.");
        exit(1);
    }
    printf( "%.19s %s\n", timebuf, am_pm );
}
```

```Output
Fri Apr 25 01:19:27 PM
```

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
