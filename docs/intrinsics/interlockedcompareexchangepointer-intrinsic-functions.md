---
title: _InterlockedCompareExchangePointer Intrinsic Functions
ms.date: 11/04/2016
f1_keywords:
- _InterlockedCompareExchangePointer_HLERelease
- _InterlockedCompareExchangePointer_rel
- _InterlockedCompareExchangePointer_acq_cpp
- _InterlockedCompareExchangePointer
- _InterlockedCompareExchangePointer_cpp
- _InterlockedCompareExchangePointer_np
- _InterlockedCompareExchangePointer_rel_cpp
- _InterlockedCompareExchangePointer_HLEAcquire
- _InterlockedCompareExchangePointer_acq
- _InterlockedCompareExchangePointer_nf
helpviewer_keywords:
- InterlockedCompareExchangePointer_acq intrinsic
- _InterlockedCompareExchangePointer_rel intrinsic
- _InterlockedCompareExchangePointer_acq intrinsic
- InterlockedCompareExchangePointer_rel intrinsic
- InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_HLERelease intrinsic
- _InterlockedCompareExchangePointer_HLEAcquire intrinsic
- _InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_nf intrinsic
- _InterlockedCompareExchangePointer_np intrinsic
ms.assetid: 97fde59d-2bf9-42aa-a0fe-a5b6befdd44b
ms.openlocfilehash: 2db18c73f7765454d29e2dfdbd9408f62c51d32a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348733"
---
# <a name="interlockedcompareexchangepointer-intrinsic-functions"></a>_InterlockedCompareExchangePointer Intrinsic Functions

**Microsoft 전용**

`Exchange` 및 `Destination` 주소가 같으면 `Comparand` 주소에 `Destination` 주소를 저장하는 원자성 작업을 수행합니다.

## <a name="syntax"></a>구문

```
void * _InterlockedCompareExchangePointer (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_acq (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_HLEAcquire (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_HLERelease (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_nf (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_np (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
long _InterlockedCompareExchangePointer_rel (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
```

#### <a name="parameters"></a>매개 변수

*대상*<br/>
[out에서] 대상 값에 대 한 포인터에 대 한 포인터입니다. 부호는 무시됩니다.

*Exchange*<br/>
[in] Exchange 포인터입니다. 부호는 무시됩니다.

*비교 피연산자*<br/>
[in] 대상과 비교할 포인터입니다. 부호는 무시됩니다.

## <a name="return-value"></a>반환 값

반환 값은 대상의 초기 값입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|헤더|
|---------------|------------------|------------|
|`_InterlockedCompareExchangePointer`|x86, ARM, x64|\<intrin.h>|
|`_InterlockedCompareExchangePointer_acq`, `_InterlockedCompareExchangePointer_nf`, `_InterlockedCompareExchangePointer_rel`|ARM|\<iiintrin.h>|
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86, x64|\<immintrin.h>|

## <a name="remarks"></a>설명

`_InterlockedCompareExchangePointer`는 `Destination` 주소와 `Comparand` 주소의 원자성 비교를 수행합니다. `Destination` 주소가 `Comparand` 주소와 같으면 `Exchange`으로 지정된 주소에 `Destination` 주소가 저장됩니다. 그렇지 않으면 작업이 수행되지 않습니다.

`_InterlockedCompareExchangePointer` Win32 Windows SDK에 대 한 컴파일러 내장 지원을 제공 [_InterlockedCompareExchangePointer](https://msdn.microsoft.com/library/ff547863.aspx) 함수입니다.

사용 하는 방법의 예제 `_InterlockedCompareExchangePointer`를 참조 하세요 [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md)합니다.

ARM 플랫폼에서는 임계 영역의 시작 및 끝과 같은 위치에서 의미 체계를 획득하고 해제하려면 `_acq` 및 `_rel` 접미사가 포함된 내장 함수를 사용합니다. `_nf`("no fence"의 약어) 접미사가 포함된 ARM 내장 함수는 메모리 장벽으로 작동하지 않습니다.

`_np`("no prefetch"의 약어) 접미사가 포함된 내장 함수는 컴파일러가 가능한 프리페치 연산을 삽입하지 못하도록 차단합니다.

HLE(Hardware Lock Elision) 명령을 지원하는 Intel 플랫폼에서 `_HLEAcquire` 및 `_HLERelease` 접미사가 포함된 내장 함수는 하드웨어에서 잠금 쓰기 단계를 제거하여 성능을 향상시킬 수 있는 힌트를 프로세서에 포함합니다. HLE를 지원하지 않는 플랫폼에서 이러한 내장 함수를 호출하면 힌트는 무시됩니다.

이러한 루틴은 내장 함수로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)