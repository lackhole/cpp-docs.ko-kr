---
title: 컴파일러 경고(수준 1) C4822
ms.date: 11/04/2016
f1_keywords:
- C4822
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
ms.openlocfilehash: f54f29fcbc6fb71033bc6d1d87c7ddb31622ee40
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051251"
---
# <a name="compiler-warning-level-1-c4822"></a>컴파일러 경고(수준 1) C4822

'member': 지역 클래스 멤버 함수에 본문이 없습니다.

지역 클래스 멤버 함수가 선언되었지만 클래스에서 정의되지 않았습니다. 지역 클래스 멤버 함수를 사용하려면 클래스에서 정의해야 합니다. 클래스에서 선언하고 클래스 외부에서 정의할 수 없습니다.

지역 클래스 멤버 함수에 대한 클래스 외부 정의는 오류가 됩니다.

다음 샘플에서는 C4822를 생성합니다.

```cpp
// C4822.cpp
// compile with: /W1
int main() {
   struct C {
      void func1(int);   // C4822
      // try the following line instead
      // void func1(int){}
  };
}
```