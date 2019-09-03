---
title: fenv_access pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
ms.openlocfilehash: c8e66881bde12df28bf24e18230471cb4caca792
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218600"
---
# <a name="fenv_access-pragma"></a>fenv_access pragma

부동 소수점환경 플래그 테스트 및 모드변경을 변경할 수 있는 (설정) 또는 최적화를 사용 하지 않도록 설정 합니다.

## <a name="syntax"></a>구문

> **#pragma fenv_access (** { **on** | **off** } **)**

## <a name="remarks"></a>설명

기본적으로 **fenv_access** 는 **해제**되어 있습니다. 컴파일러가 부동 소수점 환경을 액세스 하거나 조작 하지 않는다고 가정할 수 있는 경우 여러 부동 소수점 코드 최적화를 수행할 수 있습니다. **Fenv_access** 를 **on** 으로 설정 하 여 코드가 부동 소수점 환경에 액세스 하 여 상태 플래그 또는 예외를 테스트 하거나 제어 모드 플래그를 설정 하는 것을 컴파일러에 알립니다. 컴파일러는 코드가 부동 소수점 환경에 일관 되 게 액세스할 수 있도록 이러한 최적화를 사용 하지 않도록 설정 합니다.

부동 소수점 동작에 대 한 자세한 내용은 [/fp (부동 소수점 동작 지정)](../build/reference/fp-specify-floating-point-behavior.md)를 참조 하세요.

**Fenv_access** 에 적용 되는 최적화의 종류는 다음과 같습니다.

- 전역 공통 하위 식 제거

- 코드 이동

- 상수 정리

다른 부동 소수점 pragma는 다음과 같습니다.

- [float_control](../preprocessor/float-control.md)

- [fp_contract](../preprocessor/fp-contract.md)

## <a name="examples"></a>예

이 예제에서는 **fenv_access** 를 **on** 으로 설정 하 여 24 비트 전체 자릿수에 대해 부동 소수점 제어 레지스터를 설정 합니다.

```cpp
// pragma_directive_fenv_access_x86.cpp
// compile with: /O2 /arch:IA32
// processor: x86
#include <stdio.h>
#include <float.h>
#include <errno.h>
#pragma fenv_access (on)

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=9.999999776482582e-03
```

이전 샘플에서 주석 `#pragma fenv_access (on)` 처리 하는 경우 컴파일러에서 컴파일 시간 평가를 수행 하 고 컨트롤 모드를 사용 하지 않으므로 출력은 다릅니다.

```cpp
// pragma_directive_fenv_access_2.cpp
// compile with: /O2 /arch:IA32
#include <stdio.h>
#include <float.h>

int main() {
   double z, b = 0.1, t = 0.1;
   unsigned int currentControl;
   errno_t err;

   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);
   if (err != 0) {
      printf_s("The function _controlfp_s failed!\n");
      return -1;
   }
   z = b * t;
   printf_s ("out=%.15e\n",z);
}
```

```Output
out=1.000000000000000e-02
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
