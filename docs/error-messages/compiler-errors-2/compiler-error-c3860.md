---
title: 컴파일러 오류 C3860
ms.date: 11/04/2016
f1_keywords:
- C3860
helpviewer_keywords:
- C3860
ms.assetid: 1fb5110d-594e-4f1c-8773-888233af1313
ms.openlocfilehash: 38113ba9c75ab3e3e9b0ea058cb96e733a484f13
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757789"
---
# <a name="compiler-error-c3860"></a>컴파일러 오류 C3860

클래스 형식 이름 다음에 나오는 형식 인수 목록에는 형식 매개 변수 목록에 사용 된 순서로 매개 변수를 나열 해야 합니다.

제네릭 또는 템플릿 인수 목록의 형식이 잘못 되었습니다.

다음 샘플에서는 C3860를 생성 합니다.

```cpp
// C3860.cpp
// compile with: /LD
template <class T1, class T2>
struct A {
   void f();
};

template <class T2, class T1>
void A<T1, T2>::f() {}   // C3860
```

가능한 해결 방법:

```cpp
// C3860b.cpp
// compile with: /c
template <class T1, class T2>
struct A {
   void f();
};

template <class T2, class T1>
void A<T2, T1>::f() {}
```

제네릭을 사용 하는 경우에도 C3860이 발생할 수 있습니다.

```cpp
// C3860c.cpp
// compile with: /clr
generic<class T,class U>
ref struct GC {
   void f();
};

generic<class T, class U>
void GC<T,T>::f() {}   // C3860
```

가능한 해결 방법:

```cpp
// C3860d.cpp
// compile with: /clr /c
generic<class T,class U>
ref struct GC {
   void f();
};

generic<class T, class U>
void GC<T,U>::f() {}
```
