---
title: __noop
ms.date: 09/02/2019
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 24ba85b1fbbba4491c03d5a81afae345228db3bd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217190"
---
# <a name="__noop"></a>__noop

**Microsoft 전용**

`__noop` 내장 함수는 함수를 무시 하도록 지정 합니다. 인수 목록은 구문 분석 되지만 인수에 대해서는 코드가 생성 되지 않습니다. 가변 개수의 인수를 사용 하는 전역 디버그 함수에서 사용 하기 위한 것입니다.

컴파일러는 컴파일 타임 `__noop` 에 내장 함수를 0으로 변환 합니다.

## <a name="example"></a>예제

다음 코드에서는를 사용 `__noop`하는 방법을 보여 줍니다.

```cpp
// compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

int main() {
   PRINT("\nhello\n");
}
```

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)\
[C++ 키워드](../cpp/keywords-cpp.md)
