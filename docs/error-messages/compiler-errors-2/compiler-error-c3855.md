---
title: 컴파일러 오류 C3855
ms.date: 11/04/2016
f1_keywords:
- C3855
helpviewer_keywords:
- C3855
ms.assetid: ed90f8c0-4154-4243-b066-493913df5727
ms.openlocfilehash: 12ee1c6aa5f414a9cf3084831c956514593102c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265466"
---
# <a name="compiler-error-c3855"></a>컴파일러 오류 C3855

'class': 형식 매개 변수 'param' 선언과 호환 되지 않습니다.

컴파일러가는 비형식 템플릿 또는 서로 다른 이름 가진 제네릭 매개 변수를 찾았습니다. 템플릿 특수화의 정의에 지정 된 템플릿 매개 변수를 선언와 호환 되지 경우 발생할 수 있습니다.

다음 샘플에서는 C3855를 생성합니다.

```
// C3855.cpp
template <int N>
struct C {
   void f();
};

template <char N>
void C<N>::f() {}   // C3855
```

해결 방법:

```
// C3855b.cpp
// compile with: /c
template <int N>
struct C {
   void f();
};

template <int N>
void C<N>::f() {}
```

C3855는 제네릭을 사용할 때도 발생할 수 있습니다.

```
// C3855c.cpp
// compile with: /clr
generic <class T>
ref struct GC1 {
   generic <class U>
   ref struct GC2;
};

generic <class T>
generic <class U>
generic <class V>
ref struct GC1<T>::GC2 { };   // C3855
```

해결 방법:

```
// C3855d.cpp
// compile with: /clr /c
generic <class T>
ref struct GC1 {
   generic <class U>
   ref struct GC2;
};

generic <class T>
generic <class U>
ref struct GC1<T>::GC2 { };
```