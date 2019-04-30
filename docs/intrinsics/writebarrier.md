---
title: _WriteBarrier
ms.date: 11/04/2016
f1_keywords:
- _WriteBarrier
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
ms.openlocfilehash: d2db648c9f41bd4f773f5bf152f31cf990a75c8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389972"
---
# <a name="writebarrier"></a>_WriteBarrier

**Microsoft 전용**

호출 시점 전체에서 메모리 액세스 작업을 다시 정렬할 수 있는 컴파일러 최적화를 제한합니다.

> [!CAUTION]
>  `_ReadBarrier`, `_WriteBarrier` 및 `_ReadWriteBarrier` 컴파일러 내장 함수 및 `MemoryBarrier` 매크로는 모두 더 이상 사용되지 않으므로 사용하면 안 됩니다. 스레드 간 통신 메커니즘을 같은 사용 [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) 하 고 [std:: atomic\<T >](../standard-library/atomic.md)에 정의 된 합니다 [ C++ 표준라이브러리](../standard-library/cpp-standard-library-reference.md). 하드웨어 액세스를 사용 하 여는 [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) 과 함께 컴파일러 옵션을 [volatile](../cpp/volatile-cpp.md) 키워드.

## <a name="syntax"></a>구문

```
void _WriteBarrier(void);
```

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`_WriteBarrier`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

`_WriteBarrier` 내장 함수는 호출 시점 전체에서 메모리 액세스 작업을 제거 또는 다시 정렬할 수 있는 컴파일러 최적화를 제한합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_ReadBarrier](../intrinsics/readbarrier.md)<br/>
[_ReadWriteBarrier](../intrinsics/readwritebarrier.md)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)