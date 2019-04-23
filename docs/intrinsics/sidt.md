---
title: __sidt
ms.date: 11/04/2016
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: 88dbb4713577fcf224e1c5646bf4c38b2a1dfafe
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036762"
---
# <a name="sidt"></a>__sidt

**Microsoft 전용**

지정된 된 메모리 위치에 인터럽트 설명자 테이블 레지스터 (IDTR)의 값을 저장합니다.

## <a name="syntax"></a>구문

```
void __sidt(void * Destination);
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*대상*|[in] IDTR 저장 되어 있는 메모리 위치에 대 한 포인터입니다.|

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__sidt`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

`__sidt` 함수는 `SIDT` 컴퓨터 명령에 해당합니다. 자세한 내용은 문서에 대해 검색 "Intel 아키텍처 소프트웨어 개발자 설명서 볼륨 2: 명령 집합 참조를 "에 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 사이트입니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[__lidt](../intrinsics/lidt.md)