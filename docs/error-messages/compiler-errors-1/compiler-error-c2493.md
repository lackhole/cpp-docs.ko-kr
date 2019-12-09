---
title: 컴파일러 오류 C2493
ms.date: 11/04/2016
f1_keywords:
- C2493
helpviewer_keywords:
- C2493
ms.assetid: 68316cd5-682b-49c3-b6ea-23c4e5d296cf
ms.openlocfilehash: 17cee561a0ebb642de95a6fce5426871030e5606
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757048"
---
# <a name="compiler-error-c2493"></a>컴파일러 오류 C2493

__based 형식이 잘못 되었습니다.

`__based` 식은 포인터를 기반으로 해야 합니다.

다음 샘플에서는 C2493를 생성 합니다.

```cpp
// C2493.cpp
// compile with: /c
char mybase;
int __based(mybase) ptr;   // C2493

// OK
char * mybase;
int __based(mybase) * ptr;
```
