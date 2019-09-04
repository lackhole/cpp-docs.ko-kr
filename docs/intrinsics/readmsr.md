---
title: __readmsr
ms.date: 09/02/2019
f1_keywords:
- __readmsr
helpviewer_keywords:
- Read Model Specific Register
- rdmsr instruction
- __readmsr intrinsic
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
ms.openlocfilehash: 4398b9d42369e3a914dbec1ed2d14cafecf58483
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222344"
---
# <a name="__readmsr"></a>__readmsr

**Microsoft 전용**

`rdmsr` 로`register` 지정 된 모델 특정 레지스터를 읽고 해당 값을 반환 하는 명령을 생성 합니다.

## <a name="syntax"></a>구문

```C
__int64 __readmsr(
   int register
);
```

### <a name="parameters"></a>매개 변수

*레지스터*\
진행 읽을 모델 관련 레지스터입니다.

## <a name="return-value"></a>반환 값

지정 된 레지스터의 값입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__readmsr`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

이 함수는 커널 모드 에서만 사용할 수 있으며 루틴은 내장 함수로만 사용할 수 있습니다.

자세한 내용은 AMD 설명서를 참조 하세요.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
