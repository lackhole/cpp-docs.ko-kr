---
title: __faststorefence
ms.date: 09/02/2019
f1_keywords:
- __faststorefence_cpp
- __faststorefence
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
ms.openlocfilehash: d11a20666612fe1bca22f5d46b93e898dae375f6
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222184"
---
# <a name="__faststorefence"></a>__faststorefence

**Microsoft 전용**

로드 및 저장 메모리 참조를 모두 포함한 모든 이전 메모리 참조가 후속 메모리 참조 앞에 전역으로 표시되도록 보장합니다.

## <a name="syntax"></a>구문

```C
void __faststorefence();
```

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__faststorefence`|X64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

는 실행이 계속 되기 전에 내장 함수가 전역적으로 표시 되기 전에 발생 한 로드 및 저장 작업을 보장 하는 전체 메모리 장벽 명령 시퀀스를 생성 합니다. 효과는 모든 x64 플랫폼의 `_mm_mfence` 내장 함수와 유사하지만 속도가 더 빠릅니다.

AMD64 플랫폼에서는 이 루틴이 `sfence` 명령보다 더 빠른 store fence인 명령을 생성합니다. 시간이 중요한 코드의 경우 AMD64 플랫폼에서만 `_mm_sfence` 대신 이 내장 함수를 사용합니다. Intel x64 플랫폼에서는 `_mm_sfence` 명령이 더 빠릅니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
