---
title: 컴파일러 경고(수준 3) C4637
ms.date: 11/04/2016
f1_keywords:
- C4637
helpviewer_keywords:
- C4637
ms.assetid: 5fd347c1-2de9-408f-9136-1bf1ff273622
ms.openlocfilehash: 80c55494a391922453f2d89ae26ee5f47dc433b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401699"
---
# <a name="compiler-warning-level-3-c4637"></a>컴파일러 경고(수준 3) C4637

XML 문서 주석 대상: \<포함 > 태그가 삭제 되었습니다.  이유

구문의 [ \<포함 >](../../build/reference/include-visual-cpp.md) 태그가 잘못 되었습니다.

다음 샘플에서는 C4637을 생성합니다.

```
// C4637.cpp
// compile with: /clr /doc /LD /W3
using namespace System;

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <include file="c:\davedata\jtest\xml_include.doc"/>
   // Try the following line instead:
   // /// <include file='xml_include.doc' path='MyDocs/MyMembers/*' />
   void MyMethod() {
   }
};   // C4637
```