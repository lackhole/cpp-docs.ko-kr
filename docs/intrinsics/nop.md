---
title: __nop
ms.date: 09/02/2019
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: 4561bcb84063f3707825c8ca164867d41500e2db
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221664"
---
# <a name="__nop"></a>__nop

**Microsoft 전용**

작업을 수행 하지 않는 플랫폼별 기계어 코드를 생성 합니다.

## <a name="syntax"></a>구문

```C
void __nop();
```

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__nop`|x86, ARM, x64, ARM64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="remarks"></a>설명

`__nop` 함수는 `NOP` 컴퓨터 명령에 해당합니다. X86 및 x 64에 대 한 자세한 내용을 보려면 다음 문서를 검색 하십시오. "Intel 아키텍처 소프트웨어 개발자 설명서, 볼륨 2: " [Intel Corporation](https://software.intel.com/articles/intel-sdm) 사이트에서" 명령 집합 참조

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[__noop](../intrinsics/noop.md)
