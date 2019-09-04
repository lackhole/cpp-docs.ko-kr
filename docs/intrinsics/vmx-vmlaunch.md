---
title: __vmx_vmlaunch
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmlaunch
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
ms.openlocfilehash: 8d78e5181fdd43e10431e12d0cf540c8c9c2e719
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219555"
---
# <a name="__vmx_vmlaunch"></a>__vmx_vmlaunch

**Microsoft 전용**

현재 가상 컴퓨터 제어 구조 (VMCS)를 사용 하 여 .VMX이 아닌 작업 상태 (VM enter)에 호출 응용 프로그램을 배치 합니다.

## <a name="syntax"></a>구문

```C
unsigned char __vmx_vmlaunch(void);
```

## <a name="return-value"></a>반환 값

|값|의미|
|-----------|-------------|
|0|작업에 성공했습니다.|
|1|현재 VMCS의 `VM-instruction error field` 에서 사용할 수 있는 확장된 상태로 작업이 실패했습니다.|
|2|사용 가능한 상태 없이 작업이 실패했습니다.|

## <a name="remarks"></a>설명

응용 프로그램은 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 또는 [__vmx_vmlaunch](../intrinsics/vmx-vmresume.md) 함수를 사용 하 여 VM 입력 작업을 수행할 수 있습니다. [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 함수는 시작 상태가 `Clear`인 vmcs 에서만 사용할 수 있으며, [__vmx_vmlaunch](../intrinsics/vmx-vmresume.md) 함수는 시작 상태가 인 `Launched`vmcs 에서만 사용할 수 있습니다. 따라서 [__vmx_vmclear](../intrinsics/vmx-vmclear.md) 함수를 사용 하 여 vmcs의 시작 상태를로 `Clear`설정한 다음 첫 번째 vm에 대 한 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 함수를 사용 하 고 후속 vm에 대 한 [__vmx_vmlaunch](../intrinsics/vmx-vmresume.md) 함수를 사용 합니다. 작업도.

`__vmx_vmlaunch` 함수는 `VMLAUNCH` 컴퓨터 명령에 해당합니다. 이 함수는 게스트 운영 체제 및 해당 애플리케이션과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 자세한 내용을 보려면 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 사이트에서 "IA-32 Intel 아키텍처용 Intel 가상화 기술 사양" 문서 번호 C97063-002 문서를 검색 하십시오.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__vmx_vmlaunch`|X64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)\
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)
