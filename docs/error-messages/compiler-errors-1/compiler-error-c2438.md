---
title: 컴파일러 오류 C2438
ms.date: 11/04/2016
f1_keywords:
- C2438
helpviewer_keywords:
- C2438
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
ms.openlocfilehash: b2861090b5f7629c7f0cd94ea38a99e888909258
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375758"
---
# <a name="compiler-error-c2438"></a>컴파일러 오류 C2438

'identifier': 생성자를 통해 정적 클래스 데이터를 초기화할 수 없습니다

생성자는 클래스의 정적 멤버 초기화에 사용 됩니다. 정적 멤버는 클래스 선언 밖에 정의에서 초기화 되어야 합니다.

다음 샘플에서는 C2438를 생성합니다.

```
// C2438.cpp
struct X {
   X(int i) : j(i) {}   // C2438
   static int j;
};

int X::j;

int main() {
   X::j = 1;
}
```