---
title: _dupenv_s_dbg, _wdupenv_s_dbg
ms.date: 11/04/2016
apiname:
- _dupenv_s_dbg
- _wdupenv_s_dbg
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
apitype: DLLExport
f1_keywords:
- _tdupenv_s_dbg
- _dupenv_s_dbg
- _wdupenv_s_dbg
helpviewer_keywords:
- _tdupenv_s_dbg function
- dupenv_s_dbg function
- _wdupenv_s_dbg function
- environment variables
- tdupenv_s_dbg function
- wdupenv_s_dbg function
- _dupenv_s_dbg function
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
ms.openlocfilehash: 95d8c18a0ebc543304fdb6bf51c4adde589333aa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339223"
---
# <a name="dupenvsdbg-wdupenvsdbg"></a>_dupenv_s_dbg, _wdupenv_s_dbg

현재 환경에서 값을 가져옵니다.  추가 디버깅 정보를 제공하기 위해 [_malloc_dbg](malloc-dbg.md)를 통해 메모리를 할당하는 [_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _dupenv_s_dbg(
   char **buffer,
   size_t *numberOfElements,
   const char *varname,
   int blockType,
   const char *filename,
   int linenumber
);
errno_t _wdupenv_s_dbg(
   wchar_t **buffer,
   size_t * numberOfElements,
   const wchar_t *varname,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
변수 값을 저장하는 버퍼입니다.

*numberOfElements*<br/>
크기인 *버퍼*합니다.

*varname*<br/>
환경 변수 이름입니다.

*blockType*<br/>
요청 된 메모리 블록의 형식: **_CLIENT_BLOCK** 하거나 **_NORMAL_BLOCK**합니다.

*filename*<br/>
소스 파일의 이름에 대 한 포인터 또는 **NULL**합니다.

*linenumber*<br/>
소스 파일의 줄 번호 또는 **NULL**합니다.

## <a name="return-value"></a>반환 값

성공 시 0, 실패 시 오류 코드가 나타납니다.

이러한 함수는 매개 변수 유효성 검사 하는 경우 *버퍼* 또는 *varname* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우 함수를 설정 **errno** 하 **EINVAL** 돌아와 **EINVAL**합니다.

이러한 함수는 충분 한 메모리를 할당할 수 없습니다, 하는 경우 *버퍼* 하 **NULL** 및 *numberOfElements* 0을 반환 **ENOMEM**합니다.

## <a name="remarks"></a>설명

합니다 **_dupenv_s_dbg** 하 고 **_wdupenv_s_dbg** 함수는 동일 **_dupenv_s** 및 **_wdupenv_s** 점을 제외 하 고, **_DEBUG** 는의 디버그 버전을 사용 하 여 이러한 함수를 정의 [malloc](malloc.md)를 [_malloc_dbg](malloc-dbg.md), 환경 변수 값에 대 한 메모리를 할당할 수 있습니다. 디버깅 기능에 대 한 내용은 **_malloc_dbg**를 참조 하십시오 [_malloc_dbg](malloc-dbg.md)합니다.

대부분의 경우 이러한 함수를 명시적으로 호출할 필요가 없습니다. 대신 플래그를 정의할 수 있습니다 **_CRTDBG_MAP_ALLOC**합니다. 때 **_CRTDBG_MAP_ALLOC** 에 대 한 호출을 정의 하면 **_dupenv_s** 하 고 **_wdupenv_s** 로 다시 매핑되고 **_dupenv_s_dbg** 및 **_wdupenv_s_dbg**각각 사용 하 여는 *blockType* 로 설정 **_NORMAL_BLOCK**합니다. 따라서 힙 블록으로 표시 하려는 경우가 아니면 이러한 함수를 명시적으로 호출할 필요가 없습니다 **_CLIENT_BLOCK**합니다. 블록 형식에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s_dbg**|**_dupenv_s_dbg**|**_dupenv_s_dbg**|**_wdupenv_s_dbg**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_dupenv_s_dbg**|\<crtdbg.h>|
|**_wdupenv_s_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_dupenv_s_dbg.c
#include  <stdlib.h>
#include <crtdbg.h>

int main( void )
{
   char *pValue;
   size_t len;
   errno_t err = _dupenv_s_dbg( &pValue, &len, "pathext",
      _NORMAL_BLOCK, __FILE__, __LINE__ );
   if ( err ) return -1;
   printf( "pathext = %s\n", pValue );
   free( pValue );
   err = _dupenv_s_dbg( &pValue, &len, "nonexistentvariable",
      _NORMAL_BLOCK, __FILE__, __LINE__ );
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
[getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)<br/>
