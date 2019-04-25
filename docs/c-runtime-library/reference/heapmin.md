---
title: _heapmin
ms.date: 11/04/2016
apiname:
- _heapmin
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
- _heapmin
- heapmin
helpviewer_keywords:
- heap memory
- minimizing heaps
- memory, releasing
- heaps, releasing unused memory
- _heapmin function
- heapmin function
ms.assetid: c0bccdf6-2d14-4d7b-a7ff-d6a17bdb410f
ms.openlocfilehash: 130986894d1e2a68415e6ab9218641eff484ffd1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157226"
---
# <a name="heapmin"></a>_heapmin

사용되지 않은 힙 메모리를 운영 체제로 해제합니다.

## <a name="syntax"></a>구문

```C
int _heapmin( void );
```

## <a name="return-value"></a>반환 값

성공 하면 **_heapmin** 0을 반환 함수가-1을 반환 하는 고, 그렇지 설정 **errno** 에 **ENOSYS**합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.

## <a name="remarks"></a>설명

합니다 **_heapmin** 함수는 운영 체제에 사용 되지 않는 힙 메모리를 해제 하 여 힙을 최소화 합니다. 운영 체제를 지원 하지 않는 경우 **_heapmin**함수 (예: Windows 98)-1을 반환 하 고 설정 **errno** 에 **ENOSYS**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_heapmin**|\<malloc.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapchk](heapchk.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
[_heapwalk](heapwalk.md)<br/>
[malloc](malloc.md)<br/>
