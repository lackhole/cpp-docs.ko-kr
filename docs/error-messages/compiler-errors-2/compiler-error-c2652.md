---
title: 컴파일러 오류 C2652
ms.date: 11/04/2016
f1_keywords:
- C2652
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
ms.openlocfilehash: cedee3f1e3289aaf0ea38d75b6c812b61f891435
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756125"
---
# <a name="compiler-error-c2652"></a>컴파일러 오류 C2652

' identifier ': 복사 생성자가 잘못 되었습니다. 첫 번째 매개 변수는 ' identifier '가 아니어야 합니다.

복사 생성자의 첫 번째 매개 변수는 해당 매개 변수가 정의 된 클래스, 구조체 또는 공용 구조체와 동일한 형식입니다. 첫 번째 매개 변수는 형식에 대 한 참조가 될 수 있지만 형식 자체는 아닙니다.

다음 샘플에서는 C2651를 생성 합니다.

```cpp
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```
