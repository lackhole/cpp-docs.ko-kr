---
title: 컴파일러 오류 C3217
ms.date: 11/04/2016
f1_keywords:
- C3217
helpviewer_keywords:
- C3217
ms.assetid: 99070417-c23a-4d82-bdd2-04be1a07adea
ms.openlocfilehash: bcb63c7025f0addda546379947e2e1f5c3afc545
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311659"
---
# <a name="compiler-error-c3217"></a>컴파일러 오류 C3217

'param': 제네릭 매개 변수는 이 선언에서 제약을 받을 수 없습니다.

제약 조건의 형식이 잘못되었습니다. 제약 조건 제네릭 매개 변수는 제네릭 클래스 템플릿 매개 변수와 일치해야 합니다.

다음 샘플에서는 C3217을 생성합니다.

```
// C3217.cpp
// compile with: /clr
interface struct A {};

generic <class T>
ref class C {
   generic <class T1>
   where T : A   // C3217
   void f();
};
```

다음 샘플에는 가능한 해결 방법을 보여 줍니다.

```
// C3217b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
ref class C {
   generic <class T1>
   where T1 : A
   void f();
};
```