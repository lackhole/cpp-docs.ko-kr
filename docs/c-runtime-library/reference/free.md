---
title: free
ms.date: 11/04/2016
apiname:
- free
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
- free
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
ms.openlocfilehash: f56212874f05ea5d4ab7bd826a7a4c145551dfc0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287761"
---
# <a name="free"></a>free

메모리 블록을 할당 해제하거나 해제합니다.

## <a name="syntax"></a>구문

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
해제할 이전에 할당된 메모리 블록입니다.

## <a name="remarks"></a>설명

**무료** 함수에는 메모리 블록을 할당 취소 (*memblock*)를 호출 하 여 이전에 할당 된 **calloc**하십시오 **malloc**, 또는 **realloc**합니다. 해제 된 바이트 수는 블록이 할당 된 경우 요청 된 바이트 수와 같습니다 (또는 다시 할당의 경우 **realloc**). 경우 *memblock* 은 **NULL**, 포인터가 무시 되 고 **무료** 즉시 반환 합니다. 잘못 된 포인터를 해제 하려고 (에서 할당 되지 않은 메모리 블록에 대 한 포인터 **calloc**하십시오 **malloc**, 또는 **realloc**) 후속 할당 요청에 영향을 줄 수 및 오류가 발생 합니다.

메모리를 해제에서 오류가 발생 하는 경우 **errno** 오류의 성격에 운영 체제에서 정보를 사용 하 여 설정 합니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

메모리 블록이 해제된 후 [_heapmin](heapmin.md)은 사용되지 않은 영역을 결합하고 다시 운영 체제로 릴리스하여 힙에 있는 사용 가능한 메모리 양을 최소화합니다. 운영 체제로 릴리스되지 않은 해제된 메모리는 사용 가능한 풀로 복원되고 다시 할당할 수 있습니다.

응용 프로그램이 C 런타임 라이브러리의 디버그 버전과 연결 됩니다 **무료** 로 확인 되 [_free_dbg](free-dbg.md)합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

**사용 가능한** 표시 된 `__declspec(noalias)`는 함수가 전역 변수를 수정할 수 없도록 보장 되는 의미입니다. 자세한 내용은 [noalias](../../cpp/noalias.md)를 참조하세요.

[_malloca](malloca.md)를 사용하여 할당된 메모리를 해제하려면 [_freea](freea.md)를 사용합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**free**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[malloc](malloc.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
