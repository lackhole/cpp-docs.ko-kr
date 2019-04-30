---
title: _atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l
ms.date: 04/05/2018
apiname:
- _atoldbl
- _atoldbl_l
- _atodbl
- _atoflt
- _atoflt_l
- _atodbl_l
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _atoflt
- _atoflt_l
- atodbl_l
- atoflt_l
- _atoldbl
- _atoldbl_l
- atodbl
- _atodbl_l
- atoldbl
- atoflt
- atoldbl_l
- _atodbl
helpviewer_keywords:
- _atodbl function
- _atoldbl_l function
- atoflt function
- atoflt_l function
- atoldbl function
- _atoldbl function
- atodbl_l function
- _atoflt_l function
- atoldbl_l function
- atodbl function
- string conversion, to floating point values
- _atoflt function
- _atodbl_l function
ms.assetid: 2d2530f4-4bd4-42e3-8083-f2d2fbc8432a
ms.openlocfilehash: bb8d711dc8dfa912333f34603ad607f0a74143bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349279"
---
# <a name="atodbl-atodbll-atoldbl-atoldbll-atoflt-atofltl"></a>_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l

문자열을 double로 변환 합니다 (**_atodbl**), long double (**_atoldbl**), 또는 float (**_atoflt**).

## <a name="syntax"></a>구문

```C
int _atodbl( _CRT_DOUBLE * value, char * str );
int _atodbl_l ( _CRT_DOUBLE * value, char * str, locale_t locale );
int _atoldbl( _LDOUBLE * value, char * str );
int _atoldbl_l ( _LDOUBLE * value, char * str, locale_t locale );
int _atoflt( _CRT_FLOAT * value, const char * str );
int _atoflt_l( _CRT_FLOAT * value, const char * str, locale_t locale );
```

### <a name="parameters"></a>매개 변수

*값*<br/>
문자열을 부동 소수점 값으로 변환하여 생성되는 double, long double 또는 float 값입니다. 이러한 값은 구조체에서 래핑됩니다.

*str*<br/>
부동 소수점 값으로 변환하기 위해 구문 분석할 문자열입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

성공하면 0을 반환합니다. 가능한 오류 코드는 **_UNDERFLOW** 하거나 **_OVERFLOW**, 헤더 파일에 정의 된 \<math.h >.

## <a name="remarks"></a>설명

이러한 함수는 문자열을 부동 소수점 값으로 변환합니다. 이러한 함수 간의 차이점 및 **atof** 계열의 함수는 이러한 함수는 부동 소수점 코드를 생성 하지 않습니다 하 고 하드웨어 예외를 발생 하지 않습니다. 대신 오류 조건은 오류 코드로 보고됩니다.

문자열에 부동 소수점 값으로의 유효한 해석이 없으면 *값* 로 설정 되어 0이 있고 반환 값은 0입니다.

접미사가 있는 이러한 함수 버전을 **_l** 접미사는 동일 없는 접미사를 사용 하는 점을 제외 하 고 버전을 *로캘* 현재 스레드 대신 전달 된 매개 변수 로캘입니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|--------------|---------------------|
|**_atodbl**, **_atoldbl**, **_atoflt**<br /><br /> **_atodbl_l**, **_atoldbl_l**, **_atoflt_l**|\<stdlib.h>|

## <a name="example"></a>예제

```C
// crt_atodbl.c
// Uses _atodbl to convert a string to a double precision
// floating point value.

#include <stdlib.h>
#include <stdio.h>

int main()
{
   char str1[256] = "3.141592654";
   char abc[256] = "abc";
   char oflow[256] = "1.0E+5000";
   _CRT_DOUBLE dblval;
   _CRT_FLOAT fltval;
   int retval;

   retval = _atodbl(&dblval, str1);

   printf("Double value: %lf\n", dblval.x);
   printf("Return value: %d\n\n", retval);

   retval = _atoflt(&fltval, str1);
   printf("Float value: %f\n", fltval.f);
   printf("Return value: %d\n\n", retval);

   // A non-floating point value: returns 0.
   retval = _atoflt(&fltval, abc);
   printf("Float value: %f\n", fltval.f);
   printf("Return value: %d\n\n", retval);

   // Overflow.
   retval = _atoflt(&fltval, oflow);
   printf("Float value: %f\n", fltval.f);
   printf("Return value: %d\n\n", retval);

   return 0;
}
```

```Output
Double value: 3.141593
Return value: 0

Float value: 3.141593
Return value: 0

Float value: 0.000000
Return value: 0

Float value: inf
Return value: 3
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
