---
title: __svm_vmsave
ms.date: 11/04/2016
f1_keywords:
- __svm_vmsave
helpviewer_keywords:
- VMSAVE instruction
- __svm_vmsave intrinsic
ms.assetid: 617a60bd-8514-4ba1-8066-bcf4dd481030
ms.openlocfilehash: d683a13f636db9683b4a7c8d075ad6c3c88c2aed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390193"
---
# <a name="svmvmsave"></a>__svm_vmsave

**Microsoft 전용**

지정 된 가상 컴퓨터 제어 블록 (VMCB)의 프로세서 상태 하위 집합을 저장 합니다.

## <a name="syntax"></a>구문

```
void __svm_vmsave(
   size_t VmcbPhysicalAddress
);
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*VmcbPhysicalAddress*|[in] 실제 주소는 VMCB입니다.|

## <a name="remarks"></a>설명

`__svm_vmsave` 함수는 `VMSAVE` 컴퓨터 명령에 해당합니다. 이 함수는 게스트 운영 체제 및 해당 애플리케이션과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 자세한 내용은 문서에 대해 검색 "AMD64 아키텍처 프로그래머 수동 볼륨 2: 24593, 3.11 이상에서 수정 버전 번호를 문서화, system Programming "를 [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) 사이트입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__svm_vmsave`|x86, x64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_vmrun](../intrinsics/svm-vmrun.md)<br/>
[__svm_vmload](../intrinsics/svm-vmload.md)