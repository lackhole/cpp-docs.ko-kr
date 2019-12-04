---
title: 컴파일러 오류 C2767
ms.date: 11/04/2016
f1_keywords:
- C2767
helpviewer_keywords:
- C2767
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
ms.openlocfilehash: 259e8a58abfa2dc5eacaa6c9f6e3d47b852f5c1f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759817"
---
# <a name="compiler-error-c2767"></a>컴파일러 오류 C2767

관리 또는 WinRTarray 차원이 일치 하지 않습니다. N 개의 인수가 필요 합니다 (제공 됨).

WinRT 또는 관리되는 배열 선언의 형식이 잘못되었습니다. 자세한 내용은 [배열](../../extensions/arrays-cpp-component-extensions.md)을 참조하세요.

다음 샘플에서는 C2767 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C2767.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>(2,3); // C2767
   array<int> ^p2 = new array<int>(2);   // OK
}
```
