---
title: 컴파일러 오류 C2139
ms.date: 11/04/2016
f1_keywords:
- C2139
helpviewer_keywords:
- C2139
ms.assetid: 31e047c0-5bf9-46c2-b6de-b627ea6a5768
ms.openlocfilehash: 38e2fd090f3a2b2222658c5fd491c84dd70fd5ea
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756424"
---
# <a name="compiler-error-c2139"></a>컴파일러 오류 C2139

' type ': 정의 되지 않은 클래스는 컴파일러 내장 형식 특성 ' 특성 '에 대 한 인수로 사용할 수 없습니다.

잘못 된 인수가 형식 특성에 전달 되었습니다.

자세한 내용은 [형식 특성에 대한 컴파일러 지원](../../extensions/compiler-support-for-type-traits-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C2139를 생성 합니다.

```cpp
// C2139.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

template <class T>
struct is_polymorphic {
   static const bool value = __is_polymorphic(T);
};

class C;
class D {};

class E {
public:
   virtual void Test() {}
};

int main() {
   cout << is_polymorphic<C>::value << endl;   // C2139
   cout << is_polymorphic<D>::value << endl;   // OK
   cout << is_polymorphic<E>::value << endl;   // OK
}
```
