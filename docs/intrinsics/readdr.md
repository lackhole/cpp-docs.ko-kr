---
title: __readdr
ms.date: 09/02/2019
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: fbaf9e761f9f1450ccd12dc378ab6e498aa0df08
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857881"
---
# <a name="__readdr"></a>__readdr

**Microsoft 전용**

지정 된 디버그 레지스터의 값을 읽습니다.

## <a name="syntax"></a>구문

```C
unsigned         __readdr(unsigned int DebugRegister); /* x86 */
unsigned __int64 __readdr(unsigned int DebugRegister); /* x64 */
```

### <a name="parameters"></a>매개 변수

*Debugregister*\
진행 디버그 레지스터를 식별 하는 0부터 7 까지의 상수입니다.

## <a name="return-value"></a>반환 값

지정 된 디버그 레지스터의 값입니다.

## <a name="remarks"></a>주의

이러한 내장 함수는 커널 모드 에서만 사용할 수 있으며 루틴은 내장 함수 에서만 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__readdr`|x86, x64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
