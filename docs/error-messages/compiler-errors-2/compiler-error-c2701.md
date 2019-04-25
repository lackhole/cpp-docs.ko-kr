---
title: 컴파일러 오류 C2701
ms.date: 11/04/2016
f1_keywords:
- C2701
helpviewer_keywords:
- C2701
ms.assetid: 31cf2ab7-ced9-4f75-aa51-e169e20407fb
ms.openlocfilehash: b16ddb16d98a81e53b29ff51e41d19073200a2e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161292"
---
# <a name="compiler-error-c2701"></a>컴파일러 오류 C2701

'function': 함수 템플릿을 로컬 클래스의 friend 일 수 없습니다

지역 클래스는 friend 함수는 템플릿 함수를 가질 수 없습니다.

다음 샘플에서는 C2701를 생성합니다.

```
// C2701.cpp
// compile with: /c
template<typename T>   // OK
void f1(const T &);

void MyFunction() {
   class MyClass {
      template<typename T> friend void f2(const T &);   // C2701
   };
}
```