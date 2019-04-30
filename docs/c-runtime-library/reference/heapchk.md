---
title: _heapchk
ms.date: 11/04/2016
apiname:
- _heapchk
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
- _heapchk
- heapchk
helpviewer_keywords:
- debugging [CRT], heap-related problems
- consistency checking of heaps
- heapchk function
- heaps, checking consistency
- _heapchk function
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
ms.openlocfilehash: bdc0137761664a668d6ef95d739f09501e8290e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331716"
---
# <a name="heapchk"></a>_heapchk

힙에서 일관성 확인을 실행합니다.

## <a name="syntax"></a>구문

```C
int _heapchk( void );
```

## <a name="return-value"></a>반환 값

**_heapchk** Malloc.h에 정의 된 다음 정수 매니페스트 상수 중 하나를 반환 합니다.

|반환 값|조건|
|-|-|
| **_HEAPBADBEGIN** | 초기 헤더 정보가 잘못되었거나 찾을 수 없습니다. |
| **_HEAPBADNODE** | 잘못된 노드가 검색되었거나 힙이 손상되었습니다. |
| **_HEAPBADPTR** | 힙 포인터가 잘못되었습니다. |
| **_HEAPEMPTY** | 힙이 초기화되지 않았습니다. |
| **_HEAPOK** | 힙이 일치하는 것 같습니다. |

또한 오류가 발생 하는 경우 **_heapchk** 설정 **errno** 하 **ENOSYS**합니다.

## <a name="remarks"></a>설명

합니다 **_heapchk** 함수를 사용 하면 힙의 최소 일관성 검사 하 여 힙 관련 문제를 디버그 합니다. 운영 체제를 지원 하지 않는 경우 **_heapchk**함수를 반환 합니다 (예: Windows 98) **_HEAPOK** 집합과 **errno** 에 **ENOSYS**.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_heapchk**|\<malloc.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_heapchk.c
// This program checks the heap for
// consistency and prints an appropriate message.

#include <malloc.h>
#include <stdio.h>

int main( void )
{
   int  heapstatus;
   char *buffer;

   // Allocate and deallocate some memory
   if( (buffer = (char *)malloc( 100 )) != NULL )
      free( buffer );

   // Check heap status
   heapstatus = _heapchk();
   switch( heapstatus )
   {
   case _HEAPOK:
      printf(" OK - heap is fine\n" );
      break;
   case _HEAPEMPTY:
      printf(" OK - heap is empty\n" );
      break;
   case _HEAPBADBEGIN:
      printf( "ERROR - bad start of heap\n" );
      break;
   case _HEAPBADNODE:
      printf( "ERROR - bad node in heap\n" );
      break;
   }
}
```

```Output
OK - heap is fine
```

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
[_heapwalk](heapwalk.md)<br/>
