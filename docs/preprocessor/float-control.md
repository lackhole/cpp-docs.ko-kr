---
title: float_control pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: aa8cdc07953405175c1753791ab53214d73ba516
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218572"
---
# <a name="float_control-pragma"></a>float_control pragma

함수의 부동 소수점 동작을 지정합니다.

## <a name="syntax"></a>구문

> **#pragma float_control**\
> **#pragma float_control (** { **precise** | **strict** | **except** } **,** { **on** | **off** } [ **, push** ] **)** \
> **#pragma float_control (** { **push** | **pop** } **)**

## <a name="options"></a>변수

**정확한** **strict (** **꺼짐**,꺼짐,푸시) |  |  | \
**정확**하 고 **strict**이거나 **except**일 수 있는 부동 소수점 동작을 지정 합니다. 자세한 내용은 [/fp(부동 소수점 동작 지정)](../build/reference/fp-specify-floating-point-behavior.md)를 참조하세요. 설정은 설정 하거나 **해제할**수 있습니다.

**Strict**인 경우 **strict** 와 **except** 모두에 대 한 설정이 **on** 또는 **off** 설정으로 지정 됩니다. **except** 가 **on**으로 설정 된 경우에 만을 **on** 으로 설정할 수 있습니다.

선택적 **푸시** 토큰이 추가 되 면 **float_control** 의 현재 설정이 내부 컴파일러 스택으로 푸시됩니다.

**누르기**\
현재 **float_control** 설정을 내부 컴파일러 스택에 푸시합니다.

**창을**\
내부 컴파일러 스택 맨 위에서 **float_control** 설정을 제거 하 고 새 **float_control** 설정을 만듭니다.

## <a name="remarks"></a>설명

**Float_control** 를 사용 하 여가 on으로 설정 되어 있으면 **정확도** 를 해제할 수 없습니다. 마찬가지로 [fenv_access](../preprocessor/fenv-access.md) 를 on으로 설정 하면 **precise** 를 끌 수 없습니다. **Float_control** pragma를 사용 하 여 strict 모델에서 fast model로 이동 하려면 다음 코드를 사용 합니다.

```cpp
#pragma float_control(except, off)
#pragma fenv_access(off)
#pragma float_control(precise, off)
```

**Float_control** pragma를 사용 하 여 빠른 모델에서 엄격한 모델로 이동 하려면 다음 코드를 사용 합니다.

```cpp
#pragma float_control(precise, on)
#pragma fenv_access(on)
#pragma float_control(except, on)
```

옵션을 지정 하지 않으면 **float_control** 는 영향을 주지 않습니다.

다른 부동 소수점 pragma는 다음과 같습니다.

- [fenv_access](../preprocessor/fenv-access.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="example"></a>예제

다음 샘플에서는 pragma **float_control**를 사용 하 여 오버플로 부동 소수점 예외를 catch 하는 방법을 보여 줍니다.

```cpp
// pragma_directive_float_control.cpp
// compile with: /EHa
#include <stdio.h>
#include <float.h>

double func( ) {
   return 1.1e75;
}

#pragma float_control (except, on)

int main( ) {
   float u[1];
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);
   if (err != 0)
      printf_s("_controlfp_s failed!\n");

   try  {
      u[0] = func();
      printf_s ("Fail");
      return(1);
   }

   catch (...)  {
      printf_s ("Pass");
      return(0);
   }
}
```

```Output
Pass
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
