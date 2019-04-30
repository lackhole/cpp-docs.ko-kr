---
title: _dupenv_s, _wdupenv_s
ms.date: 11/04/2016
apiname:
- _dupenv_s
- _wdupenv_s
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
- tdupenv_s
- _dupenv_s
- wdupenv_s
- dupenv_s
- _tdupenv_s
- _wdupenv_s
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
ms.openlocfilehash: bc8af3282b57c9fa411aac97f5fa4d414bc3305b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288864"
---
# <a name="dupenvs-wdupenvs"></a>_dupenv_s, _wdupenv_s

현재 환경에서 값을 가져옵니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t _dupenv_s(
   char **buffer,
   size_t *numberOfElements,
   const char *varname
);
errno_t _wdupenv_s(
   wchar_t **buffer,
   size_t *numberOfElements,
   const wchar_t *varname
);
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
변수 값을 저장하는 버퍼입니다.

*numberOfElements*<br/>
크기인 *버퍼*합니다.

*varname*<br/>
환경 변수 이름입니다.

## <a name="return-value"></a>반환 값

성공 시 0, 실패 시 오류 코드가 나타납니다.

이러한 함수는 매개 변수 유효성 검사 하는 경우 *버퍼* 또는 *varname* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 함수를 설정 **errno** 하 **EINVAL** 돌아와 **EINVAL**합니다.

이러한 함수는 충분 한 메모리를 할당할 수 없습니다, 하는 경우 *버퍼* 하 **NULL** 및 *numberOfElements* 0을 반환 **ENOMEM**합니다.

## <a name="remarks"></a>설명

합니다 **_dupenv_s** 함수에 대 한 환경 변수 목록을 검색 *varname*합니다. 변수가 없으면 **_dupenv_s** 버퍼를 할당 하 고 변수 값을 버퍼로 복사 합니다. 에 반환 되는 버퍼의 주소 및 길이 *버퍼* 하 고 *numberOfElements*합니다. 버퍼 자체를 할당 하 여 **_dupenv_s** 는 보다 편리한 대안을 제공 [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)합니다.

> [!NOTE]
> [free](free.md)를 호출하여 메모리를 확보하는 것은 호출하는 프로그램이 해야 할 일입니다.

변수가 없는 경우, 한 다음 *버퍼* 로 설정 되어 **NULL**, *numberOfElements* 0으로 설정 되어이 이런이 오류로 간주 되지 않으므로 반환 값이 0 및 조건입니다.

버퍼의 크기에 관심이 없는 경우 전달할 수 있습니다 **NULL** 에 대 한 *numberOfElements*합니다.

**_dupenv_s** 대/소문자가 Windows 운영 체제에서. **_dupenv_s** 전역 변수에서 가리키는 환경의 복사본을 사용 하 여 **_environ** 환경에 액세스 합니다. 설명을 참조 하세요 [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) 대 한 설명은 **_environ**합니다.

값 *버퍼* 환경 변수 값의 복사본 인 환경에 영향을 주지 수정할 수 있습니다. [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md) 함수를 사용하여 환경 변수 값을 수정합니다.

**_wdupenv_s** 의 와이드 문자 버전이 **_dupenv_s**;의 인수 **_wdupenv_s** 는 와이드 문자 문자열입니다. 합니다 **_wenviron** 전역 변수는 와이드 문자 버전입니다 **_environ**합니다. 설명을 참조 하세요 [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) 대 한 자세한 내용은 **_wenviron**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s**|**_dupenv_s**|**_dupenv_s**|**_wdupenv_s**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_dupenv_s**|\<stdlib.h>|
|**_wdupenv_s**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_dupenv_s.c
#include  <stdlib.h>

int main( void )
{
   char *pValue;
   size_t len;
   errno_t err = _dupenv_s( &pValue, &len, "pathext" );
   if ( err ) return -1;
   printf( "pathext = %s\n", pValue );
   free( pValue );
   err = _dupenv_s( &pValue, &len, "nonexistentvariable" );
   if ( err ) return -1;
   printf( "nonexistentvariable = %s\n", pValue );
   free( pValue ); // It's OK to call free with NULL
}
```

```Output
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl
nonexistentvariable = (null)
```

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[환경 상수](../../c-runtime-library/environmental-constants.md)<br/>
[_dupenv_s_dbg, _wdupenv_s_dbg](dupenv-s-dbg-wdupenv-s-dbg.md)<br/>
[getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)<br/>
