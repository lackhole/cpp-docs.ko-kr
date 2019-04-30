---
title: _aligned_free_dbg
ms.date: 11/04/2016
apiname:
- _aligned_free_dbg
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
- _aligned_free_dbg
- aligned_free_dbg
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
ms.openlocfilehash: f51b9b9573ab2e23a0a60979c55a33d2e5cff747
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341901"
---
# <a name="alignedfreedbg"></a>_aligned_free_dbg

[_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록을 해제합니다(디버그에만 해당).

## <a name="syntax"></a>구문

```C
void _aligned_free_dbg(
   void *memblock
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
반환 된 메모리 블록에 대 한 포인터를 [_aligned_malloc](aligned-malloc.md) 하거나 [_aligned_offset_malloc](aligned-offset-malloc.md) 함수입니다.

## <a name="remarks"></a>설명

합니다 **_aligned_free_dbg** 함수는 디버그 버전의는 [_aligned_free](aligned-free.md) 함수입니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 를 정의 하지 않은를 호출할 때마다 **_aligned_free_dbg** 대 한 호출으로 줄어듭니다 `_aligned_free`합니다. 둘 다 `_aligned_free` 하 고 **_aligned_free_dbg** 기본 힙에서 메모리 블록을 해제 하지만 **_aligned_free_dbg** 디버깅 기능이: 해제 된 보관할 수 있는 블록을 힙의 연결 된 목록 메모리 부족 조건을 시뮬레이션 합니다.

**_aligned_free_dbg** 해제 작업을 수행 하기 전에 지정 된 모든 파일과 블록 위치에서 유효성 검사를 수행 합니다. 애플리케이션에서는 이러한 유효성 검사 정보를 제공하지 않습니다. 메모리 블록이 해제되면 디버그 힙 관리자는 자동으로 사용자 부분 양쪽에 있는 버퍼의 무결성을 확인하며 덮어쓰기가 발생하면 오류 보고서를 만듭니다. _CRTDBG_DELAY_FREE_MEM_DF 비트 필드의 경우는 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그를 설정, 해제 된 블록은 값 0xDD로, _FREE_BLOCK 블록 형식이 할당 및 메모리 블록을 힙의 연결된 리스트에 보관 합니다.

메모리 해제 중 오류가 발생하면 운영 체제에서 제공하는 실패 특성에 대한 정보를 바탕으로 `errno`가 설정됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 애플리케이션의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_aligned_free_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)