---
title: 컴파일러 오류 C2671
ms.date: 11/04/2016
f1_keywords:
- C2671
helpviewer_keywords:
- C2671
ms.assetid: fc0ee40f-c8f3-408f-b89d-745d149c4169
ms.openlocfilehash: 57f4f2538fd02174f931faa2603a1388906d9944
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760402"
---
# <a name="compiler-error-c2671"></a>컴파일러 오류 C2671

' function ': 정적 멤버 함수에 ' this ' 포인터가 없습니다.

`static` 멤버 함수가 `this`에 액세스 하려고 했습니다.

다음 샘플에서는 C2671를 생성 합니다.

```cpp
// C2671.cpp
struct S {
   static S* const func() { return this; }  // C2671
};
```
