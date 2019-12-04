---
title: 컴파일러 오류 C3153
ms.date: 11/04/2016
f1_keywords:
- C3153
helpviewer_keywords:
- C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
ms.openlocfilehash: 54fa7de8eb3df8d4b3695544c5285cc202275492
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745918"
---
# <a name="compiler-error-c3153"></a>컴파일러 오류 C3153

' interface ': 인터페이스의 인스턴스를 만들 수 없습니다.

인터페이스를 인스턴스화할 수 없습니다. 인터페이스의 멤버를 사용 하려면 인터페이스에서 클래스를 파생 시키고 인터페이스 멤버를 구현한 다음 멤버를 사용 합니다.

다음 샘플에서는 C3153를 생성 합니다.

```cpp
// C3153.cpp
// compile with: /clr
interface class A {
};

int main() {
   A^ a = gcnew A;   // C3153
}
```
