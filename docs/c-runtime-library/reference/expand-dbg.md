---
title: _expand_dbg
ms.date: 11/04/2016
apiname:
- _expand_dbg
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
- expand_dbg
- _expand_dbg
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
ms.openlocfilehash: cc3aa2b7e39b52eb71ac10a9b5c4a221ba6fb70c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288047"
---
# <a name="expanddbg"></a>_expand_dbg

블록을 확장하거나 축소하여 힙에서 지정된 메모리 블록의 크기를 조정합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void *_expand_dbg(
   void *userData,
   size_t newSize,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*userData*<br/>
이전에 할당된 메모리 블록에 대한 포인터입니다.

*newSize*<br/>
요청된 블록의 새 크기(바이트)입니다.

*blockType*<br/>
요청 된 크기가 조정 된 블록에 대 한 형식: **_CLIENT_BLOCK** 하거나 **_NORMAL_BLOCK**합니다.

*filename*<br/>
확장 작업을 요청한 소스 파일의 이름에 대 한 포인터 또는 **NULL**합니다.

*linenumber*<br/>
확장 작업이 요청 있는 소스 파일의 줄 번호 또는 **NULL**합니다.

*filename* 하 고 *linenumber* 매개 변수에 하면 볼 수 있습니다 **_expand_dbg** 명시적으로 호출 된 또는 [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)전처리기 상수가 정의 되었습니다.

## <a name="return-value"></a>반환 값

성공적으로 완료 되 면 **_expand_dbg** 크기가 조정 된 메모리 블록에 대 한 포인터를 반환 합니다. 메모리가 이동되지 않으므로 주소는 userData와 같습니다. 반환 하는 경우 오류가 발생 했습니다. 또는 요청 된 크기는 블록을 확장할 수 없습니다 **NULL**합니다. 오류가 발생 하는 경우 **errno** 오류의 특성에 대 한 정보는 운영 체제에서 사용 하는 것입니다. 에 대 한 자세한 내용은 **errno**를 참조 하십시오 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다.

## <a name="remarks"></a>설명

합니다 **_expand_dbg** 함수는 디버그 버전 _[확장](expand.md) 함수입니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 를 정의 하지 않은를 호출할 때마다 **_expand_dbg** 대 한 호출으로 줄어듭니다 **_expand**합니다. 둘 다 **_expand** 하 고 **_expand_dbg** 기본 힙에서 메모리 블록의 크기를 조정 하지만 **_expand_dbg** 몇 가지 디버깅 기능을 수용: 사용자의 양쪽에서 버퍼 부분 블록 누수 테스트, 블록 형식 매개 변수로 특정 할당 형식 추적 및 *filename*/*linenumber* 의 출처를 확인 하는 정보 할당 요청 수입니다.

**_expand_dbg** 는 요청 된 것 보다 약간 더 많은 공간을 사용 하 여 지정 된 메모리 블록 크기를 조정 *newSize*합니다. *newSize* 원래 할당 된 메모리 블록의 크기 보다 작거나 클 수 있습니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 애플리케이션에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 크기를 조정하려면 원래 메모리 블록을 확장하거나 축소합니다. **_expand_dbg** 처럼 메모리 블록을 이동 하지는 않습니다 합니다 [_realloc_dbg](realloc-dbg.md) 함수입니다.

때 *newSize* 원래 블록 크기, 메모리 블록을 확장 하는 보다 큽니다. 확장 중에 메모리 블록이 요청 된 크기에 맞게 확장할 수 없는 경우 **NULL** 반환 됩니다. 때 *newSize* 원래 블록 크기, 메모리 블록은 새 크기를 가져올 때까지 계약은 보다 작습니다.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 애플리케이션의 디버그 빌드에서 표준 힙 함수를 호출하는 것과 해당 함수의 디버그 버전을 호출하는 것의 차이에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 *memblock* 가 null 포인터인 경우 또는 크기 보다 크면 **_HEAP_MAXREQ**에 설명 된 대로이 함수는 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md). 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 고 함수가 반환 **NULL**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_expand_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="example"></a>예제

```C
// crt_expand_dbg.c
//
// This program allocates a block of memory using _malloc_dbg
// and then calls _msize_dbg to display the size of that block.
// Next, it uses _expand_dbg to expand the amount of
// memory used by the buffer and then calls _msize_dbg again to
// display the new amount of memory allocated to the buffer.
//

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
#include <crtdbg.h>

int main( void )
{
   long *buffer;
   size_t size;

   // Call _malloc_dbg to include the filename and line number
   // of our allocation request in the header
   buffer = (long *)_malloc_dbg( 40 * sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );
   if( buffer == NULL )
      exit( 1 );

   // Get the size of the buffer by calling _msize_dbg
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );

   // Expand the buffer using _expand_dbg and show the new size
   buffer = (long *)_expand_dbg( buffer, size + sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );

   if( buffer == NULL )
      exit( 1 );
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _expand_dbg of 1 more long: %u\n",
           size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after _malloc_dbg of 40 longs: 160
Size of block after _expand_dbg of 1 more long: 164
```

## <a name="comment"></a>주석

이 프로그램의 출력은 모든 섹션을 확장하는 컴퓨터 기능에 따라 달라집니다. 모든 섹션이 확장되면 출력이 출력 섹션에 반영됩니다.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
