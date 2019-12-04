---
title: 컴파일러 오류 C3919
ms.date: 11/04/2016
f1_keywords:
- C3919
helpviewer_keywords:
- C3919
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
ms.openlocfilehash: 78a42b264129ee365e664b1242c8aa58dd1244bd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758478"
---
# <a name="compiler-error-c3919"></a>컴파일러 오류 C3919

' event_method ': 함수는 ' type ' 형식 이어야 합니다.

이벤트 접근자 메서드가 올바르게 선언 되지 않았습니다.

이벤트에 대 한 자세한 내용은 [이벤트](../../extensions/event-cpp-component-extensions.md)를 참조 하세요.

다음 샘플에서는 C3919를 생성 합니다.

```cpp
// C3919.cpp
// compile with: /clr /c
using namespace System;
delegate void D(String^);
ref class R {
   event D^ e {
      int add(int);   // C3919
      int remove(int);   // C3919

      void add(D^);   // OK
      void remove(D^);   // OK
   }
};
```
