---
title: __invlpg
ms.date: 09/02/2019
f1_keywords:
- __invlpg
- __invlpg_cpp
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
ms.openlocfilehash: ba8bd81498f805992336b0dc4163fe18fa157a2c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221890"
---
# <a name="__invlpg"></a>__invlpg

**Microsoft 전용**

주소에 의해 `invlpg` 가리키는 메모리와 연결 된 페이지의 TLB (translation 할당 준비 buffer)를 무효화 하는 x86 명령을 생성합니다.

## <a name="syntax"></a>구문

```C
void __invlpg(
   void* Address
);
```

### <a name="parameters"></a>매개 변수

*위치*\
진행 64 비트 주소입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__invlpg`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

내장 함수 `__invlpg` 는 권한 있는 명령을 내보내고, 권한 수준 (CPL)이 0 인 커널 모드 에서만 사용할 수 있습니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
