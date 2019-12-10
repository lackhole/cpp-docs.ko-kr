---
title: 컴파일러 오류 C2050
ms.date: 11/04/2016
f1_keywords:
- C2050
helpviewer_keywords:
- C2050
ms.assetid: 66aaed7d-00db-4ce1-a9d6-4447c1cf07ce
ms.openlocfilehash: e3d100387264af4a3f9bba8b9934fc6ca1d0d5a6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739182"
---
# <a name="compiler-error-c2050"></a>컴파일러 오류 C2050

switch 식이 정수 계열이 아닙니다.

`switch` 식은 정수가 아닌 값으로 계산 됩니다. 이 오류를 해결 하려면 switch 문에서 정수 값만 사용 합니다.

다음 샘플에서는 C2050를 생성 합니다.

```cpp
// C2050.cpp
int main() {
   int a = 1;
   switch ("a") {   // C2050
      case 1:
         a = 0;
      default:
         a = 2;
   }
}
```

가능한 해결 방법:

```cpp
// C2050b.cpp
int main() {
   int a = 1;
   switch (a) {
      case 1:
         a = 0;
      default:
         a = 2;
   }
}
```
