---
title: 컴파일러 오류 C2976
ms.date: 11/04/2016
f1_keywords:
- C2976
helpviewer_keywords:
- C2976
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
ms.openlocfilehash: 76fd2363b6139bc1bc04aa4d4949a12522e31aa6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751796"
---
# <a name="compiler-error-c2976"></a>컴파일러 오류 C2976

' identifier ': 형식 인수가 너무 적습니다.

제네릭 또는 템플릿에 실제 인수가 하나 이상 없습니다. 제네릭 또는 템플릿 선언을 확인하여 올바른 매개 변수 개수를 찾습니다.

표준 라이브러리 구성 요소에 C++ 템플릿 인수가 누락 되어이 오류가 발생할 수 있습니다.

다음 샘플에서는 C2976를 생성 합니다.

```cpp
// C2976.cpp
template <class T>
struct TC {
   T t;
};
int main() {
   TC<>* t;   // C2976
   TC<int>* t2;   // OK
}
```

제네릭을 사용 하는 경우에도 C2976이 발생할 수 있습니다.

```cpp
// C2976b.cpp
// compile with: /clr
generic <class T>
ref struct GC {
   T t;
};

int main() {
   GC<>^ g;   // C2976
   GC<int>^ g2;   // OK
}
```
