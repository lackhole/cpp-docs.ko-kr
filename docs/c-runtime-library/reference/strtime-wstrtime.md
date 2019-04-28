---
title: _strtime, _wstrtime
ms.date: 11/04/2016
apiname:
- _wstrtime
- _strtime
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
- _wstrtime
- _strtime
- wstrtime
- strtime
- _tstrtime
helpviewer_keywords:
- strtime function
- _strtime function
- _wstrtime function
- copying time to buffers
- wstrtime function
- tstrtime function
- _tstrtime function
- time, copying
ms.assetid: 9e538161-cf49-44ec-bca5-c0ab0b9e4ca3
ms.openlocfilehash: 9d874321418854a703886eb80ee23ac1cba57fa4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223097"
---
# <a name="strtime-wstrtime"></a>_strtime, _wstrtime

버퍼에 시간을 복사합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_strtime_s, _wstrtime_s](strtime-s-wstrtime-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *_strtime(
   char *timestr
);
wchar_t *_wstrtime(
   wchar_t *timestr
);
template <size_t size>
char *_strtime(
   char (&timestr)[size]
); // C++ only
template <size_t size>
wchar_t *_wstrtime(
   wchar_t (&timestr)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*timestr*<br/>
시간 문자열입니다.

## <a name="return-value"></a>반환 값

결과 문자열에 대 한 포인터를 반환 *timestr*합니다.

## <a name="remarks"></a>설명

합니다 **_strtime** 함수는 현재 현지 시간에서 가리키는 버퍼에 복사 *timestr*합니다. 시간 형식은 **hh: mm:** 여기서 **hh** 는 24 시간 표기법의 시간을 나타내는 두 자리 숫자로 **mm** 는 시간과 분을나타내는두자리숫자**ss** 두 자리 초를 나타내는입니다. 예를 들어, 문자열 **18시 23분: 44** 23 분 44 초 오후 6 시를 나타냅니다. 버퍼는 9바이트 이상이어야 합니다.

**_wstrtime** 의 와이드 문자 버전이 **_strtime**;의 인수와 반환 값 **_wstrtime** 는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다. 경우 *timestr* 되는 **NULL** 포인터 이거나 *timestr* 는 형식이 잘못 된에 설명 된 대로 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 예외 계속 하도록 허용 된 경우 이러한 함수는 반환을 **NULL** 설정 **errno** 에 **EINVAL** 경우 *timestr* 되었습니다를 **NULL** 설정할지 **errno** 하 **ERANGE** 하는 경우 *timestr* 형식이 잘못 되었습니다.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime**|**_strtime**|**_strtime**|**_wstrtime**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_strtime**|\<time.h>|
|**_wstrtime**|\<time.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strtime.c
// compile with: /W3

#include <time.h>
#include <stdio.h>

int main( void )
{
   char tbuffer [9];
   _strtime( tbuffer ); // C4996
   // Note: _strtime is deprecated; consider using _strtime_s instead
   printf( "The current time is %s \n", tbuffer );
}
```

```Output
The current time is 14:21:44
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
