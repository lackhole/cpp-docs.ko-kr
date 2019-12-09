---
title: 컴파일러 오류 C3050
ms.date: 11/04/2016
f1_keywords:
- C3050
helpviewer_keywords:
- C3050
ms.assetid: ee090a0b-29cc-4215-a2f9-d82af79b8e82
ms.openlocfilehash: f8ab53974ac59de235a36e56991d2ef89f06be59
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761275"
---
# <a name="compiler-error-c3050"></a>컴파일러 오류 C3050

'type1': ref 클래스는 'type1'에서 상속될 수 없습니다.

`System::ValueType` 이 참조 형식에 대한 기본 클래스가 될 수 없습니다.

다음 샘플에서는 C3050을 생성합니다.

```cpp
// C3050.cpp
// compile with: /clr /LD
ref struct X : System::ValueType {};   // C3050
ref struct Y {};   // OK
```
