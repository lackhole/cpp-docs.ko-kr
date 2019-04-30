---
title: difftime, _difftime32, _difftime64
ms.date: 11/04/2016
apiname:
- _difftime32
- difftime
- _difftime64
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
- _difftime64
- difftime
- difftime64
- _difftime32
- difftime32
helpviewer_keywords:
- _difftime32 function
- difftime function
- time, finding the difference
- difftime64 function
- _difftime64 function
- difftime32 function
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
ms.openlocfilehash: 80aaac1696fc82db248b097e73a2d89d81a20346
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288525"
---
# <a name="difftime-difftime32-difftime64"></a>difftime, _difftime32, _difftime64

두 시간의 차이를 찾습니다.

## <a name="syntax"></a>구문

```C
double difftime( time_t timeEnd, time_t timeStart );
double _difftime32( __time32_t timeEnd, __time32_t timeStart );
double _difftime64( __time64_t timeEnd, __time64_t timeStart );
```

### <a name="parameters"></a>매개 변수

*timeEnd*<br/>
종료 시간입니다.

*timeStart*<br/>
시작 시간입니다.

## <a name="return-value"></a>반환 값

**difftime** 경과 된 시간에서 초 반환 *timeStart* 하려면 *시간 종료*합니다. 반환되는 값은 배정밀도 부동 소수점 숫자입니다. 반환 값은 오류를 나타내는 0일 수 있습니다.

## <a name="remarks"></a>설명

합니다 **difftime** 두 제공 된 시간 값 사이의 차이 계산 하는 함수 *timeStart* 하 고 *시간 종료*합니다.

제공 된 시간 값의 범위 내에 담겨 야 **time_t**합니다. **time_t** 64 비트 값입니다. 따라서 범위의 끝은 2038년 1월 18일 23:59:59(UTC)에서 3000년 12월 31일 23:59:59로 확장되었습니다. 더 낮은 범위의 **time_t** 는 계속 1970 년 1 월 1 일 자정입니다.

**difftime** 로 계산 되는 인라인 함수 이며 **_difftime32** 하거나 **_difftime64** 여부에 따라 **_USE_32BIT_TIME_T** 정의 됩니다. _difftime32 및 _difftime64는 시간 형식의 특정 크기를 강제로 사용하도록 직접 사용될 수 있습니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 매개 변수가 0 또는 음수인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 이러한 함수 실행을 계속 수 하는 경우 0을 반환 하 고 설정 **errno** 하 **EINVAL**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**difftime**|\<time.h>|
|**_difftime32**|\<time.h>|
|**_difftime64**|\<time.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```cpp
// crt_difftime.c
// This program calculates the amount of time
// needed to do a floating-point multiply 100 million times.
//

#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <float.h>

double RangedRand( float range_min, float range_max)
{
   // Generate random numbers in the half-closed interval
   // [range_min, range_max). In other words,
   // range_min <= random number < range_max
   return ((double)rand() / (RAND_MAX + 1) * (range_max - range_min)
            + range_min);
}

int main( void )
{
   time_t   start, finish;
   long     loop;
   double   result, elapsed_time;
   double   arNums[3];

   // Seed the random-number generator with the current time so that
   // the numbers will be different every time we run.
   srand( (unsigned)time( NULL ) );

   arNums[0] = RangedRand(1, FLT_MAX);
   arNums[1] = RangedRand(1, FLT_MAX);
   arNums[2] = RangedRand(1, FLT_MAX);
   printf( "Using floating point numbers %.5e %.5e %.5e\n", arNums[0], arNums[1], arNums[2] );

   printf( "Multiplying 2 numbers 100 million times...\n" );

   time( &start );
   for( loop = 0; loop < 100000000; loop++ )
      result = arNums[loop%3] * arNums[(loop+1)%3];
   time( &finish );

   elapsed_time = difftime( finish, start );
   printf( "\nProgram takes %6.0f seconds.\n", elapsed_time );
}
```

```Output
Using random floating point numbers 1.04749e+038 2.01482e+038 1.72737e+038
Multiplying 2 floating point numbers 100 million times...
Program takes      3 seconds.
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[시간 관리](../../c-runtime-library/time-management.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
