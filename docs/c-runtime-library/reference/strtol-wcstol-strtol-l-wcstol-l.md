---
title: strtol, wcstol, _strtol_l, _wcstol_l
ms.date: 11/04/2016
apiname:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
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
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
helpviewer_keywords:
- wcstol function
- wcstol_l function
- _tcstol function
- string conversion, to integers
- tcstol function
- strtol_l function
- _wcstol_l function
- _strtol_l function
- strtol function
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
ms.openlocfilehash: 73df5dd3ffcd4a9b2fca8b6b713b645ef94addb5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62379157"
---
# <a name="strtol-wcstol-strtoll-wcstoll"></a>strtol, wcstol, _strtol_l, _wcstol_l

문자열을 long 정수값으로 변환합니다.

## <a name="syntax"></a>구문

```C
long strtol(
   const char *strSource,
   char **endptr,
   int base
);
long wcstol(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
long _strtol_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
long _wcstol_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*strSource*<br/>
변환할 Null 종료 문자열입니다.

*endptr*<br/>
검색을 중지하는 문자에 대한 포인터입니다.

*base*<br/>
사용할 기수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**strtol** 문자열에서 나타내는 값을 반환 *strSource*표현, 인해 오버플로가 발생 하는 경우 반환 제외 하 고 **LONG_MAX** 또는 **LONG_ MIN**합니다. **strtol** 변환 작업 없이 수행할 수 있으면 0을 반환 합니다. **wcstol** 와 동일한 값을 반환 **strtol**합니다. 두 함수 모두에 대 한 **errno** 로 설정 된 **ERANGE** 오버플로 또는 언더플로가 발생 하는 경우.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은  [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **strtol** 변환 함수 *strSource* 에 **긴**합니다. **strtol** 문자열 읽기를 중지 *strSource* 숫자의 일부분으로 인식할 수 없는 첫 문자에서 합니다. 종결 null 문자를 수 있습니다 또는 보다 크거나 같은 첫 번째 숫자 문자일 수도 *기본*입니다.

**wcstol** 의 와이드 문자 버전이 **strtol**; 해당 *strSource* 인수는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

현재 로캘의 **LC_NUMERIC** 범주 설정의 기 수 문자 인식이 결정 *strSource*; 자세한 내용은 참조 하십시오 [setlocale](setlocale-wsetlocale.md)합니다. 없는 함수는 **_l** 접미사는 현재 로캘을 사용 **_strtol_l** 하 고 **_wcstol_l** 없는 해당 함수와 동일 합니다 **_l** 대신 전달 된 로캘을 사용 한다는 점을 제외 하면 접미사가 있습니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

하는 경우 *endptr* 아닙니다 **NULL**, 검색을 중지 한 문자에 대 한 포인터에서 가리키는 위치에 저장 됩니다 *endptr*합니다. 변환 작업 없이 수행할 수 있으면 (올바른 숫자를 찾을 수 없거나 잘못 된 자료를 지정 된), 값 *strSource* 가리키는 위치에 저장 된 *endptr*합니다.

**strtol** 예상 *strSource* 다음 형식의 문자열을 가리키도록 합니다.

> [*공백을*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*자릿수* &#124; *문자*]  

A *공백* 공백 및 탭 문자가 무시 되는 구성 될 수 있습니다 *자릿수* 는 하나 이상의 10 진수입니다. *문자* 가 문자의 하나 이상의 'a'-'z' (또는 'A' ~ 'Z').  이 형식에 맞지 않는 첫 번째 문자가 발견되면 검색이 중지됩니다. 하는 경우 *기본* 2와 36 사이의 인 숫자의 밑으로 사용 됩니다. 하는 경우 *기본* 은 0에서 가리키는 문자열의 초기 문자 *strSource* 밑을 결정 하는 데 사용 됩니다. 첫 번째 문자가 0이고 두 번째 문자가 'x' 또는 'X'가 아니면 문자열은 8진수 정수로 해석됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'이면 문자열은 16진수 정수로 해석됩니다. 첫 번째 문자가 '1'~'9' 이면 문자열은 10진수 정수로 해석됩니다. 문자 'a'~'z' 또는 'A'~'Z'에는 값 10~35가 할당됩니다. 할당된 값이 *밑*보다 작은 문자만 사용할 수 있습니다. 밑의 범위를 벗어난 첫 번째 문자가 발견되면 검색이 중지됩니다. 예를 들어 있으면 *기본* 0 및 처음 검색 된 문자가 '0'은는 8 진수 정수로 간주 되며 '8' 또는 '9' 문자는 검색은 중지 됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strtol**|\<stdlib.h>|
|**wcstol**|\<stdlib.h> 또는 \<wchar.h>|
|**_strtol_l**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[strtod](strtod-strtod-l-wcstod-wcstod-l.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
