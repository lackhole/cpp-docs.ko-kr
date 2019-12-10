---
title: 컴파일러 오류 C2048
ms.date: 11/04/2016
f1_keywords:
- C2048
helpviewer_keywords:
- C2048
ms.assetid: 44704726-85fc-42f0-afb9-194df8c4ca7c
ms.openlocfilehash: 039be85541a7cd3864187433e5b3299bca7d067e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740132"
---
# <a name="compiler-error-c2048"></a>컴파일러 오류 C2048

기본값이 둘 이상입니다.

`switch` 문에 `default` 레이블이 여러 개 포함되어 있습니다. 오류를 해결하려면 `default` 레이블 중 하나를 삭제합니다.

다음 샘플에서는 C2048을 생성합니다.

```cpp
// C2048.cpp
int main() {
   int a = 1;
   switch (a) {
      case 1:
         a = 0;
      default:
         a = 2;
      default:   // C2048
         a = 3;
   }
}
```

가능한 해결 방법:

```cpp
// C2048b.cpp
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
