---
title: 컴파일러 오류 C2423
ms.date: 11/04/2016
f1_keywords:
- C2423
helpviewer_keywords:
- C2423
ms.assetid: 8797fb8b-b58b-4add-b6e6-2a9a3cd9084d
ms.openlocfilehash: 29203d3816f82bce95be656fdf71cb6536b325b9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744669"
---
# <a name="compiler-error-c2423"></a>컴파일러 오류 C2423

' number ': 소수 자릿수가 잘못 되었습니다.

인라인 어셈블리 코드는 1, 2, 4 또는 8이 아닌 숫자를 사용 하 여 레지스터의 크기를 조정 합니다.

다음 샘플에서는 C2423를 생성 합니다.

```cpp
// C2423.cpp
// processor: x86
int main() {
   _asm {
      lea EAX, [EAX*3]   // C2423
      lea EAX, [EAX+EAX*2]   // OK
   }
}
```
