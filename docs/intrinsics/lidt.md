---
title: __lidt
ms.date: 09/02/2019
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 24778b761ada56830b155a2fc65e90f54ba729ed
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217512"
---
# <a name="__lidt"></a>__lidt

**Microsoft 전용**

지정 된 메모리 위치의 값을 사용 하 여 인터럽트 설명자 테이블 레지스터 (IDTR)를 로드 합니다.

## <a name="syntax"></a>구문

```C
void __lidt(void * Source);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*원본*|진행 IDTR에 복사할 값에 대 한 포인터입니다.|

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__lidt`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

함수 `__lidt` 는 `LIDT` 컴퓨터 명령과 같으며 커널 모드 에서만 사용할 수 있습니다. 자세한 내용을 보려면 다음 문서를 검색 하십시오. "Intel 아키텍처 소프트웨어 개발자 설명서, 볼륨 2: " [Intel Corporation](https://software.intel.com/articles/intel-sdm) 사이트에서" 명령 집합 참조

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[__sidt](../intrinsics/sidt.md)
