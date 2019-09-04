---
title: __svm_vmload
ms.date: 09/02/2019
f1_keywords:
- __svm_vmload
helpviewer_keywords:
- __svm_vmload intrinsic
- VMLOAD instruction
ms.assetid: b46a5592-db76-4ffc-8694-2f3494e28bed
ms.openlocfilehash: da6ca9786b9c7e5041b9a8ca908d567b16176436
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219806"
---
# <a name="__svm_vmload"></a>__svm_vmload

**Microsoft 전용**

지정 된 VMCB (가상 컴퓨터 제어 블록)에서 프로세서 상태의 하위 집합을 로드 합니다.

## <a name="syntax"></a>구문

```C
void __svm_vmload(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>매개 변수

*VmcbPhysicalAddress*\
진행 VMCB의 실제 주소입니다.

## <a name="remarks"></a>설명

`__svm_vmload` 함수는 `VMLOAD` 컴퓨터 명령에 해당합니다. 이 함수는 게스트 운영 체제 및 해당 애플리케이션과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 자세한 내용은 다음 문서를 검색 하십시오. "AMD64 아키텍처 프로그래머의 수동 볼륨 2: 시스템 프로그래밍 ( [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) 사이트에서 "문서 번호 24593, 수정 버전 3.11)

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__svm_vmload`|x86, x64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[__svm_vmrun](../intrinsics/svm-vmrun.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)
