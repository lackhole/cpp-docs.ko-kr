---
title: __svm_vmrun
ms.date: 09/02/2019
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: f23df894cc8ad1c270c4c0acbc97cab727e47d93
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219826"
---
# <a name="__svm_vmrun"></a>__svm_vmrun

**Microsoft 전용**

지정 된 VMCB (가상 컴퓨터 제어 블록)에 해당 하는 가상 컴퓨터 게스트 코드의 실행을 시작 합니다.

## <a name="syntax"></a>구문

```C
void __svm_vmrun(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>매개 변수

*VmcbPhysicalAddress*\
진행 VMCB의 실제 주소입니다.

## <a name="remarks"></a>설명

함수 `__svm_vmrun` 는 vmcb에서 최소 양의 정보를 사용 하 여 가상 컴퓨터 게스트 코드 실행을 시작 합니다. 복합 인터럽트를 처리 하는 데 추가 정보가 필요 하거나 다른 게스트로 전환 하려면 [__svm_vmsave](../intrinsics/svm-vmsave.md) 또는 [__svm_vmload](../intrinsics/svm-vmload.md) 함수를 사용 합니다.

`__svm_vmrun` 함수는 `VMRUN` 컴퓨터 명령에 해당합니다. 이 함수는 게스트 운영 체제 및 해당 애플리케이션과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 자세한 내용은 다음 문서를 검색 하십시오. "AMD64 아키텍처 프로그래머의 수동 볼륨 2: 시스템 프로그래밍 ( [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) 사이트에서 "문서 번호 24593, 수정 버전 3.11 이상).

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__svm_vmrun`|x86, x64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)\
[__svm_vmload](../intrinsics/svm-vmload.md)
