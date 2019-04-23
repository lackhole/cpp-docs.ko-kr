---
title: 컴파일러 오류 C3771
ms.date: 11/04/2016
f1_keywords:
- C3771
helpviewer_keywords:
- C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
ms.openlocfilehash: 6b15d867bbaf66f511cbda200d692f5db4371ab3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026706"
---
# <a name="compiler-error-c3771"></a>컴파일러 오류 C3771

"identifier": 가장 가까운 네임스페이스 범위에서 friend 선언을 찾을 수 없습니다.

현재 네임스페이스 내에서 지정된 템플릿 *identifier* 에 대한 클래스 템플릿 선언을 찾을 수 없습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 템플릿 식별자에 대한 클래스 템플릿 선언이 현재 네임스페이스에 정의되어 있는지 또는 템플릿 식별자가 정규화된 이름인지 확인합니다.

## <a name="example"></a>예제

다음 코드 예제에서는 `NA`네임스페이스의 클래스 템플릿 및 함수를 선언하지만 `NB`네임스페이스의 friend 함수 템플릿을 선언하려고 합니다.

```cpp
// C3771.cpp
// compile with: /c

namespace NA {
template<class T> class A {
    void aFunction(T t) {};
    };
}
// using namespace NA;
namespace NB {
    class X {
        template<class T> friend void A<T>::aFunction(T); // C3771
// try the following line instead
//      template<class T> friend void NA::A<T>::aFunction(T);
// or try "using namespace NA;" instead.
    };
}
```

## <a name="see-also"></a>참고자료

[템플릿](../../cpp/templates-cpp.md)