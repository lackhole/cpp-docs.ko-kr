---
title: 컴파일러 경고(수준 3) C4570
ms.date: 11/04/2016
f1_keywords:
- C4570
helpviewer_keywords:
- C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
ms.openlocfilehash: 386d7c210c77469d67a75d66f7d8ae35c105b3b0
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767464"
---
# <a name="compiler-warning-level-3-c4570"></a>컴파일러 경고(수준 3) C4570

'type': 명시적으로 선언 되지 추상 않았지만 추상 함수를가지고

포함 하는 형식을 [추상](../../extensions/abstract-cpp-component-extensions.md) 함수 자체 될 추상으로 표시 되어야 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4570 오류가 발생 합니다.

```
// C4570.cpp
// compile with: /clr /W3 /c
ref struct X {   // C4570
// try the following line instead
// ref class X abstract {
   virtual void f() abstract;
};
```