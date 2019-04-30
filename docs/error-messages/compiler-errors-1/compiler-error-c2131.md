---
title: 컴파일러 오류 C2131
ms.date: 02/28/2019
f1_keywords:
- C2131
helpviewer_keywords:
- C2131
ms.openlocfilehash: 19bdf73efa82e624382446c94642ceddac00bf2e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397590"
---
# <a name="compiler-error-c2131"></a>컴파일러 오류 C2131

> 식이 상수로 계산 되지 않았습니다.

식으로 선언 **상수** 또는 **constexpr** 컴파일 타임에 상수로 평가 되지 않았습니다. 컴파일러는 사용 되는 지점에서 식의 값을 결정할 수 있어야 합니다.

## <a name="example"></a>예제

이 예제에서는 C2131, 오류 및 해결 방법에 발생 하는 방법을 보여 줍니다.

```cpp
// c2131.cpp
// compile by using: cl /EHsc /W4 /c c2131.cpp

struct test
{
    static const int array_size; // To fix, init array_size here.
    int size_array[array_size];  // C2131
};

const int test::array_size = 42;
```

```Output
c2131.cpp
c2131.cpp(7): error C2131: expression did not evaluate to a constant
c2131.cpp(7): note: failure was caused by non-constant arguments or reference to a non-constant symbol
c2131.cpp(7): note: see usage of 'array_size'
```

## <a name="see-also"></a>참고자료

[const](../../cpp/const-cpp.md)<br/>
[constexpr](../../cpp/constexpr-cpp.md)<br/>
