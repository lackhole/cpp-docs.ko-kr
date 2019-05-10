---
title: _configthreadlocale
ms.date: 11/04/2016
apiname:
- _configthreadlocale
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
- _configthreadlocale
- configthreadlocale
helpviewer_keywords:
- configthreadlocale function
- locales, per-thread
- _configthreadlocale function
- per-thread locale
- thread locale
ms.assetid: 10e4050e-b587-4f30-80bc-6c76b35fc770
ms.openlocfilehash: 99e10a0330ba4880ea181e9fe3d56f3fb6bd6493
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340263"
---
# <a name="configthreadlocale"></a>_configthreadlocale

스레드별 로캘 옵션을 구성합니다.

## <a name="syntax"></a>구문

```C
int _configthreadlocale( int per_thread_locale_type );
```

### <a name="parameters"></a>매개 변수

*per_thread_locale_type*<br/>
설정할 옵션입니다. 다음 표에 나열된 옵션 중 하나입니다.

## <a name="return-value"></a>반환 값

이전 per-thread locale 상태 (**_DISABLE_PER_THREAD_LOCALE** 하거나 **_ENABLE_PER_THREAD_LOCALE**), 실패 시-1을 반환 합니다.

## <a name="remarks"></a>설명

합니다 **_configurethreadlocale** 함수 스레드 관련 로캘 사용을 제어를 사용 합니다. 다음 중 하나를 사용 하 여 *per_thread_locale_type* 옵션을 지정 하거나 per-thread locale 상태를 확인 합니다.

| 옵션 | 설명 |
|-|-|
| **_ENABLE_PER_THREAD_LOCALE** | 현재 스레드에서 스레드 관련 로캘을 사용하도록 합니다. 에 대 한 후속 호출 **setlocale** 이 스레드의 스레드 자체의 로캘에 영향을 줍니다. |
| **_DISABLE_PER_THREAD_LOCALE** | 현재 스레드에서 전역 로캘을 사용하도록 합니다. 에 대 한 후속 호출 **setlocale** 이 스레드에서 전역 로캘을 사용 하 여 다른 스레드에 영향을 줍니다. |
| **0** | 이 특정 스레드에 대한 현재 설정을 검색합니다. |

이러한 함수 동작에 영향을 줄 **setlocale**를 **_tsetlocale**를 **_wsetlocale**, 및 **_setmbcp**합니다. 스레드별 로캘은 경우 사용 안 함, 모든 후속 호출 **setlocale** 하거나 **_wsetlocale** 전역 로캘을 사용 하는 모든 스레드의 로캘을 변경 합니다. 스레드별 로캘을 사용 하는 경우 **setlocale** 하거나 **_wsetlocale** 만 현재 스레드의 로캘에 영향을 줍니다.

사용 하는 경우 **_configurethreadlocale** 스레드별 로캘을 사용할 수 있도록를 호출 하는 권장 **setlocale** 하거나 **_wsetlocale** 스레드에서 원하는 로캘을 설정 하려면 바로 다음에 있습니다.

하는 경우 *per_thread_locale_type* 값 중 하나가 아닌 표에 나열 된,이 함수는 잘못 된 매개 변수 처리기를 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우는 계속 실행 하도록 허용 합니다 **errno** 하 **EINVAL** -1을 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_configthreadlocale**|\<locale.h>|

## <a name="example"></a>예제

```cpp
// crt_configthreadlocale.cpp
//
// This program demonstrates the use of _configthreadlocale when
// using two independent threads.
//
// Compile by using: cl /EHsc /W4 crt_configthreadlocale.cpp

#include <locale.h>
#include <mbctype.h>
#include <process.h>
#include <windows.h>
#include <stdio.h>
#include <time.h>

#define BUFF_SIZE 100

// Retrieve the date and time in the current
// locale's format.
int get_time(unsigned char* str)
{
    __time64_t  ltime;
    struct tm   thetime;

    // Retieve the time
    _time64(&ltime);
    _gmtime64_s(&thetime, &ltime);

    // Format the current time structure into a string
    // using %#x is the long date representation,
    // appropriate to the current locale
    if (!strftime((char *)str, BUFF_SIZE, "%#x",
                  (const struct tm*)&thetime))
    {
        printf("strftime failed!\n");
        return -1;
    }
    return 0;
}

// This thread sets its locale to German
// and prints the time.
unsigned __stdcall SecondThreadFunc( void* /*pArguments*/ )
{
    unsigned char str[BUFF_SIZE];

    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Set the thread code page
    _setmbcp(_MB_CP_ANSI);

    // Set the thread locale
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "German"));

    // Retrieve the time string from the helper function
    if (get_time(str) == 0)
    {
        printf("The time in German locale is: '%s'\n", str);
    }

    _endthreadex( 0 );
    return 0;
}

// The main thread spawns a second thread (above) and then
// sets the locale to English and prints the time.
int main()
{
    HANDLE          hThread;
    unsigned        threadID;
    unsigned char   str[BUFF_SIZE];

    // Enable per-thread locale causes all subsequent locale
    // setting changes in this thread to only affect this thread.
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Retrieve the time string from the helper function
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "English"));

    // Create the second thread.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,
                                      NULL, 0, &threadID );

    if (get_time(str) == 0)
    {
        // Retrieve the time string from the helper function
        printf("The time in English locale is: '%s'\n\n", str);
    }

    // Wait for the created thread to finish.
    WaitForSingleObject( hThread, INFINITE );

    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
The thread locale is now set to English_United States.1252.
The time in English locale is: 'Wednesday, May 12, 2004'

The thread locale is now set to German_Germany.1252.
The time in German locale is: 'Mittwoch, 12. Mai 2004'
```

## <a name="see-also"></a>참고자료

[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 스레딩 및 로캘](../../parallel/multithreading-and-locales.md)<br/>
