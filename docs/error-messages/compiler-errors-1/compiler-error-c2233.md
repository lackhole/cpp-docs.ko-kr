---
title: 컴파일러 오류 C2233
ms.date: 11/04/2016
f1_keywords:
- C2233
helpviewer_keywords:
- C2233
ms.assetid: 236bdf0b-9607-4f26-a249-d8def0b1333c
ms.openlocfilehash: 7d96230f189a8f9371473d2da4df4e7be295ab03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375966"
---
# <a name="compiler-error-c2233"></a>컴파일러 오류 C2233

'identifier': 크기가 0 인 배열이 포함 된 개체의 배열을 올바르지 않습니다.

배열의 각 개체에 요소를 하나 이상 있어야 합니다.

다음 샘플에서는 C2233 오류가 생성 됩니다.

```
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