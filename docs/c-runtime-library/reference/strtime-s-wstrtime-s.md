---
title: _strtime_s, _wstrtime_s
ms.date: 11/04/2016
apiname:
- _wstrtime_s
- _strtime_s
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
- _wstrtime_s
- strtime_s
- wstrtime_s
- _strtime_s
helpviewer_keywords:
- wstrtime_s function
- copying time to buffers
- strtime_s function
- _wstrtime_s function
- time, copying
- _strtime_s function
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
ms.openlocfilehash: 579c4a99b52c66bd14cea947eaa1f301cc1127e1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375329"
---
# <a name="strtimes-wstrtimes"></a>_strtime_s, _wstrtime_s

버퍼에 현재 시간을 복사합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_strtime, _wstrtime](strtime-wstrtime.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _strtime_s(
   char *buffer,
   size_t numberOfElements
);
errno_t _wstrtime_s(
   wchar_t *buffer,
   size_t numberOfElements
);
template <size_t size>
errno_t _strtime_s(
   char (&buffer)[size]
); // C++ only
template <size_t size>
errno_t _wstrtime_s(
   wchar_t (&buffer)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
시간을 쓸 버퍼(10바이트 이상)입니다.

*numberOfElements*<br/>
버퍼의 크기입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되는 경우 0입니다.

오류 조건이 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 오류가 있을 경우 반환 값은 오류 코드입니다. 오류 코드는 ERRNO.H에 정의됩니다. 이 함수가 생성하는 정확한 오류는 다음 표를 참조하세요. 오류 코드에 대한 자세한 내용은 [errno 상수](../../c-runtime-library/errno-constants.md)를 참조하세요.

### <a name="error-conditions"></a>오류 조건

|*buffer*|*numberOfElements*|반환|내용을 *버퍼*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(임의)|**EINVAL**|수정 안 됨|
|되지 **NULL** (유효한 버퍼를 가리킴)|0|**EINVAL**|수정 안 됨|
|되지 **NULL** (유효한 버퍼를 가리킴)|0 < size < 9|**EINVAL**|빈 문자열|
|되지 **NULL** (유효한 버퍼를 가리킴)|크기 > 9|0|설명에 지정된 형식의 현재 시간|

## <a name="security-issues"></a>보안 문제

잘못 된 전달 이외**NULL** 버퍼 하면 액세스 위반이 발생 하는 경우에 대 한 값을 *numberOfElements* 매개 변수가 9 보다 크면 합니다.

값을 전달 *numberOfElements* 는 보다 크면 버퍼의 실제 크기는 버퍼 오버런이 발생 합니다.

## <a name="remarks"></a>설명

이러한 함수의 더 안전한 버전 제공 [_strtime](strtime-wstrtime.md) 하 고 [_wstrtime](strtime-wstrtime.md)합니다. 합니다 **_strtime_s** 함수는 현재 현지 시간에서 가리키는 버퍼에 복사 *timestr*합니다. 시간 형식은 **hh: mm:** 여기서 **hh** 는 24 시간 표기법의 시간을 나타내는 두 자리 숫자로 **mm** 는 시간과 분을나타내는두자리숫자**ss** 두 자리 초를 나타내는입니다. 예를 들어, 문자열 **18시 23분: 44** 23 분 44 초 오후 6 시를 나타냅니다. 버퍼는 9바이트 이상이어야 합니다. 실제 크기는 두 번째 매개 변수로 지정됩니다.

**_wstrtime** 의 와이드 문자 버전이 **_strtime**;의 인수와 반환 값 **_wstrtime** 는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mapping"></a>제네릭 텍스트 루틴 매핑:

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime_s**|**_strtime_s**|**_strtime_s**|**_wstrtime_s**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_strtime_s**|\<time.h>|
|**_wstrtime_s**|\<time.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// strtime_s.c

#include <time.h>
#include <stdio.h>

int main()
{
    char tmpbuf[9];
    errno_t err;

    // Set time zone from TZ environment variable. If TZ is not set,
    // the operating system is queried to obtain the default value
    // for the variable.
    //
    _tzset();

    // Display operating system-style date and time.
    err = _strtime_s( tmpbuf, 9 );
    if (err)
    {
       printf("_strdate_s failed due to an invalid argument.");
      exit(1);
    }
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );
    err = _strdate_s( tmpbuf, 9 );
    if (err)
    {
       printf("_strdate_s failed due to an invalid argument.");
       exit(1);
    }
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );

}
```

```Output
OS time:            14:37:49
OS date:            04/25/03
```

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
