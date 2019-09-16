---
title: _mkgmtime, _mkgmtime32, _mkgmtime64
ms.date: 11/04/2016
api_name:
- _mkgmtime32
- _mkgmtime64
- _mkgmtime
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mkgmtime64
- mkgmtime32
- _mkgmtime32
- mkgmtime
- mkgmtime64
- _mkgmtime
helpviewer_keywords:
- mkgmtime32 function
- time functions
- mkgmtime function
- _mkgmtime function
- converting times
- mkgmtime64 function
- _mkgmtime64 function
- _mkgmtime32 function
- time, converting
ms.assetid: b4ca2b67-e198-4f43-b3e2-e8ad6bd01867
ms.openlocfilehash: fcd1e3fdcca37d7e5bb381c234a6d8555ce2766c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951663"
---
# <a name="_mkgmtime-_mkgmtime32-_mkgmtime64"></a>_mkgmtime, _mkgmtime32, _mkgmtime64

**Struct** **TM** 이 나타내는 utc 시간을 **time_t** 형식이 나타내는 utc 시간으로 변환 합니다.

## <a name="syntax"></a>구문

```C
time_t _mkgmtime(
   struct tm* timeptr
);
__time32_t _mkgmtime32(
   struct tm* timeptr
);
__time64_t _mkgmtime64(
   struct tm* timeptr
);
```

### <a name="parameters"></a>매개 변수

*timeptr*<br/>
변환할 **struct** **tm** 의 UTC 시간에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

1970 년 1 월 1 일 자정 이후 경과 된 시간 (초)을 나타내는 **__time32_t** 또는 **__time32_t** 형식의 수량 (utc (협정 세계시))입니다. 날짜가 범위를 벗어난 경우 (설명 섹션 참조) 또는 입력을 유효한 시간으로 해석할 수 없는 경우 반환 값은-1입니다.

## <a name="remarks"></a>설명

**_Mkgmtime32** 및 **_mkgmtime64** 함수는 utc 시간을 __ 시간을 나타내는 **__time32_t** 또는 **__time32_t** 형식으로 변환 합니다. 현지 시간을 UTC 시간으로 변환 하려면 **mktime**, **_mktime32**및 **_mktime64** 를 대신 사용 합니다.

**_mkgmtime** 는 **_mkgmtime64**로 계산 되는 인라인 함수 이며 **time_t** 는 **__time64_t**와 동일 합니다. 컴파일러가 **time_t** 를 이전 32 비트 **time_t**해석 하도록 강제 해야 하는 경우 **_USE_32BIT_TIME_T**를 정의할 수 있습니다. 2038 년 1 월 18 일 (32 비트 **time_t**의 최대 범위) 후에 응용 프로그램이 실패할 수 있으므로이 방법은 권장 되지 않으며 64 비트 플랫폼에서 모두 허용 되지 않습니다.

전달 된 시간 구조는 **_mktime** 함수를 사용 하 여 변경 되는 것과 동일한 방식으로 다음과 같이 변경 됩니다. **tm_wday** 및 **tm_yday** 필드는 **tm_mday** 및 **tm_year**의 값을 기반으로 하는 새 값으로 설정 됩니다. **Tm** 구조 시간을 지정 하는 경우 **tm_isdst** 필드를 다음과 같이 설정 합니다.

- 0은 표준 시간이 적용 중임을 나타냅니다.

- 0보다 큰 값은 일광 절약 시간이 적용 중임을 나타냅니다.

- 0보다 작은 값은 C 런타임 라이브러리 코드가 표준 시간 또는 일광 절약 시간이 적용 중인지 여부를 컴퓨팅하도록 합니다.

C 런타임 라이브러리는 TZ 환경 변수를 사용하여 올바른 일광 절약 시간을 결정합니다. TZ가 설정되어 있지 않으면 운영 체제를 쿼리하여 올바른 국가별 일광 절약 시간 동작을 가져옵니다. **tm_isdst** 은 필수 필드입니다. 설정 하지 않으면 해당 값이 정의 되지 않고 **mktime** 의 반환 값을 예측할 수 없습니다.

