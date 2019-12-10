---
title: 컴파일러 오류 C2876
ms.date: 11/04/2016
f1_keywords:
- C2876
helpviewer_keywords:
- C2876
ms.assetid: 8b674bf1-f9f4-4a8e-8127-e884c1d1708f
ms.openlocfilehash: bb242c889d924612b5349ea06c19db954261b245
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736349"
---
# <a name="compiler-error-c2876"></a>컴파일러 오류 C2876

' class:: symbol ': 모든 오버 로드에 액세스할 수 없습니다.

기본 클래스에서 모든 오버 로드 된 형식의 함수는 파생 클래스에서 액세스할 수 있어야 합니다.

다음 샘플에서는 C2876를 생성 합니다.

```cpp
// C2876.cpp
// compile with: /c
class A {
public:
   double a(double);
private:
   int a(int);
};

class B : public A {
   using A::a;   // C2876 one overload is private in base class
};
```
