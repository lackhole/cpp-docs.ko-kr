---
title: __vmx_vmclear
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmclear
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
ms.openlocfilehash: 17e3e5c91a58894b25fc6b2a72f7d0056fa88119
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036539"
---
# <a name="vmxvmclear"></a>__vmx_vmclear

**Microsoft 전용**

지정 된 가상 머신 제어 구조 (VMCS)를 초기화 하 고 시작 상태로 설정 `Clear`합니다.

## <a name="syntax"></a>구문

```
unsigned char __vmx_vmclear(
   unsigned __int64 *VmcsPhysicalAddress
);
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*VmcsPhysicalAddress*|[in] 제거할 VMCS의 실제 주소를 포함 하는 64 비트 메모리 위치에 대 한 포인터입니다.|

## <a name="return-value"></a>반환 값

|값|의미|
|-----------|-------------|
|0|작업에 성공했습니다.|
|1|현재 VMCS의 `VM-instruction error field` 에서 사용할 수 있는 확장된 상태로 작업이 실패했습니다.|
|2|사용 가능한 상태 없이 작업이 실패했습니다.|

## <a name="remarks"></a>설명

응용 프로그램이 사용 하 여 VM 시작 작업을 수행할 수는 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 하거나 [__vmx_vmresume](../intrinsics/vmx-vmresume.md) 함수입니다. 합니다 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 함수는 시작 상태가 인 vmcs 에서만 사용할 수 있습니다 `Clear`, 및 [__vmx_vmresume](../intrinsics/vmx-vmresume.md) 함수는 시작 상태가 인 vmcs 에서만 사용할 수 있습니다 `Launched`합니다. 결과적으로 사용 합니다 [__vmx_vmclear](../intrinsics/vmx-vmclear.md) 에 VMCS의 시작 상태를 설정 하는 함수 `Clear`합니다. 사용 된 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 첫 번째 VM 시작 작업에 대 한 함수 및 [__vmx_vmresume](../intrinsics/vmx-vmresume.md) 이후 VM 시작 작업에 대 한 함수입니다.

`__vmx_vmclear` 함수는 `VMCLEAR` 컴퓨터 명령에 해당합니다. 이 함수는 게스트 운영 체제 및 해당 애플리케이션과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 자세한 내용은 "Intel 가상화 기술 사양에 대 한는 IA-32 Intel 아키텍처" 문서를 검색에서 숫자 C97063-002를 문서화 합니다 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 사이트입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__vmx_vmclear`|X64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)<br/>
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)