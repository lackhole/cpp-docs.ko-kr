---
title: 컴파일러 오류 C2575
ms.date: 11/04/2016
f1_keywords:
- C2575
helpviewer_keywords:
- C2575
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
ms.openlocfilehash: 2737f9078e1c17358e3c975a5c3f8b6d211fd308
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165777"
---
# <a name="compiler-error-c2575"></a>컴파일러 오류 C2575

'identifier': 멤버 함수와 기본 가상 일 수 있습니다

전역 함수 또는 클래스 선언 `virtual`합니다. 이것은 허용되지 않습니다.

다음 샘플에서는 C2575 오류가 생성 됩니다.

```
// C2575.cpp
// compile with: /c
virtual void func() {}   // C2575

void func2() {}
struct A {
   virtual void func2(){}
};
```