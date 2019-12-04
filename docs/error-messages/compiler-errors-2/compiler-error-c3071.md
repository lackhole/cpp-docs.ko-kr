---
title: 컴파일러 오류 C3071
ms.date: 11/04/2016
f1_keywords:
- C3071
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
ms.openlocfilehash: 26a95b18970aef450c6fdf718910aa3f816fd778
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759414"
---
# <a name="compiler-error-c3071"></a>컴파일러 오류 C3071

'operator' 연산자는 ref 클래스 또는 값 형식의 인스턴스에만 적용할 수 있습니다.

CLR 연산자는 네이티브 형식에 사용할 수 없습니다. 이 연산자는 ref 클래스나 ref 구조체(값 형식)에 사용할 수 있으며 int 같은 네이티브 형식이나 네이티브 형식에 대한 별칭(예: System::Int32)에는 사용할 수 없습니다. 이러한 형식은 C++ 코드에서 네이티브 변수를 참조하는 방식으로 boxing될 수 없기 때문에, 이 연산자를 사용할 수 없습니다.

자세한 내용은 [추적 참조 연산자](../../extensions/tracking-reference-operator-cpp-component-extensions.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3071 오류가 발생하는 경우를 보여 줍니다.

```cpp
// C3071.cpp
// compile with: /clr
class N {};
ref struct R {};

int main() {
   N n;
   %n;   // C3071

   R r;
   R ^ r2 = %r;   // OK
}
```
