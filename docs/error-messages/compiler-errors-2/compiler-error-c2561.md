---
title: 컴파일러 오류 C2561
ms.date: 11/04/2016
f1_keywords:
- C2561
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
ms.openlocfilehash: b4a14be9cd32c752e2ab889417494e80b935e31b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755566"
---
# <a name="compiler-error-c2561"></a>컴파일러 오류 C2561

' identifier ': 함수는 값을 반환 해야 합니다.

함수가 값을 반환 하는 것으로 선언 되었지만 함수 정의에 `return` 문이 포함 되어 있지 않습니다.

이 오류는 잘못 된 함수 프로토타입이 원인일 수 있습니다.

1. 함수가 값을 반환 하지 않는 경우 반환 형식이 [void](../../cpp/void-cpp.md)인 함수를 선언 합니다.

1. 함수의 가능한 모든 분기가 프로토타입에서 선언 된 형식의 값을 반환 하는지 확인 합니다.

1. C++`AX` 레지스터에 반환 값을 저장 하는 인라인 어셈블리 루틴을 포함 하는 함수에는 return 문이 필요할 수 있습니다. `AX`의 값을 임시 변수에 복사 하 고 함수에서 해당 변수를 반환 합니다.

다음 샘플에서는 C2561를 생성 합니다.

```cpp
// C2561.cpp
int Test(int x) {
   if (x) {
      return;   // C2561
      // try the following line instead
      // return 1;
   }
   return 0;
}

int main() {
   Test(1);
}
```
