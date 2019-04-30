---
title: _aligned_offset_malloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_offset_malloc_dbg
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
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
ms.openlocfilehash: 96fe9e7fda0d0cdfdbfa5462e4f601e3649e2233
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348876"
---
# <a name="alignedoffsetmallocdbg"></a>_aligned_offset_malloc_dbg

지정된 맞춤 경계에 메모리를 할당합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
void * _aligned_offset_malloc_dbg(
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
요청된 메모리 할당 크기입니다.

*alignment*<br/>
맞춤 값으로 2의 정수 거듭제곱이어야 합니다.

*offset*<br/>
맞춤을 강제하는 메모리 할당으로의 오프셋입니다.

*filename*<br/>
할당 작업을 요청한 소스 파일의 이름에 대 한 포인터 또는 **NULL**합니다.

*linenumber*<br/>
할당 작업이 요청 있는 소스 파일의 줄 번호 또는 **NULL**합니다.

## <a name="return-value"></a>반환 값

할당 된 메모리 블록에 대 한 포인터 또는 **NULL** 작업이 실패 합니다.

## <a name="remarks"></a>설명

**_aligned_offset_malloc_dbg** 의 디버그 버전이 합니다 [_aligned_offset_malloc](aligned-offset-malloc.md) 함수입니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 를 정의 하지 않은를 호출할 때마다 **_aligned_offset_malloc_dbg** 대 한 호출으로 줄어듭니다 **_aligned_offset_malloc**합니다. 둘 다 **_aligned_offset_malloc** 하 고 **_aligned_offset_malloc_dbg** 기본 힙에서 메모리 블록을 할당 하지만 **_aligned_offset_malloc_dbg** 여러 제공 디버깅 기능: 누수 테스트, 블록의 사용자 부분 양쪽에서 버퍼와 *filename*/*linenumber* 의 출처를 확인 하는 정보 할당 요청 수입니다. 블록 형식 매개 변수를 사용 하 여 특정 할당 형식 추적는 정렬 된 할당에 대 한 지원 되는 디버그 기능이 아닙니다. 정렬 된 할당 _NORMAL_BLOCK 블록 형식으로 표시 됩니다.

**_aligned_offset_malloc_dbg** 는 요청 된 것 보다 약간 더 많은 공간을 사용 하 여 메모리 블록 할당 *크기*합니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 애플리케이션에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 블록이 할당되면 블록의 사용자 부분은 값 0xCD로 채워지고 각 덮어쓰기 버퍼는 0xFD로 채워집니다.

**_aligned_offset_malloc_dbg** 는 중첩된 된 요소에 맞춤이 필요한 상황에서 유용 예를 들어 중첩된 된 클래스에 맞춤이 필요한 경우.

**_aligned_offset_malloc_dbg** 더해서 **malloc**; 자세한 내용은 참조 하십시오 [malloc](malloc.md)합니다.

이 함수를 설정 합니다 **errno** 하 **ENOMEM** 메모리 할당에 실패 하는 경우 또는 요청된 된 크기 보다 큰 되었으면 **_HEAP_MAXREQ**합니다. 에 대 한 자세한 내용은 **errno**를 참조 하십시오 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)합니다. 또한 **_aligned_offset_malloc** 해당 매개 변수 유효성을 검사 합니다. 하는 경우 *맞춤* 2의 거듭제곱이 아닌 경우 *오프셋* 보다 크거나 같음 *크기* 0이 아닌 경우이 함수는 잘못 된 매개 변수 처리기를 호출 에설명된대로[ 매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우이 함수를 반환 합니다 **NULL** 집합과 **errno** 하 **EINVAL**합니다.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_aligned_offset_malloc_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="see-also"></a>참조

[디버그 루틴](../../c-runtime-library/debug-routines.md)<br/>
