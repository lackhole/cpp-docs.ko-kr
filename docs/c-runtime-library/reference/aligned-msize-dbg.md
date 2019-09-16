---
title: _aligned_msize_dbg
ms.date: 11/04/2016
api_name:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
ms.openlocfilehash: f2a0ceab906dccacb2e1c78a8789d524b608a4ff
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939870"
---
# <a name="_aligned_msize_dbg"></a>_aligned_msize_dbg

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

*맞춤* 및 *오프셋* 값은 블록을 할당 한 함수에 전달 된 값과 같아야 합니다.

**_aligned_msize_dbg** 는 [_aligned_msize](aligned-msize.md) 함수의 디버그 버전입니다. [_Debug](../../c-runtime-library/debug.md) 가 정의 되지 않은 경우 **_aligned_msize_dbg** 에 대 한 각 호출은 **_aligned_msize**에 대 한 호출로 줄어듭니다. **_Aligned_msize** 와 **_aligned_msize_dbg** 는 모두 기본 힙의 메모리 블록 크기를 계산 하지만 **_aligned_msize_dbg** 는 디버깅 기능을 추가 합니다. 반환 된 크기에서 메모리 블록의 사용자 부분 양쪽에 있는 버퍼를 포함 합니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. *Memblock* 이 null 포인터 이거나 *맞춤이* 2의 거듭제곱이 아니면 **_Msize** 는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 합니다. 오류가 처리 되 면 함수는 **errno** 를 **EINVAL** 로 설정 하 고-1을 반환 합니다.

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
