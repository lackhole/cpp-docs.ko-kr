---
title: 컴파일러 오류 C3274
ms.date: 11/04/2016
f1_keywords:
- C3274
helpviewer_keywords:
- C3274
ms.assetid: 1f03f18e-b569-48eb-9249-11c70122a305
ms.openlocfilehash: a44a7d471e7e079ee43afa8bf58fd590be2f4bf8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382218"
---
# <a name="compiler-error-c3274"></a>컴파일러 오류 C3274

짝이 되는 try 없이 __finally/finally만 있습니다.

[__finally](../../cpp/try-finally-statement.md) 또는 [finally](../../dotnet/finally.md) 문이 일치하는 `try`없이 발견되었습니다. 이를 해결하려면 `__finally` 문을 삭제하거나 `try` 에 대해 `__finally`문을 추가합니다.

다음 샘플에서는 C3274를 생성합니다.

```
// C3274.cpp
// compile with: /clr
// C3274 expected
using namespace System;
int main() {
   try {
      try {
         throw gcnew ApplicationException();
      }
      catch(...) {
         Console::Error->WriteLine(L"Caught an exception");
      }
      finally {
         Console::WriteLine(L"In finally");
      }
   } finally {
      Console::WriteLine(L"In finally");
   }

   // Uncomment the following 3 lines to resolve.
   // try {
   //   throw gcnew ApplicationException();
   // }

   finally {
      Console::WriteLine(L"In finally");
   }
   Console::WriteLine(L"**FAIL**");
}
```