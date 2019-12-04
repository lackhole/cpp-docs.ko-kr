---
title: 컴파일러 오류 C2675
ms.date: 11/04/2016
f1_keywords:
- C2675
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
ms.openlocfilehash: 0b7b81ce7314fbad02d6873403fc5cf1bdd54709
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760376"
---
# <a name="compiler-error-c2675"></a>컴파일러 오류 C2675

단항 ' operator ': ' type '은이 연산자를 정의 하지 않거나 미리 정의 된 연산자에 허용 되는 형식으로의 변환을 정의 하지 않습니다.

C2675은 단항 연산자를 사용 하는 경우에도 발생할 수 있으며, 형식이 연산자를 정의 하지 않거나 미리 정의 된 연산자에 허용 되는 형식으로의 변환을 정의 하지 않습니다. 연산자를 사용하려면 지정된 형식에 대해 오버로드하거나 연산자가 정의된 형식으로의 변환을 정의해야 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2675를 생성 합니다.

```cpp
// C2675.cpp
struct C {
   C(){}
} c;

struct D {
   D(){}
   void operator-(){}
} d;

int main() {
   -c;   // C2675
   -d;   // OK
}
```
