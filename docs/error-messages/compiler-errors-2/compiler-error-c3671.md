---
title: 컴파일러 오류 C3671
ms.date: 11/04/2016
f1_keywords:
- C3671
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
ms.openlocfilehash: c4534b11f3aedf638f69337fb6a7af778e086bb4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62215019"
---
# <a name="compiler-error-c3671"></a>컴파일러 오류 C3671

'function_1': 함수가 'function_2'를 재정의 하지 않습니다

명시적 재정의 구문은 사용 하는 경우 함수를 재정의 하지 않은 경우 컴파일러는 오류를 생성 합니다.  참조 [명시적으로 재정의](../../extensions/explicit-overrides-cpp-component-extensions.md) 자세한 내용은 합니다.

## <a name="example"></a>예제

다음 샘플 C3671를 생성합니다.

```
// C3671.cpp
// compile with: /clr /c
ref struct S {
   virtual void f();
};

ref struct S1 : S {
   virtual void f(int) new sealed = S::f;   // C3671
   virtual void f() new sealed = S::f;
};
```