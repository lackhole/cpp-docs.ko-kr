---
title: 컴파일러 오류 C2469
ms.date: 11/04/2016
f1_keywords:
- C2469
helpviewer_keywords:
- C2469
ms.assetid: 3814bdff-581a-4d3e-8b47-8de6887cea69
ms.openlocfilehash: eafb3ed3a26fe127b39558542b6d415be65cefb7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743759"
---
# <a name="compiler-error-c2469"></a>컴파일러 오류 C2469

'operator': 'type' 개체를 할당할 수 없습니다.

연산자에 잘못된 형식이 전달되었습니다.

다음 샘플에서는 C2469를 생성합니다.

```cpp
// C2469.cpp
int main() {
   int *i = new void;   // C2469
   int *i = new int;   // OK
}
```
