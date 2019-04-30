---
title: 컴파일러 오류 C3634
ms.date: 11/04/2016
f1_keywords:
- C3634
helpviewer_keywords:
- C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
ms.openlocfilehash: 2acd76fee5e7ca309991e639044a45ea83ed112b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385669"
---
# <a name="compiler-error-c3634"></a>컴파일러 오류 C3634

'function': 관리 되는 또는 WinRTclass 추상 메서드를 정의할 수 없습니다.

WinRT 또는 관리되는 클래스에서 추상 메서드를 선언할 수 있지만 정의할 수는 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3634 오류가 발생하는 경우를 보여 줍니다.

```
// C3634.cpp
// compile with: /clr
ref class C {
   virtual void f() = 0;
};

void C::f() {   // C3634 - don't define managed class' pure virtual method
}
```
