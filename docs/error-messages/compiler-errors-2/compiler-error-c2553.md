---
title: 컴파일러 오류 C2553
ms.date: 11/04/2016
f1_keywords:
- C2553
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
ms.openlocfilehash: aa3e97d576e994878ab5b080363c4c09b79f42ed
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756788"
---
# <a name="compiler-error-c2553"></a>컴파일러 오류 C2553

' base_function ': 재정의 가상 함수 반환 형식이 ' override_function '과 (와) 다릅니다.

파생 클래스의 함수가 기본 클래스의 가상 함수를 재정의 하려고 했지만 파생 클래스 함수의 반환 형식이 기본 클래스 함수와 동일 하지 않습니다.  재정의 함수 시그니처는 재정의 되는 함수의 시그니처와 일치 해야 합니다.

다음 샘플에서는 C2553를 생성 합니다.

```cpp
// C2553.cpp
// compile with: /clr /c
ref struct C {
   virtual void f();
};

ref struct D : C {
   virtual int f() override ;   // C2553

   // try the following line instead
   // virtual void f() override;
};
```
