---
title: _free_dbg
ms.date: 11/04/2016
api_name:
- _free_dbg
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _free_dbg
- free_dbg
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
ms.openlocfilehash: 43591ce8710dd25ad33832a5f084ca6e84bba979
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956800"
---
# <a name="_free_dbg"></a>_free_dbg

힙의 메모리 블록을 해제합니다(디버그 버전에만 해당함).

## <a name="syntax"></a>구문

```C
void _free_dbg(
   void *userData,
   int blockType
);
```

### <a name="parameters"></a>매개 변수

*userData*<br/>
해제할 이전에 할당된 메모리 블록에 대한 포인터입니다.

*blockType*<br/>
해제할 할당 된 메모리 블록의 형식입니다 ( **_CLIENT_BLOCK**, **_NORMAL_BLOCK**또는 **_IGNORE_BLOCK**).

## <a name="remarks"></a>설명

**_Free_dbg** 함수는 [free](free.md) 함수의 디버그 버전입니다. [_Debug](../../c-runtime-library/debug.md) 가 정의 되지 않은 경우 **_free_dbg** 에 대 한 각 호출은 **free**호출로 줄어듭니다. **Free** 및 **_free_dbg** 는 둘 다 기본 힙에서 메모리 블록을 해제 하지만 **_free_dbg** 은 두 가지 디버깅 기능을 제공 합니다 .이 기능에는 메모리 부족 조건을 시뮬레이션 하기 위해 힙의 연결 된 목록에 빈 블록을 유지 하 고 블록 형식 매개 변수를 사용 가능한 특정 할당 유형입니다.

**_free_dbg** 는 모든 지정 된 파일과 블록 위치에서 사용 가능한 작업을 수행 하기 전에 유효성 검사를 수행 합니다. 애플리케이션에서는 이러한 유효성 검사 정보를 제공하지 않습니다. 메모리 블록이 해제되면 디버그 힙 관리자는 자동으로 사용자 부분 양쪽에 있는 버퍼의 무결성을 확인하며 덮어쓰기가 발생하면 오류 보고서를 만듭니다. [_CrtDbgFlag](../../c-runtime-library/crtdbgflag.md) 플래그의 **_CRTDBG_DELAY_FREE_MEM_DF** bit 필드가 설정 된 경우 해제 된 블록은 값 0Xdd로 채워지고, **_FREE_BLOCK** 블록 형식을 할당 하 고, 힙의 연결 된 메모리 블록 목록에 보관 합니다.

메모리를 확보 하는 동안 오류가 발생 하는 경우 **errno** 는 오류 특성에 따라 운영 체제의 정보로 설정 됩니다. 자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 애플리케이션의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_free_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

**_Free_dbg**를 사용 하는 방법에 대 한 샘플은 [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)를 참조 하세요.

## <a name="see-also"></a>참고자료

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
