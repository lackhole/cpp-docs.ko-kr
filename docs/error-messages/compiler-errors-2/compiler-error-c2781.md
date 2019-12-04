---
title: 컴파일러 오류 C2781
ms.date: 11/04/2016
f1_keywords:
- C2781
helpviewer_keywords:
- C2781
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
ms.openlocfilehash: ff5d3d322118d9e3e229b9302e57dc1075f80b9b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739924"
---
# <a name="compiler-error-c2781"></a>컴파일러 오류 C2781

' 선언 ': 하나 이상의 value1 인수가 필요 합니다. value2가 제공 되었습니다.

가변 매개 변수 목록을 사용 하는 함수 템플릿에 인수가 너무 적습니다.

다음 샘플에서는 C2781를 생성 합니다.

```cpp
// C2781.cpp
template<typename T>
void f(T, T, ...){}

int main() {
   f(1);   // C2781

   // try the following line instead
   f(1,1);
}
```
