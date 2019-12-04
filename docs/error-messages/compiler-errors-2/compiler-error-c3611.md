---
title: 컴파일러 오류 C3611
ms.date: 11/04/2016
f1_keywords:
- C3611
helpviewer_keywords:
- C3611
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
ms.openlocfilehash: 1fedcf406e101c87c5c831ef1b6d82fea0bbfa02
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755930"
---
# <a name="compiler-error-c3611"></a>컴파일러 오류 C3611

' function ': 봉인 된 함수에는 순수 지정자를 사용할 수 없습니다.

Sealed 함수가 잘못 선언 되었습니다.  자세한 내용은 [sealed](../../extensions/sealed-cpp-component-extensions.md)를 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3611를 생성 합니다.

```cpp
// C3611.cpp
// compile with: /clr /c

ref struct V {
   virtual void Test() sealed = 0;   // C3611
   virtual void Test2() sealed;   // OK
   virtual void Test3() = 0;   // OK
};
```
