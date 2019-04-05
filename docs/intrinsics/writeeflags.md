---
title: __writeeflags
ms.date: 11/04/2016
f1_keywords:
- __writeeflags
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
ms.openlocfilehash: 6679a3b16def3ed413c5cec2a4bb7d5fe5d732c8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030357"
---
# <a name="writeeflags"></a>__writeeflags

지정 된 값이 프로그램에 기록 상태 및 컨트롤 (EFLAGS) 등록 합니다.

## <a name="syntax"></a>구문

```
void __writeeflags(unsigned Value);
void __writeeflags(unsigned __int64 Value);
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*값*|[in] EFLAGS 레지스터에 쓸 값입니다. `Value` 매개 변수는 32 비트 및 64 비트는 32 비트 플랫폼에 대 한 장기 64 비트 플랫폼에 대 한 시간입니다.|

## <a name="remarks"></a>설명

이러한 루틴은 내장 함수로 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__writeeflags`|x86, x64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[__readeflags](../intrinsics/readeflags.md)