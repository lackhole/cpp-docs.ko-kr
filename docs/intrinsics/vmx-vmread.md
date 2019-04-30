---
title: __vmx_vmread
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmread
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
ms.openlocfilehash: 5c7b72ba3bf1bd60324704b774bcedaf5612240f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390050"
---
# <a name="vmxvmread"></a>__vmx_vmread

**Microsoft 전용**

현재 가상 머신 제어 구조 (VMCS)에 지정된 된 필드를 읽고 지정된 된 위치에 배치 합니다.

## <a name="syntax"></a>구문

```
unsigned char __vmx_vmread(
   size_t Field,
   size_t *FieldValue
);
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*필드*|[in] VMCS의 필드는 읽기입니다.|
|*FieldValue*|[in] 지정 하 여 VMCS 필드에서 읽은 값을 저장할 위치에 대 한 포인터를 `Field` 매개 변수입니다.|

## <a name="return-value"></a>반환 값

|값|의미|
|-----------|-------------|
|0|작업에 성공했습니다.|
|1|현재 VMCS의 `VM-instruction error field` 에서 사용할 수 있는 확장된 상태로 작업이 실패했습니다.|
|2|사용 가능한 상태 없이 작업이 실패했습니다.|

## <a name="remarks"></a>설명

`__vmx_vmread` 함수는 `VMREAD` 컴퓨터 명령에 해당합니다. 값을 `Field` 매개 변수는 Intel 설명서에 설명 된 인코딩된 필드 인덱스입니다. 자세한 내용은 "Intel 가상화 기술 사양에 대 한는 IA-32 Intel 아키텍처" 문서를 검색에서 숫자 C97063-002, 문서를 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 사이트를 다음 문서의 부록 C를 참조 하세요. .

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__vmx_vmread`|X64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)