---
title: 컴파일러 오류 C2944
ms.date: 11/04/2016
f1_keywords:
- C2944
helpviewer_keywords:
- C2944
ms.assetid: f209e668-e72f-442a-a438-8c4ff43a404a
ms.openlocfilehash: 542f7def550632a29fcb7ae28825b32b8c26f17d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755384"
---
# <a name="compiler-error-c2944"></a>컴파일러 오류 C2944

'class': type-class-id가 템플릿의 값 인수로 재정의되었습니다.

제네릭 또는 템플릿 클래스를 기호 대신 템플릿 값 인수로 사용할 수 없습니다.

다음 샘플에서는 C2944를 생성합니다.

```cpp
// C2944.cpp
// compile with: /c
template<class T>
class TC { };

template <int TC<int> > struct X1 { };   // C2944

template <class T > struct X2 {};
```

C2944는 제네릭을 사용하는 경우에도 발생할 수 있습니다.

```cpp
// C2944b.cpp
// compile with: /clr /c
generic<class T>
ref class GC {};

template <int GC<int> > struct X2 { };   // C2944
template <class T> struct X3 {};   // OK
```
