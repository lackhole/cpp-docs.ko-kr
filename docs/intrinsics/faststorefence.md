---
title: __faststorefence
ms.date: 11/04/2016
f1_keywords:
- __faststorefence_cpp
- __faststorefence
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
ms.openlocfilehash: a0c8027f443a475b03521920e2e036e7ed4eaafb
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036697"
---
# <a name="faststorefence"></a>__faststorefence

**Microsoft 전용**

로드 및 저장 메모리 참조를 모두 포함한 모든 이전 메모리 참조가 후속 메모리 참조 앞에 전역으로 표시되도록 보장합니다.

## <a name="syntax"></a>구문

```
void __faststorefence();
```

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__faststorefence`|X64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 내장 함수 전에 실행된 load 및 store 작업이 실행이 계속되기 전 전역으로 표시되도록 보장하는 전체 메모리 장벽 명령 시퀀스를 생성합니다. 효과는 모든 x64 플랫폼의 `_mm_mfence` 내장 함수와 유사하지만 속도가 더 빠릅니다.

AMD64 플랫폼에서는 이 루틴이 `sfence` 명령보다 더 빠른 store fence인 명령을 생성합니다. 시간이 중요한 코드의 경우 AMD64 플랫폼에서만 `_mm_sfence` 대신 이 내장 함수를 사용합니다. Intel x64 플랫폼에서는 `_mm_sfence` 명령이 더 빠릅니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)