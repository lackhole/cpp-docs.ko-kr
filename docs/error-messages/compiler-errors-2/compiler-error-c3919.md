---
title: 컴파일러 오류 C3919
ms.date: 11/04/2016
f1_keywords:
- C3919
helpviewer_keywords:
- C3919
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
ms.openlocfilehash: 05ac2fc9258a078f352b6012e64e86fe4b70c3f0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777189"
---
# <a name="compiler-error-c3919"></a>컴파일러 오류 C3919

'event_method': 함수는 'type '형식이 있어야 합니다.

이벤트 접근자 메서드를 제대로 선언 되지 않았습니다.

이벤트에 대 한 자세한 내용은 참조 하세요. [이벤트](../../extensions/event-cpp-component-extensions.md)합니다.

다음 샘플에서는 C3919 오류가 생성 됩니다.

```
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