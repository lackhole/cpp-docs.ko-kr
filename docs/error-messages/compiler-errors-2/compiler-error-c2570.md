---
title: 컴파일러 오류 C2570
ms.date: 11/04/2016
f1_keywords:
- C2570
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
ms.openlocfilehash: 6b9f94b1b17aad85aab37659565e6e0827b5a824
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755514"
---
# <a name="compiler-error-c2570"></a>컴파일러 오류 C2570

' identifier ': 공용 구조체에 기본 클래스를 사용할 수 없습니다.

Union은 클래스, 구조체 또는 공용 구조체에서 파생 됩니다. 이는 허용되지 않습니다. 대신 파생 형식을 클래스 또는 구조체로 선언 합니다.

다음 샘플에서는 C2570를 생성 합니다.

```cpp
// C2570.cpp
// compile with: /c
class base {};
union hasPubBase : public base {};   // C2570
union hasNoBase {};   // OK
```
