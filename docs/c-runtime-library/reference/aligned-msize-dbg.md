---
title: _aligned_msize_dbg
ms.date: 11/04/2016
apiname:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
ms.openlocfilehash: 054f7b88f93eef37a9a88fbb7895452f7c158716
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62342037"
---
# <a name="alignedmsizedbg"></a>_aligned_msize_dbg

힙에 할당된 메모리 블록의 크기를 반환합니다(디버그 버전에만 해당).

## <a name="syntax"></a>구문

```C
size_t _aligned_msize_dbg(
   void *memblock,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>매개 변수

*memblock*<br/>
메모리 블록에 대한 포인터입니다.

*alignment*<br/>
맞춤 값으로 2의 정수 거듭제곱이어야 합니다.

*offset*<br/>
맞춤을 강제하는 메모리 할당으로의 오프셋입니다.

## <a name="return-value"></a>반환 값

크기(바이트)를 부호 없는 정수로 반환합니다.

## <a name="remarks"></a>설명

합니다 *맞춤* 하 고 *오프셋* 값은 블록을 할당 하는 함수에 전달 된 값과 동일 해야 합니다.

**_aligned_msize_dbg** 의 디버그 버전이 합니다 [_aligned_msize](aligned-msize.md) 함수입니다. 때 [_DEBUG](../../c-runtime-library/debug.md) 를 정의 하지 않은를 호출할 때마다 **_aligned_msize_dbg** 대 한 호출으로 줄어듭니다 **_aligned_msize**합니다. 둘 다 **_aligned_msize** 하 고 **_aligned_msize_dbg** 기본 힙에서 메모리 블록의 크기를 계산 하지만 **_aligned_msize_dbg** 디버깅 기능을 추가 합니다. 반환 되는 크기의 메모리 블록의 사용자 부분 양쪽에서 버퍼를 포함합니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 하는 경우 *memblock* 가 null 포인터 또는 *맞춤* 가 2의 거듭제곱이 **_msize** 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사 ](../../c-runtime-library/parameter-validation.md). 함수를 설정 하는 오류 처리 되 면 **errno** 하 **EINVAL** -1을 반환 합니다.

기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 애플리케이션의 디버그 빌드에서 표준 힙 함수와 이 함수의 디버그 버전을 호출하는 경우의 차이점에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_aligned_msize_dbg**|\<crtdbg.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

[C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
