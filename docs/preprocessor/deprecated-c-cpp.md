---
title: deprecated (C/C++)
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
ms.openlocfilehash: 262b23e6e4813a5e22bc3f4e7c9a18efb9988a7c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023317"
---
# <a name="deprecated-cc"></a>deprecated (C/C++)

**deprecated** pragma는 함수, 형식이나 식별자가 앞으로 혹은 미래의 출시버전에서는 더이상 지원 되지 않을 수 있다는 것을 나타냅니다.

> [!NOTE]
> C++14 `[[deprecated]]` 특성(attribute)에 대한 자세한 내용, Microsoft의 declspec 또는 pragma와 특성을 어느 상황에서 사용하는지에 대한 내용은 [C++ 표준 특성](../cpp/attributes.md)의 특성을 참조합니다.

## <a name="syntax"></a>구문

```
#pragma deprecated( identifier1 [,identifier2, ...] )
```

## <a name="remarks"></a>설명

컴파일러에서 **deprecated** 식별자를 발견 하는 경우, 컴파일러 경고 [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)가 발생 합니다.

매크로 이름을 사용하지 않을 수 있습니다. 매크로 이름을 따옴표로 감싸면 매크로가 적용됩니다.

**deprecated** pragma는 일치하는 모든 식별자에 반영되고 시그니처를 고려하지 않으므로 오버로드된 함수 사용을 중단하기 위해 사용할 때는 그리 좋지 않습니다. 범위 안에 함수 이름이 일치한다면 경고가 발생합니다.

가능하다면 **deprecated** pragma 대신 C++14에서 추가된 `[[deprecated]]` 특성을 사용하는것이 좋습니다. Microsoft 전용인 [__declspec (deprecated)](../cpp/deprecated-cpp.md) 선언 한정자를 사용하는 것도 **deprecated** pragma를 사용하는 것보다 많은 경우에 좋은선택 입니다. `[[deprecated]]` 특성과 `__declspec(deprecated)` 한정자를 사용하면 특정 형태의 오버로드 된 함수라 할 지라도 사용되지 않는 상태를 지정할 수 있습니다. 진단경고는 특성 또는 한정자가 적용되는 특정 오버로드 된 함수에 대한 참조에만 나타납니다.

## <a name="example"></a>예제

```cpp
// pragma_directive_deprecated.cpp
// compile with: /W3
#include <stdio.h>
void func1(void) {
}

void func2(void) {
}

int main() {
   func1();
   func2();
   #pragma deprecated(func1, func2)
   func1();   // C4995
   func2();   // C4995
}
```

다음 샘플에서는 클래스X를 사용하지 말것을 권장하는 방법을 보여 줍니다.

```cpp
// pragma_directive_deprecated2.cpp
// compile with: /W3
#pragma deprecated(X)
class X {  // C4995
public:
   void f(){}
};

int main() {
   X x;   // C4995
}
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)