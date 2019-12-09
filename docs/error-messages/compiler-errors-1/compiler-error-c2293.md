---
title: 컴파일러 오류 C2293
ms.date: 11/04/2016
f1_keywords:
- C2293
helpviewer_keywords:
- C2293
ms.assetid: 17e7b4e2-368b-4dd7-a01b-d82be60f8e56
ms.openlocfilehash: c2c3760bcc7fcc84f914424d16a937cb3e9a0b09
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759102"
---
# <a name="compiler-error-c2293"></a>컴파일러 오류 C2293

'identifier': 멤버 변수를 __based 지정자로 사용할 수 없습니다.

`__based` 한정자에 대한 지정자는 비멤버 포인터여야 합니다.

다음 샘플에서는 C2293을 생성합니다.

```cpp
// C2293.cpp
// compile with: /c
class A {
   static int *i;
   void __based(i) *bp;   // C2293
   void *bp2;   // OK
};
```
