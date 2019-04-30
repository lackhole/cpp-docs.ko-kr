---
title: _set_new_handler
ms.date: 11/04/2016
apiname:
- _set_new_handler
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_new_handler
- set_new_handler
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
ms.openlocfilehash: bc7718503f59c69868a75cac9383286a548fc307
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356502"
---
# <a name="setnewhandler"></a>_set_new_handler

**new** 연산자에서 메모리 할당에 실패하는 경우 오류 처리 메커니즘에 제어를 전달합니다.

## <a name="syntax"></a>구문

```cpp
_PNH _set_new_handler( _PNH pNewHandler );
```

### <a name="parameters"></a>매개 변수

*pNewHandler*<br/>
애플리케이션에서 제공하는 메모리 처리 함수에 대한 포인터입니다. 인수가 0이면 새 처리기가 제거됩니다.

## <a name="return-value"></a>반환 값

이전 예외 처리로 등록 된 함수에 대 한 포인터를 반환 **_set_new_handler**이전 함수는 나중에 복원할 수 있도록 합니다. 기본 동작을 복원 하려면 반환 값을 사용할 수 없는 이전 함수가 설정 된 경우 이 값은 **NULL**합니다.

## <a name="remarks"></a>설명

C++ **_set_new_handler** 함수는 경우 컨트롤을 얻는 예외 처리 함수를 지정 합니다 **새** 연산자 메모리 할당에 실패 합니다. 하는 경우 **새** 실패 하면 런타임 시스템 예외 처리 함수에 인수로 전달 된 자동으로 호출 **_set_new_handler**합니다. **_PNH**New.h에 정의 된, 형식을 반환 하는 함수에 대 한 포인터 **int** 형식의 인수를 사용 하 고 **size_t**합니다. 사용 하 여 **size_t** 할당할 공간의 크기를 지정 합니다.

기본 처리기가 없습니다.

**_set_new_handler** 기본적으로 가비지 수집 체계입니다. 런타임 시스템은 함수가 0이 아닌 값을 반환할 때마다 할당을 다시 시도하고 함수가 0을 반환할 경우 실패합니다.

발생 합니다 **_set_new_handler** 함수는 프로그램에서 런타임 시스템을 사용 하 여 인수 목록에 지정 된 예외 처리 함수를 등록 합니다.

```cpp
// set_new_handler1.cpp
#include <new.h>

int handle_program_memory_depletion( size_t )
{
   // Your code
}

int main( void )
{
   _set_new_handler( handle_program_memory_depletion );
   int *pi = new int[BIG_NUMBER];
}
```

에 마지막으로 전달 된 함수 주소를 저장할 수 있습니다 합니다 **_set_new_handler** 함수를 나중에 다시 시작 합니다.

```cpp
   _PNH old_handler = _set_new_handler( my_handler );
   // Code that requires my_handler
   // . . .
   _set_new_handler( old_handler )
   // Code that requires old_handler
   // . . .
```

C++ [_set_new_mode](set-new-mode.md) 함수는 [malloc](malloc.md)에 대한 새 처리기 모드를 설정합니다. 새 처리기 모드를 나타내는 실패 하는지를 **malloc** 에서 설정한 대로 새 처리기 루틴을 호출 하는 것 **_set_new_handler**합니다. 기본적으로 **malloc** 메모리 할당 실패 시 새 처리기 루틴을 호출 하지 않습니다. 이 기본 동작을 재정의할 수 있도록 때 **malloc** 메모리를 할당 하지 못했습니다 **malloc** 동일한 새 처리기 루틴을 호출 방식으로 **새** 연산자는 경우 이와 같은 이유로 실패 합니다. 기본값을 재정의하려면 다음을

```cpp
_set_new_mode(1);
```

초기 프로그램 또는 Newmode.obj에 대한 링크에서 호출합니다.

사용자 정의 하는 경우 `operator new` 제공 새 처리기 함수가 자동으로 실패 시 호출 되지 않습니다.

자세한 내용은 *C++ 언어 참조*의 [new](../../cpp/new-operator-cpp.md) 및 [delete](../../cpp/delete-operator-cpp.md)를 참조하세요.

단일 **_set_new_handler** 처리기를 호출 하는 경우에 해당 Dll 또는 실행 파일을 동적으로 모든 연결 **_set_new_handler** 다른 처리기를 바꿀 수 있습니다 또는 대체 하는 다른 DLL 또는 실행 파일로 설정한 처리기입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_set_new_handler**|\<new.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 예제에서는 할당이 실패하면 컨트롤이 MyNewHandler로 전송됩니다. MyNewHandler에 전달된 인수는 요청된 바이트 수입니다. MyNewHandler에서 반환된 값은 할당을 다시 시도해야 하는지 여부를 나타내는 플래그입니다. 0이 아닌 값은 할당을 다시 시도해야 함을 나타내며 값 0은 할당에 실패했음을 나타냅니다.

```cpp
// crt_set_new_handler.cpp
// compile with: /c
#include <stdio.h>
#include <new.h>
#define BIG_NUMBER 0x1fffffff

int coalesced = 0;

int CoalesceHeap()
{
   coalesced = 1;  // Flag RecurseAlloc to stop
   // do some work to free memory
   return 0;
}
// Define a function to be called if new fails to allocate memory.
int MyNewHandler( size_t size )
{
   printf("Allocation failed. Coalescing heap.\n");

   // Call a function to recover some heap space.
   return CoalesceHeap();
}

int RecurseAlloc() {
   int *pi = new int[BIG_NUMBER];
   if (!coalesced)
      RecurseAlloc();
   return 0;
}

int main()
{
   // Set the failure handler for new to be MyNewHandler.
   _set_new_handler( MyNewHandler );
   RecurseAlloc();
}
```

```Output
Allocation failed. Coalescing heap.

This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
