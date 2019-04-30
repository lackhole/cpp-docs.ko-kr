---
title: __lidt
ms.date: 11/04/2016
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 757309603af48820a17668cfe272bbeaad9239b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263687"
---
# <a name="lidt"></a>__lidt

**Microsoft 전용**

지정된 된 메모리 위치에 있는 값을 사용 하 여 인터럽트 설명자 테이블 레지스터 (IDTR)를 로드합니다.

## <a name="syntax"></a>구문

```
void __lidt(void * Source);
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*소스*|[in] IDTR 복사할 값에 대 한 포인터입니다.|

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__lidt`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

합니다 `__lidt` 함수는 동일 합니다 `LIDT` 컴퓨터 명령 및 커널 모드 에서만 사용할 수 있습니다. 자세한 내용은 문서에 대해 검색 "Intel 아키텍처 소프트웨어 개발자 설명서 볼륨 2: 명령 집합 참조를 "에 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 사이트입니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[__sidt](../intrinsics/sidt.md)