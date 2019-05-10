---
title: 컴파일러 오류 C2990
ms.date: 11/04/2016
f1_keywords:
- C2990
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
ms.openlocfilehash: 16c111a0fb8608615abaee495680fa38920b6c77
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447349"
---
# <a name="compiler-error-c2990"></a>컴파일러 오류 C2990

'class': 비 클래스 형식으로 이미 클래스 형식으로 선언

비 제네릭 또는 템플릿 클래스는 제네릭 또는 템플릿 클래스를 재정의합니다. 충돌에 대 한 헤더 파일을 확인 합니다.

다음 샘플에서는 C2990를 생성합니다.

```
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

C2990은 제네릭을 사용할 때도 발생할 수 있습니다.

```
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

C2990도 Microsoft의 주요 변경으로 인해 발생할 수 있습니다 C++ Visual Studio 2005;에 대 한 컴파일러 컴파일러가 동일한 형식에 대 한 여러 선언이 템플릿 지정에 대해 동일 해야 합니다.

다음 샘플에서는 C2990를 생성합니다.

```
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