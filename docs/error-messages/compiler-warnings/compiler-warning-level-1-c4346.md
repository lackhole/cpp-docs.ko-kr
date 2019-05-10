---
title: 컴파일러 경고(수준 1) C4346
ms.date: 11/04/2016
f1_keywords:
- C4346
helpviewer_keywords:
- C4346
ms.assetid: 68ee562d-cca9-4a2a-9a1b-14ad1a1e7396
ms.openlocfilehash: 53381ca6e33321001299ce27bce550c5b2b8f59e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187220"
---
# <a name="compiler-warning-level-1-c4346"></a>컴파일러 경고(수준 1) C4346

'name': 종속 이름이 형식이 아닙니다.

합니다 [typename](../../cpp/typename.md) 키워드는 종속 이름이 형식으로 취급 하는 경우에 필요 합니다. 동일한 시각적 개체의 모든 버전에서 작동 하는 코드에 대 한 C++를 추가 `typename` 를 선언 합니다.

다음 샘플에서는 C4346을 생성합니다.

```
// C4346.cpp
// compile with: /WX /LD
template<class T>
struct C {
   T::X* x;   // C4346
   // try the following line instead
   // typename T::X* x;
};
```

다음 샘플에서는 다른 예를 보여 줍니다. 여기서는 **typename** 키워드를 사용 합니다.

```
// C4346b.cpp
// compile with: /LD /W1
template<class T>
const typename T::X& f(typename T::Z* p);   // Required in both places

template<class T, int N>
struct L{};

template<class T>
struct M : public L<typename T::Type, T::Value>
{   // required on type argument, not on non-type argument
   typedef typename T::X   Type;
   Type f();   // OK: "Type" is a type-specifer
   typename T::X g();   // typename required
   operator typename T::Z();   // typename required
};
```

이

```
// C4346c.cpp
// compile with: /LD /WX
struct Y {
   typedef int Y_t;
};

template<class T>
struct A {
   typedef Y A_t;
};

template<class T>
struct B {
   typedef /*typename*/ A<T>::A_t B_t;   // C4346 typename needed here
   typedef /*typename*/ B_t::Y_t  B_t2;   // typename also needed here
};
```