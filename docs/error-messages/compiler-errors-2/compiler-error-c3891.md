---
title: 컴파일러 오류 C3891
ms.date: 11/04/2016
f1_keywords:
- C3891
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
ms.openlocfilehash: 74b8802a165ab3265cc0f1c6a0b33b31d3db401d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779913"
---
# <a name="compiler-error-c3891"></a>컴파일러 오류 C3891

'var': 리터럴 데이터 멤버는 l-value로 사용할 수 없습니다

A [리터럴](../../extensions/literal-cpp-component-extensions.md) 변수는 const 및 선언에서 초기화 한 후 해당 값을 변경할 수 없습니다.

다음 샘플에서는 C3891 오류가 생성 됩니다.

```
// C3891.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3891
}
```