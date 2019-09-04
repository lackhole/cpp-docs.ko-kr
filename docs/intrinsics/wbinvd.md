---
title: __wbinvd
ms.date: 09/02/2019
f1_keywords:
- __wbinvd
helpviewer_keywords:
- __wbinvd intrinsic
- wbinvd instruction
ms.assetid: 628d0981-39e5-49e1-bd43-706d123af121
ms.openlocfilehash: fe888ef578f0c2e077911537d401890b63372a0b
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219377"
---
# <a name="__wbinvd"></a>__wbinvd

**Microsoft 전용**

Write Back 및 무효화할 Cache (`wbinvd`) 명령을 생성 합니다.

## <a name="syntax"></a>구문

```C
void __wbinvd(void);
```

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__wbinvd`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 함수는 CPL (권한 수준)이 0 인 커널 모드 에서만 사용할 수 있으며 루틴은 내장 함수로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
