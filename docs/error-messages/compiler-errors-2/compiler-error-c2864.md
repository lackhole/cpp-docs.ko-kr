---
title: 컴파일러 오류 C2864
ms.date: 11/04/2016
f1_keywords:
- C2864
helpviewer_keywords:
- C2864
ms.assetid: d0ca2ad9-90a6-4aef-8511-98a3b414c102
ms.openlocfilehash: 9bfc18137df1a54530011a8ec3f7ea50b1d6c86a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227502"
---
# <a name="compiler-error-c2864"></a>컴파일러 오류 C2864

'variable' : in-class initializer를 사용하는 정적 데이터 멤버는 비휘발성 const 정수 계열 형식이어야 합니다.

`static`, `volatile`가 아니거나 정수 계열 형식이 아닌 것으로 정의된 `const` 데이터 멤버를 초기화하려면 멤버 정의 문을 사용합니다. 그러한 멤버는 선언에서 초기화할 수 없습니다.

이 샘플에서는 C2864를 생성합니다.

```
// C2864.cpp
// compile with: /c
class B  {
private:
   int a = 3;   // OK
   static int b = 3;   // C2864
   volatile static int c = 3;   // C2864
   volatile static const int d = 3;   // C2864
   const static long long e = 3;   // OK
   static const double f = 3.33;   // C2864
};
```

이 샘플에서는 C2864를 수정하는 방법을 보여 줍니다.

```
// C2864b.cpp
// compile with: /c
class C  {
private:
   int a = 3;
   static int b; // = 3; C2864
   volatile static int c; // = 3; C2864
   volatile static const int d; // = 3; C2864
   static const long long e = 3;
   static const double f; // = 3.33; C2864
};

// Initialize static volatile, non-const, or non-integral
// data members when defined, not when declared:
int C::b = 3;
volatile int C::c = 3;
volatile const int C::d = 3;
const double C::f = 3.33;
```