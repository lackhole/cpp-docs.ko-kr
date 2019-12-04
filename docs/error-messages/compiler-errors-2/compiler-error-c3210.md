---
title: 컴파일러 오류 C3210
ms.date: 11/04/2016
f1_keywords:
- C3210
helpviewer_keywords:
- C3210
ms.assetid: c6e9d309-fabc-4e7d-b526-be20d9fe3f6a
ms.openlocfilehash: 513f08d4dddc37d36a240ee0d72b24383f951cdf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755124"
---
# <a name="compiler-error-c3210"></a>컴파일러 오류 C3210

' type ': 액세스 선언은 기본 클래스 멤버에만 적용할 수 있습니다.

[Using 선언이](../../cpp/using-declaration.md) 잘못 지정 되었습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3210를 생성 합니다.

```cpp
// C3210.cpp
// compile with: /c
struct A {
protected:
   int i;
};

struct B {
   using A::i;   // C3210
};

struct C : public A {
   using A::i;   // OK
};
```
