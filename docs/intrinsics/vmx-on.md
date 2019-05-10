---
title: __vmx_on
ms.date: 11/04/2016
f1_keywords:
- __vmx_on
helpviewer_keywords:
- VMXON instruction
- __vmx_on intrinsic
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
ms.openlocfilehash: de903eeeb29e3c194a36ccb4cb038ba89b8ea82f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390141"
---
# <a name="vmxon"></a>__vmx_on

**Microsoft 전용**

프로세서의 가상 머신 확장 (VMX) 작업을 활성화합니다.

## <a name="syntax"></a>구문

```
unsigned char __vmx_on(
   unsigned __int64 *VmsSupportPhysicalAddress
);
```

#### <a name="parameters"></a>매개 변수

*VmsSupportPhysicalAddress*<br/>
[in] 가상 머신 제어 구조 (VMCS)를 가리키는 64 비트 물리적 주소에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

|값|의미|
|-----------|-------------|
|0|작업에 성공했습니다.|
|1|현재 VMCS의 `VM-instruction error field` 에서 사용할 수 있는 확장된 상태로 작업이 실패했습니다.|
|2|사용 가능한 상태 없이 작업이 실패했습니다.|

## <a name="remarks"></a>설명

합니다 `__vmx_on` 에 해당 하는 함수는 `VMXON` 컴퓨터 명령입니다. 이 함수는 게스트 운영 체제 및 해당 애플리케이션과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 자세한 내용은 "Intel 가상화 기술 사양에 대 한는 IA-32 Intel 아키텍처" 문서를 검색에서 숫자 C97063-002를 문서화 합니다 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 사이트입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__vmx_on`|X64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)