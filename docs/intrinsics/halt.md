---
title: __halt
ms.date: 09/02/2019
f1_keywords:
- __halt
- __halt_cpp
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
ms.openlocfilehash: 66f5e05e7673523966ef35ac743fc585930b511c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222156"
---
# <a name="__halt"></a>__halt

**Microsoft 전용**

사용 가능한 인터럽트, 비 마스크 해제 인터럽트 (NMI) 또는 다시 설정이 발생할 때까지 마이크로프로세서를 중단 합니다.

## <a name="syntax"></a>구문

```C
void __halt( void );
```

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__halt`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

함수 `__halt` 는 `HLT` 컴퓨터 명령과 같으며 커널 모드 에서만 사용할 수 있습니다. 자세한 내용을 보려면 다음 문서를 검색 하십시오. "Intel 아키텍처 소프트웨어 개발자 설명서, 볼륨 2: " [Intel Corporation](https://software.intel.com/articles/intel-sdm) 사이트에서" 명령 집합 참조

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
