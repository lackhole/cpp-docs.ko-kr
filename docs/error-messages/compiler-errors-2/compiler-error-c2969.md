---
title: 컴파일러 오류 C2969
ms.date: 11/04/2016
f1_keywords:
- C2969
helpviewer_keywords:
- C2969
ms.assetid: e4ea3d66-b937-4b2c-b42a-96e03fb11579
ms.openlocfilehash: 1330babe92266a6bc410084b4a46ef75f83f0b7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256804"
---
# <a name="compiler-error-c2969"></a>컴파일러 오류 C2969

구문 오류: 'symbol': 멤버 함수 정의가 '}'로 끝나야 합니다.

템플릿 멤버 함수 정의에 짝이 맞지 않는 닫는 중괄호가 있습니다.

다음 샘플에서는 C2969를 생성합니다.

```
// C2969.cpp
// compile with: /c
class A {
   int i;
public:
   A(int i) {}
};

A anA(1);

class B {
   A a;
   B() : a(anA);   // C2969
   // try the following line instead
   // B() : a(anA) {}
};
```