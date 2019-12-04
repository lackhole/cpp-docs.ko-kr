---
title: 컴파일러 오류 C2695
ms.date: 11/04/2016
f1_keywords:
- C2695
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
ms.openlocfilehash: 6d46699a2036c4f45daf3c34802ddb6b44e554ff
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755215"
---
# <a name="compiler-error-c2695"></a>컴파일러 오류 C2695

' function1 ': 재정의 가상 함수는 ' function2 '과 호출 규칙만 다릅니다.

파생 클래스의 함수 시그니처는 기본 클래스의 함수를 재정의 하 고 호출 규칙을 변경할 수 없습니다.

다음 샘플에서는 C2695를 생성 합니다.

```cpp
// C2695.cpp
class C {
   virtual void __fastcall func();
};

class D : public C {
   virtual void __clrcall func();   // C2695
};
```
