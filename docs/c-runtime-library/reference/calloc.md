---
title: calloc
ms.date: 11/04/2016
apiname:
- calloc
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
- calloc
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
ms.openlocfilehash: 59aa535136cf32ea5dd68b8917ec969eee41e2ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347732"
---
# <a name="calloc"></a>calloc

0으로 초기화된 요소가 있는 메모리에 배열을 할당합니다.

## <a name="syntax"></a>구문

```C
void *calloc(
   size_t num,
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*number*<br/>
요소의 수입니다.

*size*<br/>
각 요소의 길이입니다(바이트).

## <a name="return-value"></a>반환 값

**calloc** 할당 된 공간에 대 한 포인터를 반환 합니다. 반환 값이 가리킨 스토리지 공간은 모든 형식의 개체 스토리지를 위해 적절하게 정렬되도록 보장됩니다. 이외의 형식에 대 한 포인터를 가져오려면 **void**, 반환 값에 형식 캐스팅을 사용 합니다.

## <a name="remarks"></a>설명

합니다 **calloc** 의 배열에 대 한 저장소 공간을 할당 하는 함수 *번호* 길이의 각 요소 *크기* 바이트. 각 요소는 0으로 초기화됩니다.

**calloc** 설정 **errno** 에 **ENOMEM** 메모리의 양을 초과 요청 하는 경우 또는 메모리를 할당 하지 못하면 **_HEAP_MAXREQ**합니다. 이 오류 코드 및 기타 오류 코드에 대한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

**calloc** 호출 **malloc** 사용 하는 C++ [_set_new_mode](set-new-mode.md) 함수를 새 처리기 모드를 설정 합니다. 새 처리기 모드를 나타내는 실패 하는지를 **malloc** 에서 설정한 대로 새 처리기 루틴을 호출 하는 것 [_set_new_handler](set-new-handler.md)합니다. 기본적으로 **malloc** 메모리 할당 실패 시 새 처리기 루틴을 호출 하지 않습니다. 이 기본 동작을 재정의할 수 있도록 때 **calloc** 메모리를 할당 하지 못했습니다 **malloc** 동일한 새 처리기 루틴을 호출 방식으로 **새** 연산자는 경우 이와 같은 이유로 실패 합니다. 기본값을 재정의하려면 다음을

```C
_set_new_mode(1);
```

프로그램에서 초기에 호출하거나, NEWMODE.OBJ를 사용하여 연결합니다([링크 옵션](../../c-runtime-library/link-options.md) 참조).

응용 프로그램이 C 런타임 라이브러리의 디버그 버전과 연결 됩니다 **calloc** 로 확인 되 [_calloc_dbg](calloc-dbg.md)합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

**calloc** 표시 됩니다 `__declspec(noalias)` 및 `__declspec(restrict)`, 즉는 함수가 전역 변수를 수정할 수 없도록 보장 되 고 반환 된 포인터는 별칭이 지정 되지 않습니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**calloc**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_calloc.c
// This program uses calloc to allocate space for
// 40 long integers. It initializes each element to zero.

#include <stdio.h>
#include <malloc.h>

int main( void )
{
   long *buffer;

   buffer = (long *)calloc( 40, sizeof( long ) );
   if( buffer != NULL )
      printf( "Allocated 40 long integers\n" );
   else
      printf( "Can't allocate memory\n" );
   free( buffer );
}
```

```Output
Allocated 40 long integers
```

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
