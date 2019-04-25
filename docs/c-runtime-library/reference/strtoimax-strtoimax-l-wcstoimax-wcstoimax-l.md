---
title: strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l
ms.date: 11/04/2016
apiname:
- wcstoimax
- _wcstoimax_l
- _strtoimax_l
- strtoimax
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
- wcstoimax
- _tcstoimax
- strtoimax
- _wcstoimax_l
- _strtoimax_l
- _tcstoimax_l
helpviewer_keywords:
- strtoimax funciton
- conversion functions
- _strtoimax_l function
- _wcstoimax_l function
- wcstoimax function
ms.assetid: 4530d3dc-aaac-4a76-b7cf-29ae3c98d0ae
ms.openlocfilehash: e0a320f90b2c0f8653109a6ae0056c4c0cdd7455
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176293"
---
# <a name="strtoimax-strtoimaxl-wcstoimax-wcstoimaxl"></a>strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l

문자열을 지원되는 가장 큰 부호 있는 정수 형식의 정수값으로 변환합니다.

## <a name="syntax"></a>구문

```C
intmax_t strtoimax(
   const char *strSource,
   char **endptr,
   int base
);
intmax_t wcstoimax(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
intmax_t _strtoimax_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
intmax_t _wcstoimax_l(
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

**strtoimax** 문자열에 표시 되는 값을 반환 *strSource*, 표현 인해 오버플로가 발생 경우를 제외 하 고-이 경우 반환 **INTMAX_MAX** 또는 **INTMAX_MIN**, 및 **errno** 로 설정 되어 **ERANGE**합니다. 변환을 수행할 수 없으면 이 함수는 0을 반환합니다. **wcstoimax** 와 동일한 값을 반환 **strtoimax**합니다.

**INTMAX_MAX** 하 고 **INTMAX_MIN** stdint.h에서 정의 됩니다.

경우 *strSource* 됩니다 **NULL** 또는 *기본* 0이 아닌 한 중 2 보다 작거나 36 보다 크면 **errno** 로 설정 된 **EINVAL** .

반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

합니다 **strtoimax** 변환 함수 *strSource* 하는 **intmax_t**합니다. 와이드 문자 버전의 **strtoimax** 됩니다 **wcstoimax**; 해당 *strSource* 인수는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 동작합니다. 두 함수 모두 문자열 읽기를 중지 *strSource* 숫자의 일부분으로 인식할 수 없는 첫 문자에서 합니다. 종결 null 문자를 수 있습니다 또는 보다 크거나 같은 경우에 첫 번째 숫자 문자일 수도 *기본*입니다.

로캘의 **LC_NUMERIC** 범주 설정의 기 수 문자 인식이 결정 *strSource*; 자세한 내용은 참조 하십시오 [setlocale, _wsetlocale](setlocale-wsetlocale.md)합니다. 없는 함수는 **_l** 접미사는 현재 로캘을 사용 **_strtoimax_l** 하 고 **_wcstoimax_l** 없는 해당 함수와 동일 합니다 **_l** 로캘을 대신 사용 한다는 점을 제외 하면 접미사가 에 전달 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

하는 경우 *endptr* 아닙니다 **NULL**, 검색을 중지 한 문자에 대 한 포인터에서 가리키는 위치에 저장 됩니다 *endptr*합니다. 변환 작업 없이 수행할 수 있으면 (올바른 숫자를 찾을 수 없거나 잘못 된 자료를 지정 된), 값 *strSource* 이 가리키는 위치에 저장 됩니다 *endptr*합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoimax**|**strtoimax**|**strtoimax**|**wcstoimax**|
|**_tcstoimax_l**|**strtoimax_l**|**_strtoimax_l**|**_wcstoimax_l**|

**strtoimax** 예상 *strSource* 다음 형식의 문자열을 가리키도록 합니다.

> [*공백을*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*자릿수* &#124; *문자*]  

A *공백* 공백 및 탭 문자가 무시 되는 구성 될 수 있습니다 *자릿수* 는 하나 이상의 10 진수입니다. *문자* 가 문자의 하나 이상의 'a'-'z' (또는 'A' ~ 'Z'). 이 형식에 맞지 않는 첫 번째 문자가 발견되면 검색이 중지됩니다. 하는 경우 *기본* 2와 36 사이의 인 숫자의 밑으로 사용 됩니다. 하는 경우 *기본* 은 0에서 가리키는 문자열의 초기 문자 *strSource* 밑을 결정 하는 데 사용 됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'가 아니면 문자열은 8진수 정수로 해석됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'이면 문자열은 16진수 정수로 해석됩니다. 첫 번째 문자가 '1'~'9' 이면 문자열은 10진수 정수로 해석됩니다. 문자 'a'~'z' 또는 'A'~'Z'에는 값 10~35가 할당됩니다. 할당된 값이 *밑*보다 작은 문자만 사용할 수 있습니다. 밑의 범위를 벗어난 첫 번째 문자가 발견되면 검색이 중지됩니다. 예를 들어 있으면 *기본* 0 및 처음 검색 된 문자가 '0'은는 8 진수 정수로 간주 되며 '8' 또는 '9' 문자가 중지 됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strtoimax**, **_strtoimax_l**, **wcstoimax**, **_wcstoimax_l**|\<inttypes.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l](strtoumax-strtoumax-l-wcstoumax-wcstoumax-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
