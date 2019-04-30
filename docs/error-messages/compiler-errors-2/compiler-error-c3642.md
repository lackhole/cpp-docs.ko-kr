---
title: 컴파일러 오류 C3642
ms.date: 11/04/2016
f1_keywords:
- C3642
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
ms.openlocfilehash: d524c49075c400caa345dd26ed681734ea0cfb94
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385623"
---
# <a name="compiler-error-c3642"></a>컴파일러 오류 C3642

' return_type/args ': __clrcall 네이티브 코드에서 호출 규칙을 사용 하 여 함수를 호출할 수 없습니다.

로 표시 된 함수는 [__clrcall](../../cpp/clrcall.md) 호출 규칙의 네이티브 (비관리) 코드에서 호출할 수 없습니다.

*return_type/args* 은 함수의 이름 또는 형식의 `__clrcall` 함수를 호출 하는 것입니다.  형식에는 함수 포인터를 통해 호출할 때 사용 됩니다.

네이티브 컨텍스트에서 관리 되는 함수를 호출 하려면 호출 하는 "래퍼" 함수를 추가할 수 있습니다는 `__clrcall` 함수입니다. 또는 CLR 마샬링 메커니즘;를 사용할 수 있습니다. 참조 [방법: 함수 포인터를 사용 하 여 PInvoke 마샬링할](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md) 자세한 내용은 합니다.

다음 샘플에서는 C3642를 생성합니다.

```
// C3642.cpp
// compile with: /clr
using namespace System;
struct S {
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall
      Console::WriteLine(s);
   }
   void Test2(char * s) {
      Test(gcnew String(s));
   }
};

#pragma unmanaged
int main() {
   S s;
   s.Test("abc");   // C3642
   s.Test2("abc");   // OK
}
```