---
title: 컴파일러 오류 C3240
ms.date: 11/04/2016
f1_keywords:
- C3240
helpviewer_keywords:
- C3240
ms.assetid: 1a8dc213-b80c-47ae-ada0-e9554b635d1e
ms.openlocfilehash: e38ac53d0473c4fe5daace0f8c674c06b2ae0161
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756385"
---
# <a name="compiler-error-c3240"></a>컴파일러 오류 C3240

' function ': ' type '의 오버 로드 되지 않은 추상 멤버 함수 여야 합니다.

기본 형식에 정의 된 함수가 포함 되어 있습니다. 함수는 virtual 이어야 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3240를 생성 합니다.

```cpp
// C3240.cpp
// compile with: /c
__interface I {
   void f();
};

struct A1 : I {
   void f() {}
};

struct A2 : I {
   void f() = 0;
};

template <class T>
struct A3 : T {
   void T::f() {}
};

template <class T>
struct A4 : T {
   void T::f() {}
};

A3<A1> x;   // C3240
A3<I> x2;
A4<A2> x3;
```
