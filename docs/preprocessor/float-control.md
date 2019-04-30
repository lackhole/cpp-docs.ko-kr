---
title: float_control
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
ms.openlocfilehash: 8a7829252cebb726363c67c990a94d08b0d6467a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389218"
---
# <a name="floatcontrol"></a>float_control

함수의 부동 소수점 동작을 지정합니다.

## <a name="syntax"></a>구문

> **#pragma float_control** [ **(** [ *value* **,** *setting* [ **, push** ] ] | [ **push** | **pop** ] **)** ]

## <a name="options"></a>옵션

*value*, *setting* [, **push**]<br/>
부동 소수점 동작을 지정합니다. *값* 될 수 있습니다 **정확한**를 **엄격한**, 또는 **제외 하 고**입니다. 자세한 내용은 [/fp(부동 소수점 동작 지정)](../build/reference/fp-specify-floating-point-behavior.md)를 참조하세요. *설정을* 중일 수 있습니다 **온** 또는 **해제**합니다.

경우 *값* 는 **엄격한**, 둘 다에 대 한 설정을 **엄격한** 및 **제외 하 고** 붙습니다 *설정* . **제외 하 고** 로 설정할 수 있습니다 **에** 때 **정확한** 또는 **엄격한** 로 설정 됩니다 **에서**합니다.

경우 선택적 **푸시** 토큰이 추가 되 면 현재 설정에 대 한 *값* 내부 컴파일러 스택으로 푸시됩니다.

**push**<br/>
현재 푸시 **float_control** 내부 컴파일러 스택의 로그온 설정

**pop**<br/>
제거 합니다 **float_control** 내부 컴파일러 스택의 맨 위에서 설정 하 고이 새 **float_control** 설정 합니다.

## <a name="remarks"></a>설명

사용할 수 없습니다 **float_control** 변환할 **정확한** 해제 하는 경우 **제외 하 고** 켜져 합니다. 마찬가지로 **정확한** 때 설정할 수 없습니다 [fenv_access](../preprocessor/fenv-access.md) 켜져 있습니다. 사용 하 여 엄격한 모델에서 빠른 모델로 이동 하는 **float_control** pragma를 다음 코드를 사용 합니다.

```cpp
#pragma float_control(except, off)
#pragma fenv_access(off)
#pragma float_control(precise, off)
```

사용 하 여 엄격한 모델에서 빠른 모델로 이동 하려면 합니다 **float_control** pragma를 다음 코드를 사용 합니다.

```cpp
#pragma float_control(precise, on)
#pragma fenv_access(on)
#pragma float_control(except, on)
```

없음 옵션을 지정 하는 경우 **float_control** 영향을 주지 않습니다.

다른 부동 소수점 pragma는 다음과 같습니다.

- [fenv_access](../preprocessor/fenv-access.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="example"></a>예제

다음 샘플에 pragma를 사용 하 여 오버플로 부동 소수점 예외를 catch 하는 방법을 보여 줍니다 **float_control**합니다.

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

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
