---
title: malloc
ms.date: 11/04/2016
apiname:
- malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- malloc
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
ms.openlocfilehash: e6a007fb6f089ebf1c9f5fc9ce59cbcbf0b13888
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157180"
---
# <a name="malloc"></a>malloc

메모리 블록을 할당합니다.

## <a name="syntax"></a>구문

```C
void *malloc(
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
할당할 바이트입니다.

## <a name="return-value"></a>반환 값

**malloc** 할당된 된 공간에 대 한 void 포인터를 반환 하거나 **NULL** 사용할 수 있는 메모리가 부족 한 경우. 이외의 다른 형식에 대 한 포인터를 반환 하려면 **void**, 반환 값에 형식 캐스팅을 사용 합니다. 반환 값이 가리키는 스토리지 공간은 맞춤 요구 사항이 기본 맞춤보다 작거나 같은 모든 형식의 개체 스토리지에 적절하게 맞춰지도록 보장됩니다. (시각적 개체의 C++를 기본 맞춤은 맞춤에 대 한 필수입니다는 **이중**, 또는 8 바이트입니다. 64비트 플랫폼을 대상으로 하는 코드에서는 16바이트입니다. 사용 하 여 [_aligned_malloc](aligned-malloc.md) 보다 큰 맞춤 요구 사항이 있는 개체에 대 한 저장소를 할당 하려면-예를 들어 SSE 형식 [__m128](../../cpp/m128.md) 및 **__m256**, 된 형식과 사용 하 여 선언 `__declspec(align( n ))` 여기서 **n** 8 보다 큽니다. 하는 경우 *크기* 가 0 이면 **malloc** 힙에서 길이가 0 인 항목을 할당 하 고 해당 항목에 대 한 유효한 포인터를 반환 합니다. 반환 된 값을 검사할 **malloc**요청 된 메모리 양이 작은 경우에 합니다.

## <a name="remarks"></a>설명

합니다 **malloc** 함수 메모리 블록을 하나 이상 할당 *크기* 바이트입니다. 블록 보다 클 수 있습니다 *크기* 맞춤 및 유지 관리 정보에 필요한 공간이 기 때문입니다.

**malloc** 설정 **errno** 에 **ENOMEM** 메모리의 양을 초과 요청 하는 경우 또는 메모리를 할당 하지 못하면 **_HEAP_MAXREQ**합니다. 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

시작 코드를 사용 하 여 **malloc** 저장소를 할당 하는 **_environ**에 *envp*, 및 *argv* 변수입니다. 다음 함수 및 와이드 문자 대응 호출할 수도 **malloc**합니다.

|||||
|-|-|-|-|
|[calloc](calloc.md)|[fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](getw.md)|[setvbuf](setvbuf.md)|
|[_exec 함수](../../c-runtime-library/exec-wexec-functions.md)|[fseek](fseek-fseeki64.md)|[_popen](popen-wpopen.md)|[_spawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)|
|[fgetc](fgetc-fgetwc.md)|[fsetpos](fsetpos.md)|[printf](printf-printf-l-wprintf-wprintf-l.md)|[_strdup](strdup-wcsdup-mbsdup.md)|
|[_fgetchar](fgetc-fgetwc.md)|[_fullpath](fullpath-wfullpath.md)|[putc](putc-putwc.md)|[system](system-wsystem.md)|
|[fgets](fgets-fgetws.md)|[fwrite](fwrite.md)|[putchar](putc-putwc.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](getc-getwc.md)|[_putenv](putenv-wputenv.md)|[ungetc](ungetc-ungetwc.md)|
|[fputc](fputc-fputwc.md)|[getchar](getc-getwc.md)|[puts](puts-putws.md)|[vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_fputchar](fputc-fputwc.md)|[_getcwd](getcwd-wgetcwd.md)|[_putw](putw.md)|[vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)|
|[fputs](fputs-fputws.md)|[_getdcwd](getcwd-wgetcwd.md)|[scanf](scanf-scanf-l-wscanf-wscanf-l.md)||
|[fread](fread.md)|[gets](../../c-runtime-library/gets-getws.md)|[_searchenv](searchenv-wsearchenv.md)||

C++ [_set_new_mode](set-new-mode.md) 함수는 **malloc**에 대한 새 처리기 모드를 설정합니다. 새 처리기 모드를 나타내는 실패 하는지를 **malloc** 에서 설정한 대로 새 처리기 루틴을 호출 하는 것 [_set_new_handler](set-new-handler.md)합니다. 기본적으로 **malloc** 메모리 할당 실패 시 새 처리기 루틴을 호출 하지 않습니다. 이 기본 동작을 재정의할 수 있도록 때 **malloc** 메모리를 할당 하지 못했습니다 **malloc** 동일한 새 처리기 루틴을 호출 방식으로 **새** 연산자는 경우 이와 같은 이유로 실패 합니다. 기본값을 재정의 하려면 호출 `_set_new_mode(1)` 초기 프로그램 또는 NEWMODE 사용 하 여 링크 합니다. OBJ (참조 [연결 옵션](../../c-runtime-library/link-options.md)).

응용 프로그램이 C 런타임 라이브러리의 디버그 버전과 연결 됩니다 **malloc** 로 확인 되 [_malloc_dbg](malloc-dbg.md)합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

**malloc** 표시 됩니다 `__declspec(noalias)` 및 `__declspec(restrict)`; 즉는 함수가 전역 변수를 수정할 수 없도록 보장 되 고 반환 된 포인터는 별칭이 지정 되지 않습니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**malloc**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_malloc.c
// This program allocates memory with
// malloc, then frees the memory with free.

#include <stdlib.h>   // For _MAX_PATH definition
#include <stdio.h>
#include <malloc.h>

int main( void )
{
   char *string;

   // Allocate space for a path name
   string = malloc( _MAX_PATH );

   // In a C++ file, explicitly cast malloc's return.  For example,
   // string = (char *)malloc( _MAX_PATH );

   if( string == NULL )
      printf( "Insufficient memory available\n" );
   else
   {
      printf( "Memory space allocated for path name\n" );
      free( string );
      printf( "Memory freed\n" );
   }
}
```

```Output
Memory space allocated for path name
Memory freed
```

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
