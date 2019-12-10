---
title: 컴파일러 오류 C3891
ms.date: 11/04/2016
f1_keywords:
- C3891
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
ms.openlocfilehash: 4b5ef8b837033a149455c040f748f479aa3f424d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736401"
---
# <a name="compiler-error-c3891"></a>컴파일러 오류 C3891

' var ': 리터럴 데이터 멤버를 l-value로 사용할 수 없습니다.

[리터럴](../../extensions/literal-cpp-component-extensions.md) 변수는 const 이며 선언에서 초기화 된 후에는 해당 값을 변경할 수 없습니다.

다음 샘플에서는 C3891를 생성 합니다.

```cpp
// C3891.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3891
}
```
