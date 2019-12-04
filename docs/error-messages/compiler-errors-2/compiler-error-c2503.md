---
title: 컴파일러 오류 C2503
ms.date: 11/04/2016
f1_keywords:
- C2503
helpviewer_keywords:
- C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
ms.openlocfilehash: 4cfe574f79eae2e45dc62315245a1b8b773d04df
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746905"
---
# <a name="compiler-error-c2503"></a>컴파일러 오류 C2503

' class ': 기본 클래스는 크기가 0 인 배열을 포함할 수 없습니다.

기본 클래스 또는 구조체에 크기가 0 인 배열이 포함 되어 있습니다. 클래스의 배열에는 하나 이상의 요소가 있어야 합니다.

다음 샘플에서는 C2503를 생성 합니다.

```cpp
// C2503.cpp
// compile with: /c
class A {
   public:
   int array [];
};

class B : A {};    // C2503

class C {
public:
   int array [10];
};

class D : C {};
```
