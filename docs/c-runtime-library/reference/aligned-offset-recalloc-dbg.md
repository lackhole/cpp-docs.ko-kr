---
title: _aligned_offset_recalloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_offset_recalloc_dbg
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
- aligned_offset_recalloc_dbg
- _aligned_offset_recalloc_dbg
helpviewer_keywords:
- aligned_offset_recalloc_dbg function
- _aligned_offset_recalloc_dbg function
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
ms.openlocfilehash: e363a1cb104db9973f5f9e9c67a5d40693d405ee
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939743"
---
# <a name="_aligned_offset_recalloc_dbg"></a>_aligned_offset_recalloc_dbg

[_aligned_malloc](aligned-malloc.md) 또는 [_aligned_offset_malloc](aligned-offset-malloc.md)를 사용하여 할당된 메모리 블록의 크기를 변경하고 메모리를 0으로 초기화합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void * _aligned_offset_recalloc_dbg(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
현재 메모리 블록 포인터입니다.

*number*<br/>
요소의 수입니다.

*size*<br/>
각 요소의 길이입니다(바이트).

*alignment*<br/>
맞춤 값으로 2의 정수 거듭제곱이어야 합니다.

*offset*<br/>
맞춤을 강제하는 메모리 할당으로의 오프셋입니다.

*filename*<br/>
Realloc 작업 또는 **NULL**을 요청한 소스 파일의 이름에 대 한 포인터입니다.

*linenumber*<br/>
Realloc 작업이 요청 되었거나 **NULL 인**소스 파일의 줄 번호입니다.

## <a name="return-value"></a>반환 값

**_aligned_offset_recalloc_dbg** 는 다시 할당 된 (그리고 이동 가능한) 메모리 블록에 대 한 void 포인터를 반환 합니다. 크기가 0이 고 버퍼 인수가 **null**이 아닌 경우 또는 블록을 지정 된 크기로 확장 하는 데 사용할 수 있는 메모리가 부족 한 경우 반환 값은 **null** 입니다. 첫 번째 경우 원래 블록이 해제됩니다. 두 번째 경우 원래 블록은 변경되지 않습니다. 반환 값은 모든 형식의 개체 스토리지를 위해 적절하게 맞도록 보장되어 있는 스토리지 공간을 가리킵니다. void가 아닌 형식의 포인터를 얻으려면 반환 값에 형식 캐스팅을 사용합니다.

## <a name="remarks"></a>설명

**_aligned_offset_realloc_dbg** 는 [_aligned_offset_recalloc](aligned-offset-recalloc.md) 함수의 디버그 버전입니다. [_Debug](../../c-runtime-library/debug.md) 가 정의 되지 않은 경우 **_aligned_offset_recalloc_dbg** 에 대 한 각 호출은 **_aligned_offset_recalloc**에 대 한 호출로 줄어듭니다. **_Aligned_offset_recalloc** 와 **_aligned_offset_recalloc_dbg** 는 둘 다 기본 힙에서 메모리 블록을 다시 할당 하지만 **_aligned_offset_recalloc_dbg** 는 여러 가지 디버깅 기능을 제공 합니다 .이는 사용자 부분 양쪽에 있는 버퍼입니다. 누수를 테스트할 블록의 이름과 *파일 이름*/*linenumber* 정보는 할당 요청의 원본을 결정 합니다. 블록 형식 매개 변수를 사용 하 여 특정 할당 형식을 추적 하는 것은 정렬 된 할당에 대해 지원 되는 디버그 기능이 아닙니다. 정렬 된 할당은 _NORMAL_BLOCK 블록 형식으로 표시 됩니다.

**_aligned_offset_realloc_dbg** 는 요청 된 *newSize*보다 약간 더 많은 공간을 사용 하 여 지정 된 메모리 블록을 다시 할당 합니다. *newSize* 는 원래 할당 된 메모리 블록의 크기 보다 크거나 적을 수 있습니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 애플리케이션에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 다시 할당하면 원래 메모리 블록이 힙의 다른 위치로 이동하고 메모리 블록의 크기가 변할 수 있습니다. 메모리 블록이 이동하면 원래 블록의 내용을 덮어씁니다.

이 함수는 메모리 할당에 실패 한 경우 또는 요청 된 크기 (*숫자* * *크기*)가 **_HEAP_MAXREQ**보다 큰 경우 **errno** 을 **enomem** 으로 설정 합니다. **Errno**에 대 한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조 하세요. 또한 **_aligned_offset_recalloc_dbg** 는 매개 변수의 유효성을 검사 합니다. *Alignment* 가 2의 거듭제곱이 아니거나 *오프셋이* 요청 된 크기 보다 크거나 같고 0이 아닌 경우이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 합니다. 계속 해 서 실행 하도록 허용한 경우이 함수는 **NULL** 을 반환 하 고 **errno** 를 **EINVAL**로 설정 합니다.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 애플리케이션의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_aligned_offset_recalloc_dbg**|\<malloc.h>|

## <a name="see-also"></a>참고자료

[데이터 맞춤](../../c-runtime-library/data-alignment.md)<br/>
