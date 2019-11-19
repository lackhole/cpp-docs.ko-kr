---
title: 컴파일러 경고 (수준 3) C4280
ms.date: 11/04/2016
f1_keywords:
- C4280
helpviewer_keywords:
- C4280
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
ms.openlocfilehash: 9936aa7b6baf0c1f94186aa4785490897d8606e2
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051717"
---
# <a name="compiler-warning-level-3-c4280"></a>컴파일러 경고 (수준 3) C4280

' operator-> '는 ' type ' 형식을 통해 자체 재귀적입니다.

코드에서 > 자신을 호출 하는 **연산자** 를 잘못 허용 합니다.

다음 샘플에서는 C4280를 생성 합니다.

```cpp
// C4280.cpp
// compile with: /W3 /WX
struct A
{
   int z;
   A& operator ->();
};

void f(A y)
{
   int i = y->z; // C4280
}
```