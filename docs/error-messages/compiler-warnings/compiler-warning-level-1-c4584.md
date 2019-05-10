---
title: 컴파일러 경고(수준 1) C4584
ms.date: 11/04/2016
f1_keywords:
- C4584
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
ms.openlocfilehash: 3c60575e766ea3490a40711fe26c3e402c41fbdd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397252"
---
# <a name="compiler-warning-level-1-c4584"></a>컴파일러 경고(수준 1) C4584

'class1': 기본 클래스 'class2' 이미 'class3'의 기본 클래스입니다.

클래스 정의에서 다른 상속 하는 중 두 개의 클래스에서 상속 됩니다. 예를 들어:

```
// C4584.cpp
// compile with: /W1 /LD
class A {
};

class B : public A {
};

class C : public A, public B { // C4584
};
```

이 경우에 경고가 발생 합니다. 클래스 C에 모두 클래스 A 및 B 또한 A. 클래스에서 상속 되는 클래스에서 상속 하므로 이 경고는 이러한 기본 클래스에서 멤버를 사용 하는 정규화 해야 하거나 참조 하는 클래스 멤버에 대 한 모호성으로 인해 컴파일러 오류를 생성할 알림으로 사용 됩니다.