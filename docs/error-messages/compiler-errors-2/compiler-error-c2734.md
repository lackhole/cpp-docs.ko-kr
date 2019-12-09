---
title: 컴파일러 오류 C2734
ms.date: 11/04/2016
f1_keywords:
- C2734
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
ms.openlocfilehash: a188948a6d7ea7902b2df548819ffb8c40486dbc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755774"
---
# <a name="compiler-error-c2734"></a>컴파일러 오류 C2734

' identifier ': extern이 아닌 경우에는 const 개체를 초기화 해야 합니다.

식별자는 `const` 선언 되었지만 초기화 되거나 `extern`되지 않습니다.

다음 샘플에서는 C2734를 생성 합니다.

```cpp
// C2734.cpp
const int j;   // C2734
extern const int i;   // OK, declared as extern
```
