---
title: 컴파일러 오류 C3282
ms.date: 11/04/2016
f1_keywords:
- C3282
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
ms.openlocfilehash: a119f8a9482d3f49c98873fee6f54b434416ee48
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757581"
---
# <a name="compiler-error-c3282"></a>컴파일러 오류 C3282

제네릭 매개 변수 목록은 관리 되는 또는 WinRTclasses, 구조체 또는 함수에만 나타날 수 있습니다.

제네릭 매개 변수 목록이 잘못 사용되었습니다.  자세한 내용은 [제네릭](../../extensions/generics-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3282 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C3282.cpp
// compile with: /clr /c
generic <typename T> int x;   // C3282

ref struct GC0 {
   generic <typename T> int x;   // C3282
};

// OK
generic <typename T>
ref class M {};
```
