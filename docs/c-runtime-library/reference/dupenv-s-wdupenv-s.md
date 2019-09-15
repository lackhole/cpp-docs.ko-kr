---
title: _dupenv_s, _wdupenv_s
ms.date: 11/04/2016
api_name:
- _dupenv_s
- _wdupenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: f66828e0941c2324d75797cbb1fa77bdfa184205
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942019"
---
# <a name="_dupenv_s-_wdupenv_s"></a>_dupenv_s, _wdupenv_s

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
*버퍼*의 크기입니다.

*varname*<br/>
환경 변수 이름입니다.

## <a name="return-value"></a>반환 값

성공 시 0, 실패 시 오류 코드가 나타납니다.

이러한 함수는 해당 매개 변수의 유효성을 검사 합니다. *buffer* 또는 *varname* 이 **NULL**인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다. 계속 해 서 실행 하도록 허용한 경우이 함수는 **errno** 를 **EINVAL** 로 설정 하 고 **EINVAL**를 반환 합니다.

이러한 함수는 충분 한 메모리를 할당할 수 없는 경우 *버퍼* 를 **NULL** 로 설정 하 고 *numberofelements* 를 0으로 설정 하 고 **enomem**을 반환 합니다.

## <a name="remarks"></a>설명

**_Dupenv_s** 함수는 *varname*에 대 한 환경 변수 목록을 검색 합니다. 변수가 발견 되 면 **_dupenv_s** 는 버퍼를 할당 하 고 변수 값을 버퍼에 복사 합니다. 버퍼의 주소 및 길이가 *buffer* 및 *numberofelements*에서 반환 됩니다. **_Dupenv_s** 는 버퍼 자체를 할당 하 여 [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)에 대 한 보다 편리한 대안을 제공 합니다.

> [!NOTE]
> [free](free.md)를 호출하여 메모리를 확보하는 것은 호출하는 프로그램이 해야 할 일입니다.

변수를 찾을 수 없는 경우 *버퍼가* **NULL**로 설정 되 고 *numberofelements* 가 0으로 설정 되 고 반환 값은 0이 됩니다 .이 상황은 오류 조건으로 간주 되지 않기 때문입니다.

버퍼 크기에 관심이 없는 경우에는 *Numberofelements*에 대해 **NULL** 을 전달할 수 있습니다.

**_dupenv_s** 는 Windows 운영 체제에서 대/소문자를 구분 하지 않습니다. **_dupenv_s** 는 전역 변수 **_environ** 이 가리키는 환경의 복사본을 사용 하 여 환경에 액세스 합니다. **_Environ**의 토론은 [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) 의 설명을 참조 하세요.

*버퍼* 의 값은 환경 변수 값의 복사본입니다. 이를 수정 하면 환경에 영향을 주지 않습니다. [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md) 함수를 사용하여 환경 변수 값을 수정합니다.

**_wdupenv_s** 는 **_dupenv_s**의 와이드 문자 버전입니다. **_wdupenv_s** 의 인수는 와이드 문자 문자열입니다. **_Wenviron** 전역 변수는 **_environ**의 와이드 문자 버전입니다. **_Wenviron**에서 [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md) 에 대 한 설명을 참조 하세요.

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
