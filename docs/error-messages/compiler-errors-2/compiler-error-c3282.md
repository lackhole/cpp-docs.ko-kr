---
title: 컴파일러 오류 C3282
ms.date: 11/04/2016
f1_keywords:
- C3282
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
ms.openlocfilehash: 46be1f5250c1ca787909c48646d59180d62bd899
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58780849"
---
# <a name="compiler-error-c3282"></a>컴파일러 오류 C3282

관리 되는 제네릭 매개 변수 목록에만 나타날 수 있습니다 또는 WinRTclasses, 구조체 또는 함수

제네릭 매개 변수 목록이 잘못 사용되었습니다.  자세한 내용은 [제네릭](../../extensions/generics-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3282 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
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