**_Mkgmtime32** 함수의 범위는 utc에서 1 월 1970 1 일 자정부터 23:59:59 년 1 월 18 일 2038, utc 까지의 시간입니다. **_Mkgmtime64** 의 범위는 1970 년 1 월 1 일 자정부터 23:59:59 년 12 월 3000 31 일 (utc) 까지의 utc입니다. 범위를 벗어난 날짜의 반환 값은-1입니다. **_Mkgmtime** 의 범위는 **_USE_32BIT_TIME_T** 가 정의 되었는지 여부에 따라 달라 집니다. 정의 되지 않은 경우 (기본값) 범위는 **_mkgmtime64**입니다. 그렇지 않으면 범위가 **_mkgmtime32**의 32 비트 범위로 제한 됩니다.

**Gmtime** 및 **localtime** 는 변환에 대해 정적으로 할당 된 단일 버퍼를 사용 합니다. 이 버퍼를 **mkgmtime**에 제공 하면 이전 내용이 제거 됩니다.

## <a name="example"></a>예제

```C
// crt_mkgmtime.c
#include <stdio.h>
#include <time.h>

int main()
{
    struct tm t1, t2;
    time_t now, mytime, gmtime;
    char buff[30];

    time( & now );

    _localtime64_s( &t1, &now );
    _gmtime64_s( &t2, &now );

    mytime = mktime(&t1);
    gmtime = _mkgmtime(&t2);

    printf("Seconds since midnight, January 1, 1970\n");
    printf("My time: %I64d\nGM time (UTC): %I64d\n\n", mytime, gmtime);

    /* Use asctime_s to display these times. */

    _localtime64_s( &t1, &mytime );
    asctime_s( buff, sizeof(buff), &t1 );
    printf( "Local Time: %s\n", buff );

    _gmtime64_s( &t2, &gmtime );
    asctime_s( buff, sizeof(buff), &t2 );
    printf( "Greenwich Mean Time: %s\n", buff );

}
```

### <a name="sample-output"></a>샘플 출력

```Output
Seconds since midnight, January 1, 1970
My time: 1171588492
GM time (UTC): 1171588492

Local Time: Thu Feb 15 17:14:52 2007

Greenwich Mean Time: Fri Feb 16 01:14:52 2007
```

다음 예제에서는 계산된 요일과 날짜 값을 사용하여 불완전한 구조체를 채우는 방법을 보여 줍니다.

```C
// crt_mkgmtime2.c
#include <stdio.h>
#include <time.h>
#include <memory.h>

int main()
{
    struct tm t1, t2;
    time_t gmtime;
    char buff[30];

    memset(&t1, 0, sizeof(struct tm));
    memset(&t2, 0, sizeof(struct tm));

    t1.tm_mon = 1;
    t1.tm_isdst = 0;
    t1.tm_year = 103;
    t1.tm_mday = 12;

    // The day of the week and year will be incorrect in the output here.
    asctime_s( buff, sizeof(buff), &t1);
    printf("Before calling _mkgmtime, t1 = %s t.tm_yday = %d\n",
            buff, t1.tm_yday );

    gmtime = _mkgmtime(&t1);

    // The correct day of the week and year were determined.
    asctime_s( buff, sizeof(buff), &t1);
    printf("After calling _mkgmtime, t1 = %s t.tm_yday = %d\n",
            buff, t1.tm_yday );

}
```

### <a name="output"></a>출력

```Output
Before calling _mkgmtime, t1 = Sun Feb 12 00:00:00 2003
t.tm_yday = 0
After calling _mkgmtime, t1 = Wed Feb 12 00:00:00 2003
t.tm_yday = 42
```

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
