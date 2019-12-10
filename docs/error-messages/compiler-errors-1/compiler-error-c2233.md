---
title: 컴파일러 오류 C2233
ms.date: 11/04/2016
f1_keywords:
- C2233
helpviewer_keywords:
- C2233
ms.assetid: 236bdf0b-9607-4f26-a249-d8def0b1333c
ms.openlocfilehash: 066f28bfaacd1ad2e7645822aef082e43e863327
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759258"
---
# <a name="compiler-error-c2233"></a>컴파일러 오류 C2233

' identifier ': 크기가 0 인 배열을 포함 하는 개체의 배열이 잘못 되었습니다.

배열의 각 개체는 하나 이상의 요소를 포함 해야 합니다.

다음 샘플에서는 C2233를 생성 합니다.

```cpp
// C2233.cpp
// compile with: /c
class A {
   char somearray[1];
};

class B {
   char zeroarray[];
};

A array[100];   // OK
B array2[100];   // C2233
```
