---
title: _msize_dbg
ms.date: 11/04/2016
apiname:
- _msize_dbg
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
- _msize_dbg
- msize_dbg
helpviewer_keywords:
- memory blocks
- _msize_dbg function
- msize_dbg function
ms.assetid: a333f4b6-f8a2-4e61-bb69-cb34063b8cef
ms.openlocfilehash: 3b6d08d44162d8263ca88147fe86166924d7d162
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156306"
---
# <a name="msizedbg"></a>_msize_dbg

힙의 메모리 블록 크기를 계산합니다(디버그 버전에만 해당함).

## <a name="syntax"></a>구문

```C
size_t _msize_dbg(
   void *userData,
   int blockType
);
```

### <a name="parameters"></a>매개 변수

*userData*<br/>
크기를 결정할 메모리 블록에 대한 포인터입니다.

*blockType*<br/>
지정 된 메모리 블록의 형식: **_CLIENT_BLOCK** 하거나 **_NORMAL_BLOCK**합니다.

## <a name="return-value"></a>반환 값

성공적으로 완료 되 면 **_msize_dbg** 는 지정 된 메모리 블록의 크기 (메가바이트)를 반환 합니다. 그렇지 않으면 반환 **NULL**합니다.

## <a name="remarks"></a>설명

**_msize_dbg** _의 디버그 버전이[msize](msize.md) 함수입니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 를 정의 하지 않은를 호출할 때마다 **_msize_dbg** 대 한 호출으로 줄어듭니다 **_msize**합니다. 둘 다 **_msize** 하 고 **_msize_dbg** 기본 힙에서 메모리 블록의 크기를 계산 하지만 **_msize_dbg** 두 가지 디버깅 기능을 추가 합니다. 반환 되는 크기의 메모리 블록의 사용자 부분 양쪽에서 버퍼를 포함 하 고 특정 블록 유형에 대해 크기를 계산할 수 있습니다.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 애플리케이션의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 하는 경우 *memblock* 가 null 포인터 **_msize** 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수를 설정 하는 오류 처리 되 면 **errno** 하 **EINVAL** -1을 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_msize_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="example"></a>예제

```C
// crt_msize_dbg.c
// compile with: /MTd
/*
* This program allocates a block of memory using _malloc_dbg
* and then calls _msize_dbg to display the size of that block.
* Next, it uses _realloc_dbg to expand the amount of
* memory used by the buffer and then calls _msize_dbg again to
* display the new amount of memory allocated to the buffer.
*/

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
#include <crtdbg.h>

int main( void )
{
        long *buffer, *newbuffer;
        size_t size;

        /*
         * Call _malloc_dbg to include the filename and line number
         * of our allocation request in the header
         */
        buffer = (long *)_malloc_dbg( 40 * sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );
        if( buffer == NULL )
               exit( 1 );

        /*
         * Get the size of the buffer by calling _msize_dbg
         */
        size = _msize_dbg( buffer, _NORMAL_BLOCK );
        printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );

        /*
         * Reallocate the buffer using _realloc_dbg and show the new size
         */
        newbuffer = _realloc_dbg( buffer, size + (40 * sizeof(long)), _NORMAL_BLOCK, __FILE__, __LINE__ );
        if( newbuffer == NULL )
               exit( 1 );
        buffer = newbuffer;
        size = _msize_dbg( buffer, _NORMAL_BLOCK );
        printf( "Size of block after _realloc_dbg of 40 more longs: %u\n", size );

        free( buffer );
        exit( 0 );
}
```

### <a name="output"></a>출력

```Output
Size of block after _malloc_dbg of 40 longs: 160
Size of block after _realloc_dbg of 40 more longs: 320
```

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
