---
title: _searchenv_s, _wsearchenv_s
ms.date: 11/04/2016
apiname:
- _wsearchenv_s
- _searchenv_s
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
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
ms.openlocfilehash: 40c2d0c42a3d61f84db78015388eba19742af06e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356825"
---
# <a name="searchenvs-wsearchenvs"></a>_searchenv_s, _wsearchenv_s

환경 경로를 사용하여 파일을 검색합니다. 이러한 버전의 [_searchenv, _wsearchenv](searchenv-wsearchenv.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char *pathname,
   size_t numberOfElements
);
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t *pathname,
   size_t numberOfElements
);
template <size_t size>
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char (&pathname)[size]
); // C++ only
template <size_t size>
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t (&pathname)[size]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*filename*<br/>
검색할 파일의 이름입니다.

*varname*<br/>
검색할 환경입니다.

*pathname*<br/>
전체 경로를 저장할 버퍼입니다.

*numberOfElements*<br/>
크기를 *pathname* 버퍼입니다.

## <a name="return-value"></a>반환 값

성공 시 0이고, 실패 시 오류 코드입니다.

하는 경우 *filename* 빈 문자열이 면 반환 값은 **ENOENT**합니다.

### <a name="error-conditions"></a>오류 조건

|*filename*|*varname*|*pathname*|*numberOfElements*|반환 값|내용을 *경로 이름*|
|----------------|---------------|----------------|------------------------|------------------|----------------------------|
|any|any|**NULL**|any|**EINVAL**|N/A|
|**NULL**|any|any|any|**EINVAL**|변경되지 않음|
|any|any|any|<= 0|**EINVAL**|변경되지 않음|

이러한 조건 중 하나라도 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 발생합니다. 실행은 계속 하도록 허용 하는 경우 이러한 함수 설정 **errno** 하 **EINVAL** 돌아와 **EINVAL**합니다.

## <a name="remarks"></a>설명

합니다 **_searchenv_s** 루틴은 지정된 된 도메인에 대상 파일을 검색 합니다. 합니다 *varname* 와 같은 디렉터리 경로의 목록을 지정 하는 사용자 정의 변수 나 환경 변수 될 수 있습니다 **경로**를 **LIB**, 및 **포함** . 때문에 **_searchenv_s** 대/소문자 *varname* 환경 변수의 대/소문자와 일치 해야 합니다. 하는 경우 *varname* 프로세스의 환경에서 환경 변수 이름을 정의 하는 일치 하지 않으면, 0을 반환 하는 함수 및 *pathname* 변수는 변경 되지 않습니다.

루틴은 먼저 현재 작업 디렉터리에서 파일을 검색합니다. 파일을 찾을 수 없는 경우 다음 위치로 환경 변수에 지정된 디렉터리를 확인합니다. 새로 만든된 경로에 복사 됩니다 대상 파일이 이러한 디렉터리 중 하나에 있으면 *pathname*합니다. 경우는 *filename* 파일을 찾지 *pathname* 빈 null 종료 문자열을 포함 합니다.

*pathname* 버퍼 이상 이어야 **_max_path(256** 생성 된 경로 이름의 전체 길이 맞게 자입니다. 이 고, 그렇지 **_searchenv_s** 오버런 수 합니다 *pathname* 예기치 않은 동작이 발생 하는 버퍼입니다.

**_wsearchenv_s** 의 와이드 문자 버전이 **_searchenv_s**;에 대 한 인수 **_wsearchenv_s** 는 와이드 문자 문자열입니다. **_wsearchenv_s** 하 고 **_searchenv_s** 동일 하 게 작동 합니다.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv_s**|**_searchenv_s**|**_searchenv_s**|**_wsearchenv_s**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_searchenv_s**|\<stdlib.h>|
|**_wsearchenv_s**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_searchenv_s.c
/* This program searches for a file in
* a directory specified by an environment variable.
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char pathbuffer[_MAX_PATH];
   char searchfile[] = "CL.EXE";
   char envvar[] = "PATH";
   errno_t err;

   /* Search for file in PATH environment variable: */
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );
   if (err != 0)
   {
      printf("Error searching the path. Error code: %d\n", err);
   }
   if( *pathbuffer != '\0' )
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );
   else
      printf( "%s not found\n", searchfile );
}
```

```Output
Path for CL.EXE:
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE
```

## <a name="see-also"></a>참고자료

[디렉터리 제어](../../c-runtime-library/directory-control.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
