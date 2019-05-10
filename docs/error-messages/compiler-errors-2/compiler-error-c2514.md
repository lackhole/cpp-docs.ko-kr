---
title: 컴파일러 오류 C2514
ms.date: 11/04/2016
f1_keywords:
- C2514
helpviewer_keywords:
- C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
ms.openlocfilehash: aef9df0718d013378f88c1a34d08d1b1e05e214c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243773"
---
# <a name="compiler-error-c2514"></a>컴파일러 오류 C2514

'class': 클래스에 생성자가 없습니다

클래스, 구조체 또는 공용 구조체에 생성자를 없습니다 인스턴스화해야 하는 데 사용 되는 매개 변수와 일치 하는 매개 변수 목록 사용 합니다.

클래스를 인스턴스화하려면 먼저 완벽 하 게 선언 되어야 합니다.

다음 샘플에서는 C2514를 생성합니다.

```
// C2514.cpp
// compile with: /c
class f;

class g {
public:
    g (int x);
};

class fmaker {
   f *func1() {
      return new f(2);   // C2514
   }

   g *func2() {
      return new g(2);   // OK
   }
};
```