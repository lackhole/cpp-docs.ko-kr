---
title: __svm_vmrun
ms.date: 11/04/2016
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: 40e53b2ebd54fc109b47f3067e5f89ce50b327de
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041061"
---
# <a name="svmvmrun"></a>__svm_vmrun

**Microsoft 전용**

지정 된 가상 컴퓨터 제어 블록 (VMCB)에 해당 하는 가상 컴퓨터 게스트 코드의 실행을 시작 합니다.

## <a name="syntax"></a>구문

```
void __svm_vmrun(
   size_t VmcbPhysicalAddress
);
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*VmcbPhysicalAddress*|[in] 실제 주소는 VMCB입니다.|

## <a name="remarks"></a>설명

`__svm_vmrun` 함수를 사용 하 여 최소한의 정보는 VMCB에서 가상 컴퓨터 게스트 코드 실행을 시작 합니다. 사용 된 [__svm_vmsave](../intrinsics/svm-vmsave.md) 또는 [__svm_vmload](../intrinsics/svm-vmload.md) 을 복잡 한 인터럽트를 처리 하거나 다른 게스트도 전환 하는 자세한 정보가 필요한 경우 함수입니다.

`__svm_vmrun` 함수는 `VMRUN` 컴퓨터 명령에 해당합니다. 이 함수는 게스트 운영 체제 및 해당 애플리케이션과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 자세한 내용은 문서에 대해 검색 "AMD64 아키텍처 프로그래머 수동 볼륨 2: 24593, 3.11 이상에서 수정 버전 번호를 문서화, system Programming "를 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) 사이트입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__svm_vmrun`|x86, x64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_vmsave](../intrinsics/svm-vmsave.md)<br/>
[__svm_vmload](../intrinsics/svm-vmload.md)