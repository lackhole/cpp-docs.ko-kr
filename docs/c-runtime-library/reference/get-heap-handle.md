---
title: _get_heap_handle
ms.date: 11/04/2016
apiname:
- _get_heap_handle
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
- _get_heap_handle
- get_heap_handle
helpviewer_keywords:
- heap functions
- memory allocation, heap memory
- _get_heap_handle function
- get_heap_handle function
ms.assetid: a4d05049-8528-494a-8281-a470d1e1115c
ms.openlocfilehash: 82ea108a41bec1d0276e2c952b3f509f36bab8ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332119"
---
# <a name="getheaphandle"></a>_get_heap_handle

C 런타임 시스템에서 사용되는 힙의 핸들을 반환합니다.

## <a name="syntax"></a>구문

```C
intptr_t _get_heap_handle( void );
```

## <a name="return-value"></a>반환 값

C 런타임 시스템에서 사용되는 Win32 힙에 대한 핸들을 반환합니다.

## <a name="remarks"></a>설명

[HeapSetInformation](/windows/desktop/api/heapapi/nf-heapapi-heapsetinformation) 을 호출하고 CRT 힙에서 낮은 조각화 힙을 사용하도록 설정하려는 경우 이 함수를 사용합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_heap_handle**|\<malloc.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="sample"></a>샘플

```cpp
// crt_get_heap_handle.cpp
// compile with: /MT
#include <windows.h>
#include <malloc.h>
#include <stdio.h>

int main(void)
{
    intptr_t hCrtHeap = _get_heap_handle();
    ULONG ulEnableLFH = 2;
    if (HeapSetInformation((PVOID)hCrtHeap,
                           HeapCompatibilityInformation,
                           &ulEnableLFH, sizeof(ulEnableLFH)))
        puts("Enabling Low Fragmentation Heap succeeded");
    else
        puts("Enabling Low Fragmentation Heap failed");
    return 0;
}
```

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
