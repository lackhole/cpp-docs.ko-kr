---
title: 컴파일러 오류 C2507
ms.date: 11/04/2016
f1_keywords:
- C2507
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
ms.openlocfilehash: 23433dccd7fc4f86c2e848359ac50c796fcccab0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746801"
---
# <a name="compiler-error-c2507"></a>컴파일러 오류 C2507

' identifier ': 기본 클래스에 가상 한정자가 너무 많습니다.

클래스 또는 구조체는 `virtual` 두 번 이상 선언 됩니다. 기본 클래스 목록에서 각 클래스에 대해 하나의 `virtual` 한정자만 나타날 수 있습니다.

다음 샘플에서는 C2507를 생성 합니다.

```cpp
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```
