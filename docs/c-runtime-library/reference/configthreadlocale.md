---
title: _configthreadlocale
ms.date: 11/04/2016
api_name:
- _configthreadlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: aac0d36654a81e5d616ffff28e5a254fe06628a3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939018"
---
# <a name="_configthreadlocale"></a>_configthreadlocale

스레드별 로캘 옵션을 구성합니다.

## <a name="syntax"></a>구문

```C
int _configthreadlocale( int per_thread_locale_type );
```

### <a name="parameters"></a>매개 변수

*per_thread_locale_type*<br/>
설정할 옵션입니다. 다음 표에 나열된 옵션 중 하나입니다.

## <a name="return-value"></a>반환 값

이전 스레드별 로캘 상태 (_Disable_per_thread_ststst_st_stn_st_st_stn_st_stn_st_st_l **) 또는**실패 한 경우-1입니다.

## <a name="remarks"></a>설명

**_Configurethreadlocale** 함수는 스레드 관련 로캘의 사용을 제어 하는 데 사용 됩니다. 다음 *per_thread_locale_type* 옵션 중 하나를 사용 하 여 스레드별 로캘 상태를 지정 하거나 결정 합니다.

| 옵션 | Description |
|-|-|
| **_ENABLE_PER_THREAD_LOCALE** | 현재 스레드에서 스레드 관련 로캘을 사용하도록 합니다. 이 스레드에서 **setlocale** 에 대 한 후속 호출은 스레드의 자체 로캘로만 영향을 줍니다. |
| **_DISABLE_PER_THREAD_LOCALE** | 현재 스레드에서 전역 로캘을 사용하도록 합니다. 이 스레드에서 **setlocale** 에 대 한 후속 호출은 전역 로캘을 사용 하는 다른 스레드에 영향을 줍니다. |
| **0** | 이 특정 스레드에 대한 현재 설정을 검색합니다. |

이러한 함수는 **setlocale**, **_tsetlocale**, **_wsetlocale**및 **_setmbcp**의 동작에 영향을 줍니다. 스레드 단위 로캘을 사용 하지 않도록 설정한 경우에는 **setlocale** 또는 **_wsetlocale** 에 대 한 후속 호출에서 전역 로캘을 사용 하는 모든 스레드의 로캘을 변경 합니다. 스레드 단위 로캘을 사용 하는 경우 **setlocale** 또는 **_wsetlocale** 은 현재 스레드의 로캘로만 영향을 줍니다.

**_Configurethreadlocale** 를 사용 하 여 스레드별 로캘을 사용 하도록 설정 하는 경우 **setlocale** 또는 **_wsetlocale** 을 호출 하 여 즉시 해당 스레드에서 기본 설정 로캘을 설정 하는 것이 좋습니다.

*Per_thread_locale_type* 가 테이블에 나열 된 값 중 하나가 아닌 경우이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 합니다. 계속 해 서 실행 하도록 허용한 경우이 함수는 **errno** 를 **EINVAL** 로 설정 하 고-1을 반환 합니다.

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
