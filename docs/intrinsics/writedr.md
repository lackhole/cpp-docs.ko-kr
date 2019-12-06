---
title: __writedr
ms.date: 09/02/2019
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: 473e7223e9974d0125e772c152ea85ae90b97342
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858063"
---
# <a name="__writedr"></a>__writedr

**Microsoft 전용**

지정 된 값을 지정 된 디버그 레지스터에 씁니다.

## <a name="syntax"></a>구문

```C
void __writedr(unsigned DebugRegister, unsigned DebugValue); /* x86 */
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue); /* x64 */
```

### <a name="parameters"></a>매개 변수

*Debugregister*\
진행 디버그 레지스터를 식별 하는 0부터 7 까지의 숫자입니다.

*Debugvalue*\
진행 디버그 레지스터에 쓸 값입니다.

## <a name="remarks"></a>주의

이러한 내장 함수는 커널 모드 에서만 사용할 수 있으며 루틴은 내장 함수 에서만 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__writedr`|x86, x64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[__readdr](../intrinsics/readdr.md)
