---
title: 컴파일러 오류 C3653
ms.date: 11/04/2016
f1_keywords:
- C3653
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
ms.openlocfilehash: 75e2c061190b24019491db7a625ecafb5ac82b6b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776650"
---
# <a name="compiler-error-c3653"></a>컴파일러 오류 C3653

'function': 명명된 된 재정의로 사용할 수 없습니다: 찾은; 재정의 되는 함수 함수를 사용 하 여 명시적으로 이름을 하 였는:: operator?

명시적 재정의 모든 인터페이스에서 찾을 수 없는 함수를 지정 합니다. 자세한 내용은 [명시적으로 재정의](../../extensions/explicit-overrides-cpp-component-extensions.md)합니다.

다음 샘플에서는 C3653를 생성합니다.

```
// C3653.cpp
// compile with: /clr
public interface struct I {
   void h();
};

public ref struct X : public I {
   virtual void f() new sealed = J {};   // C3653 no J in scope
   virtual void g() {}   // OK
   virtual void h() new sealed = I::h {};   // OK
};
```