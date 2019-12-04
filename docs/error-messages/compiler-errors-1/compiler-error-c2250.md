---
title: 컴파일러 오류 C2250
ms.date: 11/04/2016
f1_keywords:
- C2250
helpviewer_keywords:
- C2250
ms.assetid: f990986f-5c7d-4af4-a25c-b35540f1e217
ms.openlocfilehash: 472aabf00fecd000f274d97b5753ed8460ff867f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758868"
---
# <a name="compiler-error-c2250"></a>컴파일러 오류 C2250

' identifier ': ' class:: member '의 상속은 모호 합니다.

파생 클래스가 가상 기본 클래스의 가상 함수에 대해 둘 이상의 재정의를 상속 합니다. 이러한 재정의는 파생 클래스에서 모호 합니다.

다음 샘플에서는 C2286을 생성합니다.

```cpp
// C2250.cpp
// compile with: /c
// C2250 expected
struct V {
   virtual void vf();
};

struct A : virtual V {
   void vf();
};

struct B : virtual V {
   void vf();
};

struct D : A, B {
   // Uncomment the following line to resolve.
   // void vf();
};
```
