---
title: 컴파일러 오류 C2572
ms.date: 11/04/2016
f1_keywords:
- C2572
helpviewer_keywords:
- C2572
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
ms.openlocfilehash: 78402c054573de8c9860e96b6abe60ec5c3cfe38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395523"
---
# <a name="compiler-error-c2572"></a>컴파일러 오류 C2572

'class::member': 기본 매개 변수 재정의: 매개 변수 매개 변수

기본 매개 변수를 재정의할 수 없습니다. 필요한 경우 다른 값 매개 변수를 기본 매개 변수 왼쪽을 정의 하지 않아야 합니다.

다음 샘플에서는 C2572 오류가 생성 됩니다.

```
// C2572.cpp
// compile with: /c
void f(int i = 1);   // function declaration

// function definition
void f(int i = 1) {}   // C2572

// try the following line instead
// void f(int i) {}
```