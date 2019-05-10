---
title: gmtime_s, _gmtime32_s, _gmtime64_s
ms.date: 11/04/2016
apiname:
- _gmtime32_s
- gmtime_s
- _gmtime64_s
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
- _gmtime_s
- gmtime64_s
- gmtime32_s
- _gmtime64_s
- gmtime_s
- _gmtime32_s
helpviewer_keywords:
- gmtime_s function
- gmtime32_s function
- time functions
- gmtime64_s function
- _gmtime64_s function
- time structure conversion
- _gmtime_s function
- _gmtime32_s function
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
ms.openlocfilehash: 8225fed21ca9dc67440a4af5dcf43b2ad5cfdffb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157450"
---
# <a name="gmtimes-gmtime32s-gmtime64s"></a>gmtime_s, _gmtime32_s, _gmtime64_s

시간 값을 변환 된 **tm** 구조입니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t gmtime_s(
   struct tm* tmDest,
   const __time_t* sourceTime
);
errno_t _gmtime32_s(
   struct tm* tmDest,
   const __time32_t* sourceTime
);
errno_t _gmtime64_s(
   struct tm* tmDest,
   const __time64_t* sourceTime
);
```

### <a name="parameters"></a>매개 변수

*tmDest*<br/>
에 대 한 포인터를 [tm](../../c-runtime-library/standard-types.md) 구조입니다. 반환 된 구조체의 필드의 계산된 값을 유지 합니다 *타이머* UTC 대신 현지 시간 인수입니다.

*sourceTime*<br/>
저장된 시간에 대한 포인터입니다. 시간은 1970년 1월 1일 자정(00:00:00)(UTC(협정 세계시)) 이후 경과한 시간(초)으로 표현됩니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되는 경우 0입니다. 오류가 있을 경우 반환 값은 오류 코드입니다. 오류 코드는 Errno.h에 정의됩니다. 이러한 오류의 목록을 보려면 [errno](../../c-runtime-library/errno-constants.md)를 참조하세요.

### <a name="error-conditions"></a>오류 조건

|*tmDest*|*sourceTime*|반환|값 *tmDest*|
|-----------|------------|------------|--------------------|
|**NULL**|any|**EINVAL**|수정되지 않습니다.|
|되지 **NULL** (유효한 메모리를 가리킴)|**NULL**|**EINVAL**|모든 필드가 -1로 설정됩니다.|
|하지 **NULL**|< 0|**EINVAL**|모든 필드가 -1로 설정됩니다.|

처음 두 오류 조건의 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 돌아와 **EINVAL**합니다.

## <a name="remarks"></a>설명

합니다 **_gmtime32_s** 함수는 *sourceTime* 값 형식의 구조체에 저장 합니다 **tm**Time.h에 정의 된 합니다. 구조체의 주소에 전달 됩니다 *tmDest*합니다. 변수의 *sourceTime* 에 대 한 호출에서 가져온 일반적으로 [시간](time-time32-time64.md) 함수입니다.

> [!NOTE]
> 대상 환경에서는 일광 절약 시간이 적용되는지 확인해야 합니다. C 런타임 라이브러리에서는 일광 절약 시간 계산 구현을 위한 미국의 규칙이 사용된다고 가정합니다.

각 구조체 필드는 형식의 **int**다음 표에 나와 있는 것 처럼 합니다.

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
|**tm_isdst**|항상 0에 대 한 **gmtime_s**합니다.|

**_gmtime64_s**를 사용 합니다 **__time64_t** 구조에 날짜를 23시 59분: 59 까지의 3000 년 12 월 31 일, UTC; 표현할 수 있습니다. 반면 **gmtime32_s** 통해 날짜만 나타냅니다 23시 59분: 59 2038 년 1 월 18 일 UTC입니다. 1970년 1월 1일 자정은 이러한 두 함수 모두에 대한 날짜 범위의 하한입니다.

**gmtime_s** 계산 되는 인라인 함수 이며 **_gmtime64_s** 하 고 **time_t** 동일 **__time64_t**합니다. 해석 하도록 컴파일러에 게 해야 하는 경우 **time_t** 이전 32 비트로 **time_t**를 정의할 수 있습니다 **_USE_32BIT_TIME_T**합니다. 이렇게 하면 **gmtime_s** 에 인라인 할 **_gmtime32_s**합니다. 2038년 1월 18일 이후에는 애플리케이션에서 오류가 발생할 수 있으므로 이 방식은 사용하지 않는 것이 좋으며, 64비트 플랫폼에서는 이러한 방식이 허용되지 않습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 C 헤더|필수 C++ 헤더|
|-------------|---------------------|-|
|**gmtime_s**, **_gmtime32_s**, **_gmtime64_s**|\<time.h>|\<ctime > 또는 \<time.h >|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_gmtime64_s.c
// This program uses _gmtime64_s to convert a 64-bit
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime_s to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm newtime;
   __int64 ltime;
   char buf[26];
   errno_t err;

   _time64( &ltime );

   // Obtain coordinated universal time:
   err = _gmtime64_s( &newtime, &ltime );
   if (err)
   {
      printf("Invalid Argument to _gmtime64_s.");
   }

   // Convert to an ASCII representation
   err = asctime_s(buf, 26, &newtime);
   if (err)
   {
      printf("Invalid Argument to asctime_s.");
   }

   printf( "Coordinated universal time is %s\n",
           buf );
}
```

```Output
Coordinated universal time is Fri Apr 25 20:12:33 2003
```

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[_mkgmtime, _mkgmtime32, _mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
