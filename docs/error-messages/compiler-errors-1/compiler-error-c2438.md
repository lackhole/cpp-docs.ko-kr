---
title: 컴파일러 오류 C2438
ms.date: 11/04/2016
f1_keywords:
- C2438
helpviewer_keywords:
- C2438
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
ms.openlocfilehash: da6443f3f319c864b53f6d077e8bf99faffc5888
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744318"
---
# <a name="compiler-error-c2438"></a>컴파일러 오류 C2438

' identifier ': 생성자를 통해 정적 클래스 데이터를 초기화할 수 없습니다.

생성자는 클래스의 정적 멤버를 초기화 하는 데 사용 됩니다. 정적 멤버는 클래스 선언 외부의 정의에서 초기화 해야 합니다.

다음 샘플에서는 C2438를 생성 합니다.

```cpp
// C2438.cpp
struct X {
   X(int i) : j(i) {}   // C2438
   static int j;
};

int X::j;

int main() {
   X::j = 1;
}
```
