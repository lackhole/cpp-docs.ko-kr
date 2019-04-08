---
title: __svm_vmload
ms.date: 11/04/2016
f1_keywords:
- __svm_vmload
helpviewer_keywords:
- __svm_vmload intrinsic
- VMLOAD instruction
ms.assetid: b46a5592-db76-4ffc-8694-2f3494e28bed
ms.openlocfilehash: 282f1c005c7eb59b2c590c70b38233c88c664e07
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031156"
---
# <a name="svmvmload"></a>__svm_vmload

**Microsoft 전용**

지정 된 가상 컴퓨터 제어 블록 (VMCB)에서 프로세서 상태의 하위 집합을 로드합니다.

## <a name="syntax"></a>구문

```
void __svm_vmload(
   size_t VmcbPhysicalAddress
);
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*VmcbPhysicalAddress*|[in] 실제 주소는 VMCB입니다.|

## <a name="remarks"></a>설명

`__svm_vmload` 함수는 `VMLOAD` 컴퓨터 명령에 해당합니다. 이 함수는 게스트 운영 체제 및 해당 애플리케이션과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 자세한 내용은 문서에 대해 검색 "AMD64 아키텍처 프로그래머 수동 볼륨 2: 24593, 3.11, 수정 버전 번호를 문서화, system Programming "를 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) 사이트입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__svm_vmload`|x86, x64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_vmrun](../intrinsics/svm-vmrun.md)<br/>
[__svm_vmsave](../intrinsics/svm-vmsave.md)