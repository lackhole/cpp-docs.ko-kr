---
title: 컴파일러 오류 C2380
ms.date: 11/04/2016
f1_keywords:
- C2380
helpviewer_keywords:
- C2380
ms.assetid: 717b1e6e-ddfe-4bac-a5f3-7f9a4dcb1572
ms.openlocfilehash: ca249bc592bd66c2e461a37fdc18204077f51db2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745436"
---
# <a name="compiler-error-c2380"></a>컴파일러 오류 C2380

' identifier ' 앞의 형식 (반환 형식이 있는 생성자 또는 현재 클래스 이름에 대 한 잘못 된 재정의)

생성자는 값을 반환 하거나 클래스 이름을 다시 정의 합니다.

다음 샘플에서는 C2326을 생성합니다.

```cpp
// C2380.cpp
// compile with: /c
class C {
public:
   int C();   // C2380, specifies an int return
   int C;   // C2380, redefinition of i
   C();   // OK
};
```
