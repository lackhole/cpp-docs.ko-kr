---
title: 컴파일러 경고(수준 2) C4356
ms.date: 11/04/2016
f1_keywords:
- C4356
helpviewer_keywords:
- C4356
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
ms.openlocfilehash: 218aac1cc98d9b119490a547d63b4b5ee83e53df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402465"
---
# <a name="compiler-warning-level-2-c4356"></a>컴파일러 경고(수준 2) C4356

'member': 파생된 클래스를 통해 정적 데이터 멤버를 초기화할 수 없습니다

정적 데이터 멤버의 초기화 형식이 잘못 되었습니다. 컴파일러가 초기화를 허용 합니다. 경고를 방지 하려면 기본 클래스를 통해 멤버를 초기화 합니다.

사용 합니다 [경고](../../preprocessor/warning.md) pragma를이 경고를 표시 합니다.

다음 샘플에서는 C4356 오류가 생성 됩니다.

```
// C4356.cpp
// compile with: /W2 /EHsc
#include <iostream>

template <class T>
class C {
   static int n;
};

class D : C<int> {};

int D::n = 0; // C4356
// try the following line instead
// int C<int>::n = 0;

class A {
public:
   static int n;
};

class B : public A {};

int B::n = 10;   // C4356
// try the following line instead
// int A::n = 99;

int main() {
   using namespace std;
   cout << B::n << endl;
}
```