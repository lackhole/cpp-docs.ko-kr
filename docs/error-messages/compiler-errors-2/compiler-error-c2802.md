---
title: 컴파일러 오류 C2802
ms.date: 11/04/2016
f1_keywords:
- C2802
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
ms.openlocfilehash: 12ce65def043a05f5f154130b64326797a974137
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758296"
---
# <a name="compiler-error-c2802"></a>컴파일러 오류 C2802

' operator operator ' 정적 멤버에 정식 매개 변수가 없습니다.

`static` 멤버 함수에 의해 선언 된 연산자에는 매개 변수가 하나 이상 있어야 합니다.

다음 샘플에서는 C2802를 생성 합니다.

```cpp
// C2802.cpp
// compile with: /clr /c
ref class A {
   static operator+ ();   // C2802
   static operator+ (A^, A^);   // OK
};
```
