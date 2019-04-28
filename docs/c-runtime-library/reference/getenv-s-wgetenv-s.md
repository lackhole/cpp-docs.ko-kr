---
title: getenv_s, _wgetenv_s
ms.date: 11/04/2016
apiname:
- getenv_s
- _wgetenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- getenv_s
- _tgetenv_s
- _wgetenv_s
helpviewer_keywords:
- _tgetenv_s function
- wgetenv_s function
- _wgetenv_s function
- getenv_s function
- environment variables
- tgetenv_s function
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
ms.openlocfilehash: eac3c036e2f4f271c7bc2d77c8ae82bec28d3617
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331742"
---
# <a name="getenvs-wgetenvs"></a>getenv_s, _wgetenv_s

현재 환경에서 값을 가져옵니다. 이러한 버전의 [getenv, _wgetenv](getenv-wgetenv.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t getenv_s(
   size_t *pReturnValue,
   char* buffer,
   size_t numberOfElements,
   const char *varname
);
errno_t _wgetenv_s(
   size_t *pReturnValue,
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *varname
);
template <size_t size>
errno_t getenv_s(
   size_t *pReturnValue,
   char (&buffer)[size],
   const char *varname
); // C++ only
template <size_t size>
errno_t _wgetenv_s(
   size_t *pReturnValue,
   wchar_t (&buffer)[size],
   const wchar_t *varname
); // C++ only
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
필요한 버퍼 크기이거나, 변수가 없으면 0입니다.

*buffer*<br/>
환경 변수의 값을 저장할 버퍼입니다.

*numberOfElements*<br/>
크기인 *버퍼*합니다.

*varname*<br/>
환경 변수 이름입니다.

## <a name="return-value"></a>반환 값

성공하면 0이고, 그렇지 않으면 실패 시 오류 코드입니다.

### <a name="error-conditions"></a>오류 조건

|*pReturnValue*|*buffer*|*numberOfElements*|*varname*|반환 값|
|--------------------|--------------|------------------------|---------------|------------------|
|**NULL**|any|any|any|**EINVAL**|
|any|**NULL**|>0|any|**EINVAL**|
|any|any|any|**NULL**|**EINVAL**|

이들 오류 조건은 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행은 계속 하도록 허용 하는 경우 함수를 설정 **errno** 하 **EINVAL** 돌아와 **EINVAL**합니다.

또한 버퍼가 너무 작은 경우 이러한 함수는 반환 **ERANGE**합니다. 잘못된 매개 변수 처리기를 호출하지 않습니다. 필요한 버퍼 크기를 작성 *pReturnValue*, 하므로 더 큰 버퍼를 사용 하 여 다시 함수를 호출 하는 프로그램을 사용 하도록 설정 합니다.

## <a name="remarks"></a>설명

합니다 **getenv_s** 함수에 대 한 환경 변수 목록을 검색 *varname*합니다. **getenv_s** 대/소문자가 Windows 운영 체제에서. **getenv_s** 하 고 [_putenv_s](putenv-s-wputenv-s.md) 전역 변수가 가리키는 환경의 복사본을 사용 하 여 **_environ** 환경에 액세스 합니다. **getenv_s** 환경 "세그먼트" 운영 체제에서 프로세스에 대해 만든 아니라 런타임 라이브러리에 액세스할 수 있는 데이터 구조 에서만 작동 합니다. 따라서 사용 하는 프로그램을 *envp* 인수를 [주](../../cpp/main-program-startup.md) 하거나 [wmain](../../cpp/main-program-startup.md) 잘못 된 정보를 검색할 수 있습니다.

**_wgetenv_s** 의 와이드 문자 버전이 **getenv_s**;의 인수와 반환 값 **_wgetenv_s** 는 와이드 문자 문자열입니다. 합니다 **_wenviron** 전역 변수는 와이드 문자 버전입니다 **_environ**합니다.

MBCS 프로그램 (예를 들어: SBCS ASCII 프로그램)에서 **_wenviron** 처음에 **NULL** 환경이 멀티 바이트 문자열로 구성 되기 때문입니다. 그런 다음 첫 번째 호출은 [_wputenv](putenv-wputenv.md), 또는 첫 번째 호출은 **_wgetenv_s**, (MBCS) 환경이 이미 있는 경우 해당 와이드 문자 문자열 환경이 만들어지고 여 가리킵니다 **_wenviron**합니다.

마찬가지로 유니코드에서 (**_wmain**) 프로그램인 **_environ** 처음에 **NULL** 환경이 와이드 문자열로 구성 되기 때문입니다. 그런 다음 첫 번째 호출은 [_putenv](putenv-wputenv.md), 또는 첫 번째 호출은 **getenv_s** (유니코드) 환경이 이미 있는 경우 해당 MBCS 환경이 만들어지고 여 가리킵니다 **_ environ**합니다.

환경의 두 개의 복사본(MBCS 및 유니코드)이 프로그램에 동시에 존재하는 경우 런타임 시스템은 두 복사본을 모두 유지해야 하며 이로 인해 실행 시간이 늦어집니다. 예를 들어, 호출 하는 경우 **_putenv**에 대 한 호출 **_wputenv** 두 환경 문자열이 일치 되도록 자동으로 실행 됩니다.

> [!CAUTION]
> 드문 경우지만, 런타임 시스템이 유니코드 버전과 멀티바이트 버전의 환경을 모두 유지할 때 두 환경 버전이 정확히 일치하지 않을 수도 있습니다. 이는 고유한 멀티바이트 문자열이 고유한 유지코드 문자열에 매핑되지만 고유 유니코드 문자열에서 멀티바이트 문자열로 매핑이 반드시 고유하지는 않기 때문에 발생합니다. 자세한 내용은 [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md)을 참조하세요.

> [!NOTE]
> 합니다 **_putenv_s** 하 고 **_getenv_s** 함수 패밀리는 스레드로부터 안전 하지 않습니다. **_getenv_s** 하는 동안 문자열 포인터를 반환할 수 있습니다 **_putenv_s** 가 문자열을 수정 하 고 있으므로 임의의 오류를 발생 합니다. 이러한 함수에 대한 호출은 동기화해야 합니다.

C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 보다 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv_s**|**getenv_s**|**getenv_s**|**_wgetenv_s**|

확인의 값을 변경 하는 **TZ** 환경 변수를 사용 하 여 **getenv_s**를 **_putenv**, 및 **_tzset**필요에 따라 합니다. 에 대 한 자세한 내용은 **TZ**를 참조 하세요 [_tzset](tzset.md) 하 고 [_daylight, _dstbias, _timezone 및 _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**getenv_s**|\<stdlib.h>|
|**_wgetenv_s**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_getenv_s.c
// This program uses getenv_s to retrieve
// the LIB environment variable and then uses
// _putenv to change it to a new value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char* libvar;
   size_t requiredSize;

   getenv_s( &requiredSize, NULL, 0, "LIB");
   if (requiredSize == 0)
   {
      printf("LIB doesn't exist!\n");
      exit(1);
   }

   libvar = (char*) malloc(requiredSize * sizeof(char));
   if (!libvar)
   {
      printf("Failed to allocate memory!\n");
      exit(1);
   }

   // Get the value of the LIB environment variable.
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );

   printf( "Original LIB variable is: %s\n", libvar );

   // Attempt to change path. Note that this only affects
   // the environment variable of the current process. The command
   // processor's environment is not changed.
   _putenv_s( "LIB", "c:\\mylib;c:\\yourlib" );

   getenv_s( &requiredSize, NULL, 0, "LIB");

   libvar = (char*) realloc(libvar, requiredSize * sizeof(char));
   if (!libvar)
   {
      printf("Failed to allocate memory!\n");
      exit(1);
   }

   // Get the new value of the LIB environment variable.
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );

   printf( "New LIB variable is: %s\n", libvar );

   free(libvar);
}
```

```Output
Original LIB variable is: c:\vctools\lib;c:\vctools\atlmfc\lib;c:\vctools\PlatformSDK\lib;c:\vctools\Visual Studio SDKs\DIA Sdk\lib;c:\vctools\Visual Studio SDKs\BSC Sdk\lib
New LIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[환경 상수](../../c-runtime-library/environmental-constants.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md)<br/>
