---
title: 컴파일러 오류 C3648
ms.date: 11/04/2016
f1_keywords:
- C3648
helpviewer_keywords:
- C3648
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
ms.openlocfilehash: 3b26be9890bbbdf6276c61023e6867160528e236
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751835"
---
# <a name="compiler-error-c3648"></a>컴파일러 오류 C3648

이 명시적 재정의 구문에는/clr: oldSyntax가 필요 합니다.

최신 관리 되는 구문을 컴파일하는 경우 컴파일러에서 더 이상 지원 되지 않는 이전 버전에 대 한 명시적 재정의 구문을 발견 했습니다.

자세한 내용은 [명시적 재정의](../../extensions/explicit-overrides-cpp-component-extensions.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3648를 생성 합니다.

```cpp
// C3648.cpp
// compile with: /clr
public interface struct I {
   void f();
};

public ref struct R : I {
   virtual void I::f() {}   // C3648
   // try the following line instead
   // virtual void f() = I::f{}
};
```
