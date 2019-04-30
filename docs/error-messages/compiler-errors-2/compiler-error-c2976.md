---
title: 컴파일러 오류 C2976
ms.date: 11/04/2016
f1_keywords:
- C2976
helpviewer_keywords:
- C2976
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
ms.openlocfilehash: 02771d7419c58ee4f0b6d7db46ba91fde253d9a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395367"
---
# <a name="compiler-error-c2976"></a>컴파일러 오류 C2976

'identifier': 형식 인수가 너무 적습니다.

제네릭 또는 템플릿에 하나 이상의 실제 인수가 없습니다. 제네릭 또는 템플릿 선언을 확인하여 올바른 매개 변수 개수를 찾습니다.

이 오류는 템플릿 인수 없는 경우에 발생할 수 있습니다 C++ 표준 라이브러리 구성 요소입니다.

다음 샘플에서는 C2976 오류가 생성 됩니다.

```
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

C2976은 제네릭을 사용할 때도 발생할 수 있습니다.

```
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