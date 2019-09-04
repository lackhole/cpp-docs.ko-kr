---
title: _ReadWriteBarrier
ms.date: 09/02/2019
f1_keywords:
- _ReadWriteBarrier
helpviewer_keywords:
- ReadWriteBarrier intrinsic
- _ReadWriteBarrier intrinsic
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
ms.openlocfilehash: d755d045970da01d2eee33377c1452191eac4fe2
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217978"
---
# <a name="_readwritebarrier"></a>_ReadWriteBarrier

**Microsoft 전용**

호출 시점 전체에서 메모리 액세스를 다시 정렬할 수 있는 컴파일러 최적화를 제한합니다.

> [!CAUTION]
> `_ReadBarrier`, `_WriteBarrier` 및 `_ReadWriteBarrier` 컴파일러 내장 함수 및 `MemoryBarrier` 매크로는 모두 더 이상 사용되지 않으므로 사용하면 안 됩니다. 스레드 간 통신의 경우 [ C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)에 정의 된 [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) 및 [std:: atomic\<T >](../standard-library/atomic.md)와 같은 메커니즘을 사용 합니다. 하드웨어 액세스의 경우 [/volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md) 컴파일러 옵션을 [volatile](../cpp/volatile-cpp.md) 키워드와 함께 사용 합니다.

## <a name="syntax"></a>구문

```C
void _ReadWriteBarrier(void);
```

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_ReadWriteBarrier`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

`_ReadWriteBarrier` 내장 함수는 호출 시점 전체에서 메모리 액세스를 제거 또는 다시 정렬할 수 있는 컴파일러 최적화를 제한합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_ReadBarrier](../intrinsics/readbarrier.md)\
[_WriteBarrier](../intrinsics/writebarrier.md)\
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[C++ 키워드](../cpp/keywords-cpp.md)
