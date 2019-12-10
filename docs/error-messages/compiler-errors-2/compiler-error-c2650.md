---
title: 컴파일러 오류 C2650
ms.date: 11/04/2016
f1_keywords:
- C2650
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
ms.openlocfilehash: f71996c6d04d8be2101762fb0fb17634e6b25a1a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756138"
---
# <a name="compiler-error-c2650"></a>컴파일러 오류 C2650

' operator ': 가상 함수 일 수 없습니다.

`new` 또는 `delete` 연산자는 `virtual`선언 됩니다. 이러한 연산자는 `static` 멤버 함수 이며 `virtual`수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2650를 생성 합니다.

```cpp
// C2650.cpp
// compile with: /c
class A {
   virtual void* operator new( unsigned int );   // C2650
   // try the following line instead
   // void* operator new( unsigned int );
};
```
