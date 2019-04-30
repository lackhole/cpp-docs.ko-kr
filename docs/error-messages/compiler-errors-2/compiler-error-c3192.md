---
title: 컴파일러 오류 C3192
ms.date: 11/04/2016
f1_keywords:
- C3192
helpviewer_keywords:
- C3192
ms.assetid: 8b0083d4-706f-46f6-858a-e1d9af464cf8
ms.openlocfilehash: 685657857b2ed41c29c704633b07dc677fc32fc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382309"
---
# <a name="compiler-error-c3192"></a>컴파일러 오류 C3192

구문 오류: ' ^'는 접두사 연산자가 아닙니다 (했습니까 ' *'?)

핸들은 역참조 연산자로 사용할 수 없습니다.

다음 샘플에서는 C3192 오류가 생성 됩니다.

```
// C3192.cpp
// compile with: /clr
using namespace System;

ref class MyClass {
public:
   MyClass () {}
   MyClass(MyClass%) {}
};

int main() {
   MyClass ^ s = gcnew MyClass;
   MyClass b = ^s;   // C3192

   // OK
   MyClass b2 = *s;
}
```