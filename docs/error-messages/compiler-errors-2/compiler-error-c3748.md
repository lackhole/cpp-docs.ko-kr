---
title: 컴파일러 오류 C3748
ms.date: 11/04/2016
f1_keywords:
- C3748
helpviewer_keywords:
- C3748
ms.assetid: 6fe71a0a-dd93-4ce6-9729-b9616360cf34
ms.openlocfilehash: 1b7da734b72acfda4efd55c518b1cc356ff49cce
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761857"
---
# <a name="compiler-error-c3748"></a>컴파일러 오류 C3748

' interface ': 관리 되는 인터페이스가 이벤트를 발생 시킬 수 없습니다.

[__Event](../../cpp/event.md) 키워드는 인터페이스 안에 나타날 수 없습니다.

다음 샘플에서는 C3748를 생성 합니다.

```cpp
// C3748.cpp
__interface I {
// try the following line instead
// struct I {
   __event void f();   // C3748
};

int main() {
}
```
