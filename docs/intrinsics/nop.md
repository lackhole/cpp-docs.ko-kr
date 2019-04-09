---
title: __nop
ms.date: 11/04/2016
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: 1e76110c1ef0c4b98c295578189eedc99d76eeb9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038250"
---
# <a name="nop"></a>__nop

**Microsoft 전용**

아무 작업도 수행 하는 플랫폼별 기계어 코드를 생성 합니다.

## <a name="syntax"></a>구문

```
void __nop();
```

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__nop`|x86, ARM, x64, ARM64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="remarks"></a>설명

`__nop` 함수는 `NOP` 컴퓨터 명령에 해당합니다. X86 및 x64에 대 한 자세한 내용은 문서에 대해 검색 "Intel 아키텍처 소프트웨어 개발자 설명서 볼륨 2: 명령 집합 참조를 "에 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 사이트입니다.

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[__noop](../intrinsics/noop.md)
