---
title: setlocale, _wsetlocale
ms.date: 11/04/2016
apiname:
- _wsetlocale
- setlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wsetlocale
- _tsetlocale
- setlocale
helpviewer_keywords:
- wsetlocale function
- setlocale function
- tsetlocale function
- locales, defining
- _tsetlocale function
- defining locales
- _wsetlocale function
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
ms.openlocfilehash: 618b3e58a52e89561439fe76bf1b30e3cbbce001
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356357"
---
# <a name="setlocale-wsetlocale"></a>setlocale, _wsetlocale

런타임 로캘을 설정하거나 가져옵니다.

## <a name="syntax"></a>구문

```C
char *setlocale(
   int category,
   const char *locale
);
wchar_t *_wsetlocale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>매개 변수

*category*<br/>
로캘의 영향을 받는 범주입니다.

*locale*<br/>
로캘 지정자입니다.

## <a name="return-value"></a>반환 값

유효한 경우 *로캘* 하 고 *범주* 된, 지정 된 연결 문자열에 대 한 포인터를 반환 합니다 *로캘* 하 고 *범주*. 경우는 *로캘* 또는 *범주* null 포인터와 프로그램의 현재 로캘 설정은 변경 되지 않습니다 반환에서는 유효 하지 않습니다.

예: 호출

```C
setlocale( LC_ALL, "en-US" );
```

문자열만 반환하는 모든 범주를 설정합니다.

```Output
en-US
```

반환한 문자열을 복사할 수 있습니다 **setlocale** 프로그램 로캘 정보의 일부를 복원할 합니다. 전역 또는 스레드 로컬 저장소에서 반환한 문자열에 사용 됩니다 **setlocale**합니다. 나중에 호출 **setlocale** 이전 호출에서 반환 하는 문자열 포인터를 무효화 하는 문자열을 덮어씁니다.

## <a name="remarks"></a>설명

사용 합니다 **setlocale** 설정, 변경 또는 일부 또는 전부에서 지정한 현재 프로그램 로캘 정보를 쿼리 하는 함수 *로캘* 하 고 *범주*합니다. *로캘* 는 프로그램의 특정 요소를 사용자 지정할 수 있습니다 위치 (국가/지역 및 언어)을 가리킵니다. 일부 로캘 종속 범주에는 날짜 형식 지정 및 통화 값의 형식 표시가 포함됩니다. 설정 하는 경우 *로캘* 컴퓨터에서 지원 되는 여러 폼에 있는 언어에 대 한 기본 문자열을 확인 해야 합니다 **setlocale** 적용 되는 언어 값을 반환 합니다. 예를 들어 설정한 *로캘* 을 "중국어"로 반환 값을 "중국어 간체" 또는 "중국어 번체" 일 수 있습니다.

**_wsetlocale** 의 와이드 문자 버전이 **setlocale**; *로캘* 의 인수와 반환 값 **_wsetlocale** 는 와이드 문자 문자열입니다. **_wsetlocale** 하 고 **setlocale** 동일 하 게 작동 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsetlocale**|**setlocale**|**setlocale**|**_wsetlocale**|

합니다 *범주* 인수 영향을 받는 프로그램 로캘 정보의 일부를 지정 합니다. 에 사용 되는 매크로 *범주* 및 영향을 주는 프로그램의 일부는 다음과 같습니다.

|*범주* 플래그|미치는 영향|
|-|-|
| **LC_ALL** | 아래에 나열된 모든 범주입니다. |
| **LC_COLLATE** | 합니다 **strcoll**, **_stricoll**를 **wcscoll**를 **_wcsicoll**를 **strxfrm**, **_ strncoll**, **_strnicoll**를 **_wcsncoll**를 **_wcsnicoll**, 및 **wcsxfrm** 함수입니다. |
| **LC_CTYPE** | 문자 처리 함수 (제외한 **isdigit**, **isxdigit**를 **mbstowcs**, 및 **mbtowc**, 영향을 받지 않습니다). |
| **LC_MONETARY** | 반환 되는 통화 서식 정보를 **localeconv** 함수입니다. |
| **LC_NUMERIC** | 소수점 문자 형식이 지정 된 출력 루틴 (같은 **printf**), 데이터 변환 루틴 및 반환 하는 비 통화 서식 지정 정보에 대 한 **localeconv**합니다. 소수점 문자 이외에 **LC_NUMERIC** 제어에서 반환 된 문자열 집합 1000 단위 구분 기호 및 그룹화 [localeconv](localeconv.md)합니다. |
| **LC_TIME** | 합니다 **strftime** 하 고 **wcsftime** 함수입니다. |

이 함수는 범주 매개 변수의 유효성을 검사합니다. 범주 매개 변수가 이전 표에 지정된 값 중 하나가 아닌 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 함수를 설정 하는 경우는 계속 실행 하도록 허용 합니다 **errno** 하 **EINVAL** 반환 **NULL**합니다.

합니다 *로캘* 인수는 로캘을 지정 하는 문자열에 대 한 포인터입니다. 형식에 대 한 자세한 합니다 *로캘* 인수를 참조 하십시오 [로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)합니다. *locale*에서 빈 문자열을 가리키면 로캘은 구현에서 정의된 네이티브 환경입니다. 값이 **C** C 번역에 대 한 최소 ANSI 표준에 맞는 환경을 지정 합니다. 합니다 **C** 로캘 가정 **char** 및 해당 값이 항상 256 보다 작은 데이터 형식은 1 바이트입니다.

프로그램을 시작할 때 다음 문을 실행합니다.

`setlocale( LC_ALL, "C" );`

합니다 *로캘* 인수는 로캘 이름, 언어 문자열, 언어 문자열 및 국가/지역 코드, 코드 페이지 또는 언어 문자열, 국가/지역 코드 및 코드 페이지에 사용할 수 있습니다. 사용 가능한 로캘 이름, 언어, 국가/지역 코드 및 코드 페이지의 집합에는 문자당 2바이트 이상을 필요로 하는 코드 페이지를 제외하고, Windows NLS API에서 지원하는 모든 항목이 포함됩니다(예: UTF-7 및 UTF-8). Utf-7 또는 u t F-8로의 코드 페이지 값을 제공 하는 경우 **setlocale** 실패를 반환 **NULL**합니다. 지 원하는 로캘 이름 집합이 **setlocale** 에 설명 되어 있습니다 [로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)합니다. 지 원하는 언어 및 국가/지역 문자열 집합이 **setlocale** 에 나와 [언어 문자열](../../c-runtime-library/language-strings.md) 하 고 [국가/지역 문자열](../../c-runtime-library/country-region-strings.md)합니다. 코드에 포함되거나 스토리지에 직렬화된 로캘 문자열의 성능과 유지 관리를 위해 로캘 이름 형식을 사용하는 것이 좋습니다. 로캘 이름 문자열은 언어와 국가/지역 이름 형식보다 운영 체제 업데이트에 의해 변경될 가능성이 적습니다.

로 전달 되는 null 포인터를 *로캘* 지정 하는 인수 **setlocale** 국제 환경을 설정 하려면 대신 쿼리 합니다. 경우는 *로캘* 인수가 null 포인터 인지, 프로그램의 현재 로캘 설정은 변경 되지 않습니다. 대신 **setlocale** 연관 된 된 문자열에 대 한 포인터를 반환 합니다 *범주* 스레드의 현재 로캘. 경우는 *범주* 인수가 **LC_ALL**, 함수는 세미콜론으로 구분 된 각 범주의 현재 설정을 나타내는 문자열을 반환 합니다. 예: 호출 시퀀스

```C
// Set all categories and return "en-US"
setlocale(LC_ALL, "en-US");
// Set only the LC_MONETARY category and return "fr-FR"
setlocale(LC_MONETARY, "fr-FR");
printf("%s\n", setlocale(LC_ALL, NULL));
```

returns

```Output
LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US
```

연결 된 문자열로 합니다 **LC_ALL** 범주입니다.

다음 예제와 관련 된 **LC_ALL** 범주입니다. 사용자 기본 OEM 코드 페이지 및 사용자 기본 ANSI 코드 페이지의 사용을 각각 지정하기 위해 코드 페이지 번호 대신 ".OCP" 및 ".ACP" 문자열을 사용할 수 있습니다.

- `setlocale( LC_ALL, "" );`

   로캘을 운영 체제에서 가져온 사용자 기본 ANSI 코드 페이지인 기본값으로 설정합니다.

- `setlocale( LC_ALL, ".OCP" );`

   로캘을 운영 체제에서 얻은 현재 OEM 코드 페이지로 명시적으로 설정합니다.

- `setlocale( LC_ALL, ".ACP" );`

   로캘을 운영 체제에서 얻은 ANSI 코드 페이지로 설정합니다.

- `setlocale( LC_ALL, "<localename>" );`

   로캘을 *\<localename>* 에 의해 표시되는 로캘 이름으로 설정합니다.

- `setlocale( LC_ALL, "<language>_<country>" );`

   호스트 운영 체제에서 가져온 기본 코드 페이지와 함께 로캘을 *\<language>* 및 *\<country>* 에 의해 표시되는 언어 및 국가/지역으로 설정합니다.

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   언어, 국가/지역 및 코드 페이지에 로캘을 나타내는 집합을  *\<언어 >* 를  *\<국가 >*, 및  *\<code_page >* 문자열입니다. 언어, 국가/지역 및 코드 페이지의 다양한 조합을 사용할 수 있습니다. 예를 들어, 이 호출은 코드 페이지 1252에 따라 로캘을 프랑스어(캐나다)로 설정합니다.

   `setlocale( LC_ALL, "French_Canada.1252" );`

   이 호출은 기본 ANSI 코드 페이지에 따라 로캘을 프랑스어(캐나다)로 설정합니다.

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   이 호출은 기본 OEM 코드 페이지에 따라 로캘을 프랑스어(캐나다)로 설정합니다.

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   로캘을 *\<language>* 에 의해 표시되는 언어로 설정하고 호스트 운영 체제에서 가져온 대로 지정된 언어 및 사용자 기본 ANSI 코드 페이지와 지정된 언어를 위한 기본 국가/지역을 사용합니다. 다음 호출은 예를 들어 **setlocale** 기능적으로 동일 합니다.

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   성능 및 유지 관리에 첫 번째 폼을 사용하는 것이 좋습니다.

- `setlocale( LC_ALL, ".<code_page>" );`

   지정한 코드 페이지에 대한 기본 국가/지역 및 언어(호스트 운영 체제에 의해 정의됨)와 함께 *<code_page>* 에 의해 표시되는 값으로 코드 페이지를 설정합니다.

범주 중 하나 여야 합니다 **LC_ALL** 하거나 **LC_CTYPE** 를 코드 페이지에 변경 내용을 적용 합니다. 예를 들어 경우 기본 국가/지역 및 호스트 운영 체제의 언어가 "미국" 및 "영어"는 다음 두 호출이 **setlocale** 기능적으로 동일 합니다.

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

자세한 내용은 [C/C++ 전처리기 참조](../../preprocessor/c-cpp-preprocessor-reference.md)에서 [setlocale](../../preprocessor/setlocale.md) pragma 지시문을 참조하세요.

함수 [_configthreadlocale](configthreadlocale.md) 여부를 제어 하 되 **setlocale** 프로그램의 모든 스레드 로캘 또는 호출 스레드의 로캘에 영향을 줍니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**setlocale**|\<locale.h>|
|**_wsetlocale**|\<locale.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_setlocale.c
//
// This program demonstrates the use of setlocale when
// using two independent threads.
//

#include <locale.h>
#include <process.h>
#include <windows.h>
#include <stdio.h>
#include <time.h>

#define BUFF_SIZE 100

// Retrieve the date in the current
// locale's format.
int get_date(unsigned char* str)
{
    __time64_t ltime;
    struct tm  thetime;

    // Retrieve the current time
    _time64(&ltime);
    _gmtime64_s(&thetime, &ltime);

    // Format the current time structure into a string
    // "%#x" is the long date representation in the
    // current locale
    if (!strftime((char *)str, BUFF_SIZE, "%#x",
                  (const struct tm *)&thetime))
    {
        printf("strftime failed!\n");
        return -1;
    }
    return 0;
}

// This thread sets its locale to the argument
// and prints the date.
uintptr_t __stdcall SecondThreadFunc( void* pArguments )
{
    unsigned char str[BUFF_SIZE];
    char * locale = (char *)pArguments;

    // Set the thread locale
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, locale));

    // Retrieve the date string from the helper function
    if (get_date(str) == 0)
    {
        printf("The date in %s locale is: '%s'\n", locale, str);
    }

    _endthreadex( 0 );
    return 0;
}

// The main thread sets the locale to English
// and then spawns a second thread (above) and prints the date.
int main()
{
    HANDLE          hThread;
    unsigned        threadID;
    unsigned char   str[BUFF_SIZE];

    // Enable per-thread locale causes all subsequent locale
    // setting changes in this thread to only affect this thread.
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Set the locale of the main thread to US English.
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "en-US"));

    // Create the second thread with a German locale.
    // Our thread function takes an argument of the locale to use.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,
                                      "de-DE", 0, &threadID );

    if (get_date(str) == 0)
    {
        // Retrieve the date string from the helper function
        printf("The date in en-US locale is: '%s'\n\n", str);
    }

    // Wait for the created thread to finish.
    WaitForSingleObject( hThread, INFINITE );

    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
The thread locale is now set to en-US.
The time in en-US locale is: 'Wednesday, May 12, 2004'

The thread locale is now set to de-DE.
The time in de-DE locale is: 'Mittwoch, 12. Mai 2004'
```

## <a name="see-also"></a>참고자료

[로캘 이름, 언어 및 국가/지역 문자열](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[strcoll 함수](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
