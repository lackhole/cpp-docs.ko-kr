---
title: 컴파일러 오류 C2523
ms.date: 11/04/2016
f1_keywords:
- C2523
helpviewer_keywords:
- C2523
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
ms.openlocfilehash: 56b0f88949d7a7fa5af945ab5d03ee9a480d6d3f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746424"
---
# <a name="compiler-error-c2523"></a>컴파일러 오류 C2523

' class:: ~ identifier ': 소멸자/종료자 태그가 일치 하지 않습니다.

소멸자의 이름은 클래스 이름 앞에 물결표 (`~`)가와 야 합니다. 생성자와 소멸자는 클래스와 동일한 이름을 가진 유일한 멤버입니다.

다음 샘플에서는 C2523를 생성 합니다.

```cpp
// C2523.cpp
// compile with: /c
class A {
   ~B();    // C2523
   ~A();   // OK
};
```
