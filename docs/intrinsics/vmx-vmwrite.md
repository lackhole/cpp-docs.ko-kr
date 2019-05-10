---
title: __vmx_vmwrite
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmwrite
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
ms.openlocfilehash: e52b1f181f00ce013a111d1a5a62abeff544e20a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389985"
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite

**Microsoft 전용**

현재 가상 머신 제어 구조 (VMCS)에 지정된 된 필드를 지정된 된 값을 씁니다.

## <a name="syntax"></a>구문

```
unsigned char __vmx_vmwrite(
   size_t Field,
   size_t FieldValue
);
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*필드*|[in] 쓸 VMCS 필드입니다.|
|*FieldValue*|[in] VMCS 필드에 쓸 값입니다.|

## <a name="return-value"></a>반환 값

작업이 성공적으로 수행 하는 0입니다.

1에서 사용할 수 있는 확장 된 상태를 사용 하 여 작업이 실패 합니다 `VM-instruction error field` 현재 VMCS의 합니다.

2 사용 가능한 상태 없이 작업에 실패 했습니다.

## <a name="remarks"></a>설명

`__vmx_vmwrite` 함수는 `VMWRITE` 컴퓨터 명령에 해당합니다. 값을 `Field` 매개 변수는 Intel 설명서에 설명 된 인코딩된 필드 인덱스입니다. 자세한 내용은 "Intel 가상화 기술 사양에 대 한는 IA-32 Intel 아키텍처" 문서를 검색에서 숫자 C97063-002, 문서를 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 사이트 및 다음의 부록 C를 참조 하세요. 문서입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__vmx_vmwrite`|X64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmread](../intrinsics/vmx-vmread.md)