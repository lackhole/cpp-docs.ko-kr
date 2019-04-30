---
title: 컴파일러 오류 C2047
ms.date: 11/04/2016
f1_keywords:
- C2047
helpviewer_keywords:
- C2047
ms.assetid: 686a5a81-3857-4753-84a0-5c2e7149cbee
ms.openlocfilehash: 50a8ce4ab9d88312b7f91ebb9df068a07fa21aa6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408877"
---
# <a name="compiler-error-c2047"></a>컴파일러 오류 C2047

기본값이 잘못되었습니다.

`default` 키워드는 `switch` 문에만 나타날 수 있습니다.

다음 샘플에서는 C2047을 생성합니다.

```
// C2047.cpp
int main() {
   int i = 0;
   default:   // C2047
   switch(i) {
      case 0:
      break;
   }
}
```

해결 방법:

```
// C2047b.cpp
int main() {
   int i = 0;
   switch(i) {
      case 0:
      break;
      default:
      break;
   }
}
```