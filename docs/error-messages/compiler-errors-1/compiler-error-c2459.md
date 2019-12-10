---
title: 컴파일러 오류 C2459
ms.date: 11/04/2016
f1_keywords:
- C2459
helpviewer_keywords:
- C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
ms.openlocfilehash: c49c348968f750c7e5c64ab9ef4f298d3fc74f67
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743993"
---
# <a name="compiler-error-c2459"></a>컴파일러 오류 C2459

' identifier ':을 (를) 정의 하는 중입니다. 익명 멤버로 추가할 수 없습니다.

클래스, 구조체 또는 공용 구조체가 익명 공용 구조체의 멤버에 의해 자체 범위에서 다시 정의 됩니다.

다음 샘플에서는 C2459를 생성 합니다.

```cpp
// C2459.cpp
// compile with: /c
class C {
   union { int C; };   // C2459
   union { int D; };
};
```
