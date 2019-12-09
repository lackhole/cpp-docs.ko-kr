---
title: 컴파일러 오류 C2502
ms.date: 11/04/2016
f1_keywords:
- C2502
helpviewer_keywords:
- C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
ms.openlocfilehash: 4ff3523ac803e7804ca56532631fe77b240c215d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746918"
---
# <a name="compiler-error-c2502"></a>컴파일러 오류 C2502

' identifier ': 기본 클래스에 액세스 한정자가 너무 많습니다.

기본 클래스에 액세스 한정자가 둘 이상 있습니다. 하나의 액세스 한정자 (`public`, `private`또는 `protected`)만 허용 됩니다.

다음 샘플에서는 C2502를 생성 합니다.

```cpp
// C2502.cpp
// compile with: /c
class A { };
class B { };
class C : private public A { };   // C2502

// OK
class D : private A {};
class E : public A, private B {};
```
