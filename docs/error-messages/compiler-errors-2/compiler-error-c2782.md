---
title: 컴파일러 오류 C2782
ms.date: 11/04/2016
f1_keywords:
- C2782
helpviewer_keywords:
- C2782
ms.assetid: 8b685422-294d-4f64-9f3d-c14eaf03a93d
ms.openlocfilehash: c779a9789f532a5d623401058b9ea7e268ede17d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739729"
---
# <a name="compiler-error-c2782"></a>컴파일러 오류 C2782

' 선언 ': ' identifier ' 템플릿 매개 변수가 모호 합니다.

컴파일러가 템플릿 인수의 형식을 확인할 수 없습니다.

다음 샘플에서는 C2782를 생성 합니다.

```cpp
// C2782.cpp
template<typename T>
void f(T, T) {}

int main() {
   f(1, 'c');   // C2782
   // try the following line instead
   // f<int>(1, 'c');
}
```

제네릭을 사용 하는 경우에도 C2782이 발생할 수 있습니다.

```cpp
// C2782b.cpp
// compile with: /clr
generic<typename T> void gf(T, T) { }

int main() {
   gf(1, 'c'); // C2782
   // try the following line instead
   // gf<int>(1, 'c');
}
```
