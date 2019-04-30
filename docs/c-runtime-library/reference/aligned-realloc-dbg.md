---
title: _aligned_realloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_realloc_dbg
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
- aligned_realloc_dbg
- _aligned_realloc_dbg
helpviewer_keywords:
- _aligned_realloc_dbg function
- aligned_realloc_dbg function
ms.assetid: 8aede920-991e-44cd-867f-83dc2165db47
ms.openlocfilehash: 136edf6b5c95149302920af0c8a8dc9c07458e3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348018"
---
# <a name="alignedreallocdbg"></a>_aligned_realloc_dbg

[_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void * _aligned_realloc_dbg(
   void *memblock,
   size_t size,
   size_t alignment,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
현재 메모리 블록 포인터입니다.

*size*<br/>
요청된 메모리 할당 크기입니다.

*alignment*<br/>
맞춤 값으로 2의 정수 거듭제곱이어야 합니다.

*filename*<br/>
요청한 소스 파일의 이름에 대 한 포인터를 **realloc** 작업이 나 **NULL**합니다.

*linenumber*<br/>
소스 파일의 줄 번호 위치는 **realloc** 작업이 요청 또는 **NULL**합니다.

## <a name="return-value"></a>반환 값

**_aligned_realloc_dbg** 다시 할당 (그리고 이동 되었을 수 있는) 메모리 블록에 대 한 void 포인터를 반환 합니다. 반환 값은 **NULL** 는 크기가 0이 고 버퍼 인수가 아닙니다 **NULL**, 충분 한 사용 가능한 메모리 블록을 지정 된 크기로 확장할 수 없는 경우 또는 합니다. 첫 번째 경우 원래 블록이 해제됩니다. 두 번째 경우 원래 블록은 변경되지 않습니다. 반환 값은 모든 형식의 개체 스토리지를 위해 적절하게 맞도록 보장되어 있는 스토리지 공간을 가리킵니다. void가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스팅을 사용합니다.

메모리를 다시 할당하고 블록의 맞춤을 변경하면 오류가 발생합니다.

## <a name="remarks"></a>설명

**_aligned_realloc_dbg** 의 디버그 버전이 합니다 [_aligned_realloc](aligned-realloc.md) 함수입니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 를 정의 하지 않은를 호출할 때마다 **_aligned_realloc_dbg** 대 한 호출으로 줄어듭니다 **_aligned_realloc**합니다. 둘 다 **_aligned_realloc** 하 고 **_aligned_realloc_dbg** 기본 힙에서 메모리 블록 다시 할당 하지만 **_aligned_realloc_dbg** 몇 가지 디버깅 기능을 수용 합니다. : 누수 테스트, 블록의 사용자 부분 양쪽에서 버퍼와 *filename*/*linenumber* 정보로 할당 요청의 원점을 확인 하 합니다. 블록 형식 매개 변수를 사용 하 여 특정 할당 형식 추적는 정렬 된 할당에 대 한 지원 되는 디버그 기능이 아닙니다. 정렬 된 할당 _NORMAL_BLOCK 블록 형식으로 표시 됩니다.

**_aligned_realloc_dbg** 는 요청 된 것 보다 약간 더 많은 공간을 사용 하 여 지정 된 메모리 블록 다시 할당 *newSize*합니다. *newSize* 원래 할당 된 메모리 블록의 크기 보다 작거나 클 수 있습니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 애플리케이션에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 다시 할당하면 원래 메모리 블록이 힙의 다른 위치로 이동하고 메모리 블록의 크기가 변할 수 있습니다. 메모리 블록이 이동하면 원래 블록의 내용을 덮어씁니다.

**_aligned_realloc_dbg** 설정 **errno** 하려면 **ENOMEM** 메모리 할당이 실패 하는 경우 또는 (앞에서 언급 한 오버 헤드 포함)는 데 필요한 메모리 양을 초과 **_ HEAP_MAXREQ**합니다. 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

또한 **_aligned_realloc_dbg** 해당 매개 변수 유효성을 검사 합니다. 하는 경우 *맞춤* 거듭제곱이 아닌 2의이 함수는 잘못 된 매개 변수 처리기를 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우이 함수를 반환 합니다 **NULL** 집합과 **errno** 하 **EINVAL**합니다.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 애플리케이션의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_aligned_realloc_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="see-also"></a>참조

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
