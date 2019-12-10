---
title: 컴파일러 오류 C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: e4952f4702d871ecf1c818b1fc7394e54a1a295f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743889"
---
# <a name="compiler-error-c2464"></a>컴파일러 오류 C2464

' identifier ': ' n e w '를 사용 하 여 참조를 할당할 수 없습니다.

`new` 연산자를 사용 하 여 참조 식별자를 할당 했습니다. 참조는 메모리 개체가 아니므로 `new` 포인터를 반환할 수 없습니다. 표준 변수 선언 구문을 사용 하 여 참조를 선언 합니다.

다음 샘플에서는 C2464를 생성 합니다.

```cpp
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```
