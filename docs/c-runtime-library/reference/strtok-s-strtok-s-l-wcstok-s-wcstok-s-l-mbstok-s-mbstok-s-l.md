---
title: strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l
ms.date: 03/25/2019
apiname:
- _wcstok_s_l
- _mbstok_s_l
- _mbstok_s
- strtok_s
- wcstok_s
- _strtok_s_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _tcstok_s_l
- _wcstok_s_l
- _tcstok_s
- _mbstok_s_l
- strtok_s
- wcstok_s
- _mbstok_s
- _strtok_s_l
helpviewer_keywords:
- _strtok_s_l function
- _mbstok_s_l function
- strings [C++], searching
- mbstok_s_l function
- wcstok_s_l function
- _wcstok_s_l function
- _tcstok_s function
- _tcstok_s_l function
- strtok_s_l function
- wcstok_s function
- tokens, finding in strings
- mbstok_s function
- _mbstok_s function
- strtok_s function
ms.assetid: 7696c972-f83b-4617-8c82-95973e9fdb46
ms.openlocfilehash: e2c237927aa133d33085be40b88789c1024d6b34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176202"
---
# <a name="strtoks-strtoksl-wcstoks-wcstoksl-mbstoks-mbstoksl"></a>strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l

현재 로캘 또는 전달된 로캘을 사용하여 문자열의 다음 토큰을 찾습니다. 이러한 버전의 [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 향상된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> **_mbstok_s** 하 고 **_mbstok_s_l** Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char* strtok_s(
   char* str,
   const char* delimiters,
   char** context
);

char* _strtok_s_l(
   char* str,
   const char* delimiters,
   char** context,
   _locale_t locale
);

wchar_t* wcstok_s(
   wchar_t* str,
   const wchar_t* delimiters,
   wchar_t** context
);

wchar_t *_wcstok_s_l(
   wchar_t* str,
   const wchar_t* delimiters,
   wchar_t** context,
   _locale_t locale
);

unsigned char* _mbstok_s(
   unsigned char* str,
   const unsigned char* delimiters,
   char** context
);

unsigned char* _mbstok_s_l(
   unsigned char* str,
   const unsigned char* delimiters,
   char** context,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
찾으려는 토큰을 포함 하는 문자열입니다.

*delimiters*<br/>
사용할 구분 기호 문자 집합이 있습니다.

*context*<br/>
함수 호출 간의 위치 정보를 저장 하는 데 사용 합니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

다음 토큰에 대 한 포인터를 반환 *str*합니다. 반환 **NULL** 더 이상 토큰이 검색 되 면 합니다. 각 호출을 수정 *str* 반환된 된 토큰 뒤에 오는 첫 번째 구분 기호에 대 한 null 문자를 대체 하 여 합니다.

### <a name="error-conditions"></a>오류 조건

|*str*|*delimiters*|*context*|반환 값|**errno**|
|----------------|------------------|---------------|------------------|-------------|
|**NULL**|any|null 포인터에 대한 포인터|**NULL**|**EINVAL**|
|any|**NULL**|any|**NULL**|**EINVAL**|
|any|any|**NULL**|**NULL**|**EINVAL**|

경우 *str* 는 **NULL** 하지만 *상황에 맞는* 포인터가를 유효한 컨텍스트 포인터에 오류가 나타나지 않습니다.

## <a name="remarks"></a>설명

합니다 **strtok_s** 패밀리 함수에서 다음 토큰을 찾습니다 *str*합니다. 문자 집합이 *구분 기호* 에서 찾을 토큰의 사용 가능한 구분 기호를 지정 *str* 현재 호출 합니다. **wcstok_s** 하 고 **_mbstok_s** 와이드 문자 및 멀티 바이트 문자 버전입니다 **strtok_s**합니다. 인수 및 반환 값 **wcstok_s** 하 고 **_wcstok_s_l** 은 와이드 문자열이 고 **_mbstok_s** 고 **_mbstok_s_l**은 멀티 바이트 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 오류 조건 표에 같이 오류 조건이 발생할 때 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 돌아와 **NULL**합니다.

첫 번째 호출에서 **strtok_s**, 함수는 선행 구분 기호를 건너뛰고 및 첫 번째 토큰에 대 한 포인터를 반환 합니다. *str*, null 문자로 토큰을 종료 합니다. 더 많은 토큰의 나머지 부분으로 분할할 수 있습니다 *str* 일련의 호출에 의해 **strtok_s**합니다. 호출할 때마다 **strtok_s** 수정 *str* 해당 호출에서 반환 된 후 null 문자를 삽입 하 여 합니다. 합니다 *상황에 맞는* 포인터는 추적 문자열 읽고 있는 문자열의 다음 토큰은 읽을 수 있습니다. 다음 토큰을 읽어올 *str*, 호출 **strtok_s** 사용 하 여를 **NULL** 에 대 한 값을 *str* 인수를 동일한 전달  *상황에 맞는* 매개 변수입니다. 합니다 **NULL** *str* 인수를 사용 하면 **strtok_s** 에서 수정 된 다음 토큰을 검색할 *str*합니다. 합니다 *구분 기호* 인수 구분 기호 집합이 달라질 수 있도록 다음에 대 한 호출에서 값을 사용할 수 있습니다.

이후 합니다 *상황에 맞는* 매개 변수 대체에 사용 되는 정적 버퍼 **strtok** 및 **_strtok_l**, 동일한 스레드에서 동시에 두 개의 문자열을 구문 분석할 수 있습니다.

출력 값의 설정이 적용 됩니다는 **LC_CTYPE** 로캘 범주 설정 합니다. 자세한 내용은 [setlocale](setlocale-wsetlocale.md)을 참조하세요.

없는 이러한 함수의 버전은 **_l** 접미사가 로캘 종속 동작에 대 한 현재 스레드의 로캘을 사용 합니다. 있는 버전의 **_l** 접미사는 동일 하 여 지정 된 로캘을 대신 사용 한다는 점을 제외 하 고는 *로캘* 매개 변수입니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**strtok_s**|\<string.h>|
|**_strtok_s_l**|\<string.h>|
|**wcstok_s**,<br />**_wcstok_s_l**|\<string.h> 또는 \<wchar.h>|
|**_mbstok_s**,<br />**_mbstok_s_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|\_유니코드 & \_MBCS 정의 되지 않았습니다|\_MBCS 정의|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstok_s**|**strtok_s**|**_mbstok_s**|**wcstok_s**|
|**_tcstok_s_l**|**_strtok_s_l**|**_mbstok_s_l**|**_wcstok_s_l**|

## <a name="example"></a>예제

```C
// crt_strtok_s.c
// In this program, a loop uses strtok_s
// to print all the tokens (separated by commas
// or blanks) in two strings at the same time.

#include <string.h>
#include <stdio.h>

char string1[] =
    "A string\tof ,,tokens\nand some  more tokens";
char string2[] =
    "Another string\n\tparsed at the same time.";
char seps[]   = " ,\t\n";
char *token1 = NULL;
char *token2 = NULL;
char *next_token1 = NULL;
char *next_token2 = NULL;

int main(void)
{
    printf("Tokens:\n");

    // Establish string and get the first token:
    token1 = strtok_s(string1, seps, &next_token1);
    token2 = strtok_s(string2, seps, &next_token2);

    // While there are tokens in "string1" or "string2"
    while ((token1 != NULL) || (token2 != NULL))
    {
        // Get next token:
        if (token1 != NULL)
        {
            printf(" %s\n", token1);
            token1 = strtok_s(NULL, seps, &next_token1);
        }
        if (token2 != NULL)
        {
            printf("        %s\n", token2);
            token2 = strtok_s(NULL, seps, &next_token2);
        }
    }
}
```

```Output
Tokens:
A
        Another
string
        string
of
        parsed
tokens
        at
and
        the
some
        same
more
        time.
tokens
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
