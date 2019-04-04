---
title: 컴파일러 오류 C3828
ms.date: 11/04/2016
f1_keywords:
- C3828
helpviewer_keywords:
- C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
ms.openlocfilehash: f499bb2a8fd6d3148935daec89835b79d2ff5b49
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770553"
---
# <a name="compiler-error-c3828"></a>컴파일러 오류 C3828

'object type': 관리 되는 인스턴스를 만드는 동안 허용 되지 배치 인수 또는 WinRTclasses

관리 되는 형식 또는 Windows 런타임 형식의 개체를 만들 때 연산자의 배치 형식을 사용할 수 없습니다 [ref new, gcnew](../../extensions/ref-new-gcnew-cpp-component-extensions.md) 하거나 [새](../../cpp/new-operator-cpp.md)합니다.

다음 샘플에서는 C3828 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C3828a.cpp
// compile with: /clr
ref struct M {
};

ref struct N {
   static array<char>^ bytes = gcnew array<char>(256);
};

int main() {
   M ^m1 = new (&N::bytes) M();   // C3828
   // The following line fixes the error.
   // M ^m1 = gcnew M();
}
```