---
title: 컴파일러 오류 C2572
ms.date: 11/04/2016
f1_keywords:
- C2572
helpviewer_keywords:
- C2572
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
ms.openlocfilehash: ed2e9771d1a407b947926a6f0d8beeb51e724ac7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755488"
---
# <a name="compiler-error-c2572"></a>컴파일러 오류 C2572

' class:: member ': 기본 매개 변수 재정의: parameter param

기본 매개 변수는 다시 정의할 수 없습니다. 매개 변수에 다른 값을 지정 해야 하는 경우에는 기본 매개 변수를 정의 하지 않은 상태로 두어야 합니다.

다음 샘플에서는 C2572를 생성 합니다.

```cpp
// C2572.cpp
// compile with: /c
void f(int i = 1);   // function declaration

// function definition
void f(int i = 1) {}   // C2572

// try the following line instead
// void f(int i) {}
```
