---
title: strtod, _strtod_l, wcstod, _wcstod_l
ms.date: 10/20/2017
apiname:
- wcstod
- _wcstod_l
- _strtod_l
- strtod
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
- _tcstod
- strtod
- wcstod
- _strtod_l
- _wcstod_l
- stdlib/strtod
- corecrt_wstdlib/wcstod
- stdlib/_strtod_l
- corecrt_wstdlib/_wcstod_l
helpviewer_keywords:
- wcstod_l function
- tcstod_l function
- _tcstod_l function
- strtod function
- _wcstod_l function
- wcstod function
- strtod_l function
- tcstod function
- _tcstod function
- _strtod_l function
- string conversion, to floating point values
ms.assetid: 0444f74a-ba2a-4973-b7f0-1d77ba88c6ed
ms.openlocfilehash: c8c2b3b491e2e7265829fa88580529dc757ace8c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376473"
---
# <a name="strtod-strtodl-wcstod-wcstodl"></a>strtod, _strtod_l, wcstod, _wcstod_l

문자열을 배정밀도 값으로 변환합니다.

## <a name="syntax"></a>구문

```C
double strtod(
   const char *strSource,
   char **endptr
);
double _strtod_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
double wcstod(
   const wchar_t *strSource,
   wchar_t **endptr
);
double wcstod_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*strSource*<br/>
변환할 Null 종료 문자열입니다.

*endptr*<br/>
검색을 중지하는 문자에 대한 포인터입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**strtod** 표현을 인해 오버플로가 발생 + /-경우 함수 반환 하는 경우 제외 된 부동 소수점 숫자의 값을 반환**HUGE_VAL**합니다. 부호 **HUGE_VAL** 표현할 수 없는 값의 부호와 일치 합니다. **strtod** 변환을 수행할 수 없거나 언더플로가 발생 하는 경우 0을 반환 합니다.

**wcstod** 와 동일한 값을 반환 **strtod**합니다. 두 함수 모두에 대 한 **errno** 로 설정 된 **ERANGE** 오버플로 또는 언더플로가 발생 하에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

각 함수는 입력된 문자열을 변환 *strSource* 에 **double**합니다. 합니다 **strtod** 변환 함수 *strSource* 배정밀도 값으로. **strtod** 문자열 읽기를 중지 *strSource* 숫자의 일부분으로 인식할 수 없는 첫 문자에서 합니다. 이 문자는 종료 null 문자일 수 있습니다. **wcstod** 의 와이드 문자 버전이 **strtod**; 해당 *strSource* 인수는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

합니다 **LC_NUMERIC** 현재 로캘 범주 설정에서 지점 기 수 문자 인식이 결정 *strSource*합니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md)을 참조하세요. 없는 함수는 **_l** 접미사는 현재 로캘을 사용 **_strtod_l** 동일 **_strtod_l** 를 사용 하는 점을 제외 하 고는 *로캘* 대신 전달 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

하는 경우 *endptr* 아닙니다 **NULL**, 검색을 중지 한 문자에 대 한 포인터에서 가리키는 위치에 저장 됩니다 *endptr*합니다. 변환 작업 없이 수행할 수 있으면 (올바른 숫자를 찾을 수 없거나 잘못 된 자료를 지정 된), 값 *strSource* 가리키는 위치에 저장 된 *endptr*합니다.

**strtod** 예상 *strSource* 문자열을 다음 형식 중 하나를 가리키도록 합니다.

[*공백을*] [*기호*] {*자릿수* [*기* *자리*] &#124;  *기 수* *자리*} [{**e** &#124; **E**} [*기호*] *자리*] [*공백을*] [*sign*] {**0x** &#124; **0x**} {*hexdigits* [ *기* *hexdigits*] &#124; *기* *hexdigits*} [{**p** &#124; **P**} [*sign*] *hexdigits*] [*공백*] [*로그인*] { **INF** &#124; **무한대**} [*공백*] [*로그인*]  **NAN** [*시퀀스*]

선택적 선행 *공백* 공백 및 탭 문자가 무시 되는 구성 될 수 있습니다 *기호* 은 더하기 (+) 또는 빼기 (-) 이며 *자릿수* 는 하나 이상의 10 진수입니다. *hexdigits* 는 하나 이상의 16 진수입니다. *기* 됨 지점 기 수 문자, 마침표 (.) 기본 "C" 로캘에서 또는 현재 로캘이 다른 경우에 로캘별 값 *로캘* 지정 되어 있으면을 *시퀀스* 는 일련의 영숫자 또는 밑줄 문자입니다. 10 진수 및 16 진수 숫자 형식의 기 수 지점 문자 앞에 숫자가 있으면 하나 이상의 뒤에 나타나야 지점 기 수 문자입니다. 10 진수 형식, 소수 자릿수 올 수 있습니다는 소개 문자 구성 된 지 수 (**e** 하거나 **E**) 및 선택적으로 부호 있는 정수입니다. 16 진수 형식, 16 진수는 소개 문자 구성 된 지 수가 올 수 있습니다 (**p** 하거나 **P**)을 나타내는 부호 있는 16 진수 정수는 2의 거듭제곱으로 지 수입니다. 둘 중 하나의 형태로 지 수 부분을 아니고 지점 기 수 문자 표시 지점 기 수 문자 문자열의 마지막 숫자임을 수행 하려면 간주 됩니다. 둘 다에서 대/소문자를 무시할지를 **INF** 하 고 **NAN** forms 합니다. 이러한 형식 중 하나로 맞지 않는 첫 번째 문자는 검색을 중지 합니다.

이러한 함수의 UCRT 버전은 Fortran 스타일의 변환을 지원 하지 않습니다 (**d** 하거나 **D**) 지 수 문자의 합니다. 이러한 비표준 확장은 CRT의 이전 버전에서 지원되었으므로 코드에 대한 중요한 변경 사항일 수 있습니다. UCRT 버전은 16 진수 문자열 및 이전 버전에서 지원 되지 않았습니다 INF 및 NAN 값의 라운드트립을 지원 합니다. 코드에서 주요 변경 사항이 발생할 수 있습니다. 문자열 "0x1a"는 해석 하는 예를 들어 **strtod** UCRT 버전에서 26.0가 아니라 이전 버전에서는 0.0.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strtod**, **_strtod_l**|C: &lt;stdlib.h> C++: &lt;cstdlib> 또는 &lt;stdlib.h> |
|**wcstod**, **_wcstod_l**|C: &lt;stdlib.h> 또는 &lt;wchar.h> C++: &lt;cstdlib>, &lt;stdlib.h> 또는 &lt;wchar.h> |

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strtod.c
// This program uses strtod to convert a
// string to a double-precision value; strtol to
// convert a string to long integer values; and strtoul
// to convert a string to unsigned long-integer values.
//

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char   *string, *stopstring;
   double x;
   long   l;
   int    base;
   unsigned long ul;

   string = "3.1415926This stopped it";
   x = strtod( string, &stopstring );
   printf( "string = %s\n", string );
   printf("   strtod = %f\n", x );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "-10110134932This stopped it";
   l = strtol( string, &stopstring, 10 );
   printf( "string = %s\n", string );
   printf("   strtol = %ld\n", l );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "10110134932";
   printf( "string = %s\n", string );

   // Convert string using base 2, 4, and 8:
   for( base = 2; base <= 8; base *= 2 )
   {
      // Convert the string:
      ul = strtoul( string, &stopstring, base );
      printf( "   strtol = %ld (base %d)\n", ul, base );
      printf( "   Stopped scan at: %s\n", stopstring );
   }
}
```

```Output
string = 3.1415926This stopped it
   strtod = 3.141593
   Stopped scan at: This stopped it

string = -10110134932This stopped it
   strtol = -2147483648
   Stopped scan at: This stopped it

string = 10110134932
   strtol = 45 (base 2)
   Stopped scan at: 34932
   strtol = 4423 (base 4)
   Stopped scan at: 4932
   strtol = 2134108 (base 8)
   Stopped scan at: 932
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
