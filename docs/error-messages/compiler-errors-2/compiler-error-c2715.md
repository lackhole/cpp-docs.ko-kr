---
title: 컴파일러 오류 C2715
ms.date: 11/04/2016
f1_keywords:
- C2715
helpviewer_keywords:
- C2715
ms.assetid: c81567a7-5b65-468f-aaf9-835f91e468e4
ms.openlocfilehash: 0f0df136952e09d26fbf43104bbf13b001c87255
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386761"
---
# <a name="compiler-error-c2715"></a>컴파일러 오류 C2715

'type': throw 또는이 형식을 catch 할 수 없습니다.

관리 코드에서 예외 처리를 사용 하는 경우 값 형식은 올바른 인수가 아닙니다 (참조 [예외 처리](../../extensions/exception-handling-cpp-component-extensions.md) 자세한).

```
// C2715a.cpp
// compile with: /clr
using namespace System;

value struct V {
   int i;
};

void f1() {
   V v;
   v.i = 10;
   throw v;   // C2715
   // try the following line instead
   // throw ((V^)v);
}

int main() {
   try {
      f1();
   }

   catch(V v) { if ( v.i == 10 ) {   // C2715
   // try the following line instead
   // catch(V^ pv) { if ( pv->i == 10 ) {
         Console::WriteLine("caught 10 - looks OK");
      }
      else {
         Console::WriteLine("catch looks bad");
      }
   }
   catch(...) {
      Console::WriteLine("catch looks REALLY bad");
   }
}
```
