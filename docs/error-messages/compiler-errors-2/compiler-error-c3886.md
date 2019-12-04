---
title: 컴파일러 오류 C3886
ms.date: 11/04/2016
f1_keywords:
- C3886
helpviewer_keywords:
- C3886
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
ms.openlocfilehash: 2e7ba0fcc76d723cebb5b82315faf36313b1d7db
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736635"
---
# <a name="compiler-error-c3886"></a>컴파일러 오류 C3886

' var ': 리터럴 데이터 멤버를 초기화 해야 합니다.

[리터럴](../../extensions/literal-cpp-component-extensions.md) 변수는 declaraed 될 때 초기화 되어야 합니다.

다음 샘플에서는 C3886를 생성 합니다.

```cpp
// C3886.cpp
// compile with: /clr /c
ref struct Y1 {
   literal int staticConst;   // C3886
   literal int staticConst2 = 0;   // OK
};
```
