---
title: _strdate, _wstrdate
ms.date: 11/04/2016
apiname:
- _strdate
- _wstrdate
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
- _tstrdate
- wstrdate
- _wstrdate
- _strdate
- strdate
helpviewer_keywords:
- strdate function
- dates, copying
- tstrdate function
- _wstrdate function
- wstrdate function
- _strdate function
- _tstrdate function
- copying dates
ms.assetid: de8e4097-58f8-42ba-9dcd-cb4d9a9f1696
ms.openlocfilehash: 4dc2ea7f25e644c9bf7a4ddca4a625991f37d912
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353965"
---
# <a name="strdate-wstrdate"></a>_strdate, _wstrdate

현재 시스템 날짜를 버퍼에 복사합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_strdate_s, _wstrdate_s](strdate-s-wstrdate-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_strdate(
   char *datestr
);
wchar_t *_wstrdate(
   wchar_t *datestr
);
template <size_t size>
char *_strdate(
   char (&datestr)[size]
); // C++ only
template <size_t size>
wchar_t *_wstrdate(
   wchar_t (&datestr)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*datestr*<br/>
형식이 지정된 날짜 문자열을 포함하는 버퍼에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

이러한 각 함수는 결과 문자열에 대 한 포인터를 반환 *datestr*합니다.

## <a name="remarks"></a>설명

이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_strdate_s, _wstrdate_s](strdate-s-wstrdate-s.md)를 참조하세요. 가능한 경우에는 항상 더 안전한 함수를 사용하는 것이 좋습니다.

합니다 **_strdate** 함수는 현재 시스템 날짜를 가리키는 버퍼에 복사 *datestr*서식을 **mm**/**dd** / **yy**여기서 **mm** 는 월을 나타내는 두 자리 숫자로 **dd** 는 일을 나타내는 두 자리 숫자로 및 **yy**  연도의 마지막 두 자리 됩니다. 예를 들어, 문자열 **9905/12/** 1999 년 12 월 5 일을 나타냅니다. 버퍼는 9바이트 이상이어야 합니다.

하는 경우 *datestr* 되는 **NULL** 에 설명 된 대로 포인터인 경우 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수가-1를 반환 하는 설정 **errno** 하 **EINVAL**합니다.

**_wstrdate** 의 와이드 문자 버전이 **_strdate**;의 인수와 반환 값 **_wstrdate** 는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate**|**_strdate**|**_strdate**|**_wstrdate**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_strdate**|\<time.h>|
|**_wstrdate**|\<time.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// strdate.c
// compile with: /W3
#include <time.h>
#include <stdio.h>
int main()
{
    char tmpbuf[9];

    // Set time zone from TZ environment variable. If TZ is not set,
    // the operating system is queried to obtain the default value
    // for the variable.
    //
    _tzset();

    printf( "OS date: %s\n", _strdate(tmpbuf) ); // C4996
    // Note: _strdate is deprecated; consider using _strdate_s instead
}
```

```Output
OS date: 04/25/03
```

## <a name="see-also"></a>참고자료

[시간 관리](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
