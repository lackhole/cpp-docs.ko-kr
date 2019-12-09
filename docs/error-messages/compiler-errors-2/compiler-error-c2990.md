---
title: 컴파일러 오류 C2990
ms.date: 11/04/2016
f1_keywords:
- C2990
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
ms.openlocfilehash: 1c58c2d5da0049ec670e11c930b397caec3cbbee
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751523"
---
# <a name="compiler-error-c2990"></a>컴파일러 오류 C2990

' class ': 클래스 형식으로 이미 선언 된 클래스 형식이 아닙니다.

제네릭이 아닌 또는 템플릿 클래스는 제네릭 또는 템플릿 클래스를 다시 정의 합니다. 헤더 파일의 충돌을 검사 합니다.

다음 샘플에서는 C2990를 생성 합니다.

```cpp
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

제네릭을 사용 하는 경우에도 C2990이 발생할 수 있습니다.

```cpp
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

C2990는 Visual Studio 2005 용 Microsoft C++ 컴파일러의 주요 변경 내용으로 인해 발생할 수도 있습니다. 이제 컴파일러에서 템플릿 사양과 관련 하 여 동일한 형식에 대 한 여러 선언이 동일 해야 합니다.

다음 샘플에서는 C2990를 생성 합니다.

```cpp
// C2990c.cpp
// compile with: /c
template<class T>
class A;

template<class T>
struct A2 {
   friend class A;   // C2990
};

// OK
template<class T>
struct B {
   template<class T>
   friend class A;
};
```
