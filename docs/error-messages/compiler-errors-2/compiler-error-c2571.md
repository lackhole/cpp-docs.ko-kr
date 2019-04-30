---
title: 컴파일러 오류 C2571
ms.date: 11/04/2016
f1_keywords:
- C2571
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
ms.openlocfilehash: d7d4898e5f0b55c50a4c18cef053cc150394d7e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408584"
---
# <a name="compiler-error-c2571"></a>컴파일러 오류 C2571

'function': ' union'에서 가상 함수 일 수 없습니다

공용 구조체는 가상 함수를 사용 하 여 선언 됩니다. 클래스 또는 구조체에만 가상 함수를 선언할 수 있습니다.  가능한 해결 방법:

1. 클래스 또는 구조체를 공용 구조체를 변경 합니다.

1. 비가상 함수를 확인 합니다.

다음 샘플에서는 C2571 오류가 생성 됩니다.

```
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```