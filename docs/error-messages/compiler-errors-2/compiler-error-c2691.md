---
title: 컴파일러 오류 C2691
ms.date: 11/04/2016
f1_keywords:
- C2691
helpviewer_keywords:
- C2691
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
ms.openlocfilehash: 73fd3188fd1ee4c95d8444bea0f3c05beefa478f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760232"
---
# <a name="compiler-error-c2691"></a>컴파일러 오류 C2691

' 데이터 형식 ': 관리 되는 또는 WinRTarray에는이 요소 형식을 사용할 수 없습니다.

관리되는 배열 또는 WinRT 배열의 요소 형식은 값 형식이나 참조 형식일 수 있습니다.

다음 샘플에서는 C2691 오류가 발생하는 경우를 보여 줍니다.

```cpp
// C2691a.cpp
// compile with: /clr
class A {};

int main() {
   array<A>^ a1 = gcnew array<A>(20);   // C2691
   array<int>^ a2 = gcnew array<int>(20);   // value type OK
}
```
