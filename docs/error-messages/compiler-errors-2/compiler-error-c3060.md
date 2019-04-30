---
title: 컴파일러 오류 C3060
ms.date: 11/04/2016
f1_keywords:
- C3060
helpviewer_keywords:
- C3060
ms.assetid: 6282bb92-0546-4b59-9435-d3840bf93bdb
ms.openlocfilehash: c77af7fa1220aa5211d480cddf3bf0979c642ade
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265544"
---
# <a name="compiler-error-c3060"></a>컴파일러 오류 C3060

'member': friend 함수는 클래스 내부에서 정규화된 이름을 사용하여 정의할 수 없으며 선언만 할 수 있습니다.

Friend 함수가 정규화된 이름을 사용하여 정의되었으며 이는 허용되지 않습니다.

다음 샘플에서는 C3060을 생성합니다.

```
// C3060.cpp
class A {
public:
   void func();
};

class C {
public:
   friend void A::func() { }   // C3060
   // Try the following line and the out of class definition:
   // friend void A::func();
};

// void A::func(){}
```