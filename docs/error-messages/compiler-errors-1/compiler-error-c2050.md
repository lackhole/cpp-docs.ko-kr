---
title: 컴파일러 오류 C2050
ms.date: 11/04/2016
f1_keywords:
- C2050
helpviewer_keywords:
- C2050
ms.assetid: 66aaed7d-00db-4ce1-a9d6-4447c1cf07ce
ms.openlocfilehash: 99091452c2fc845ba396d7a8b290c2c857146257
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408903"
---
# <a name="compiler-error-c2050"></a>컴파일러 오류 C2050

switch 식이 정수 계열이 아닙니다

`switch` 정수가 아닌 값으로 계산 되는 식입니다. 이 오류를 해결 하려면 switch 문에서 정수 계열 값만을 사용 합니다.

다음 샘플에서는 C2050 오류가 생성 됩니다.

```
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

해결 방법:

```
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