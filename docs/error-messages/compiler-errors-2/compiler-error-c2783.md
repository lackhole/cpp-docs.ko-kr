---
title: 컴파일러 오류 C2783
ms.date: 11/04/2016
f1_keywords:
- C2783
helpviewer_keywords:
- C2783
ms.assetid: 1ce94a11-bb8b-4be3-a222-f1f105da74b3
ms.openlocfilehash: 539eeebc39fa7fc061cc615f29d87d3e6bcfc5c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408435"
---
# <a name="compiler-error-c2783"></a>컴파일러 오류 C2783

'declaration': 'identifier'에 대 한 템플릿 인수를 추론할 수 없습니다

컴파일러는 템플릿 인수를 확인할 수 없습니다. 기본 인수는 템플릿 인수 추론을 사용할 수 없습니다.

다음 샘플에서는 C2783를 생성합니다.

```
// C2783.cpp
template<typename T1, typename T2>
T1 f(T2) {
   return 248;
}

int main() {
   f(1);   // C2783
   // try the following line instead
   int i = f<int>(1);
}
```

C2783은 제네릭을 사용할 때도 발생할 수 있습니다.

```
// C2783b.cpp
// compile with: /clr
using namespace System;
generic<typename T1, typename T2>
T1 gf(T2) {
   T1 t1 = safe_cast<T1>( Activator::CreateInstance(T1::typeid));
   return t1;
}

ref class MyClass{};

int main() {
   int i;
   i = gf(9);   // C2783

   // OK
   i = gf<int>(9);
}
```