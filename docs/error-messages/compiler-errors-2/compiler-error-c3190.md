---
title: 컴파일러 오류 C3190
ms.date: 11/04/2016
f1_keywords:
- C3190
helpviewer_keywords:
- C3190
ms.assetid: 7c701afa-85a7-4f7a-8881-0662436ac244
ms.openlocfilehash: 1f30026d8f853aedc863bef4ecfa32b0bd3262b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382361"
---
# <a name="compiler-error-c3190"></a>컴파일러 오류 C3190

제공 된 템플릿 인수를 사용 하 여 ' 인스턴스화' 't y'의 모든 멤버 함수의 명시적 인스턴스화가 아닙니다.

컴파일러 함수 명시적 인스턴스화; 확인 시도를 감지 했습니다. 단, 제공 된 형식 인수를 가능한 기능의 일치 하지 않습니다.

다음 샘플에서는 C3190 오류가 생성 됩니다.

```
// C3190.cpp
// compile with: /LD
template<class T>
struct A {
   A(int x = 0) {
   }
   A(int x, int y) {
   }
};

template A<float>::A();   // C3190
// try the following line instead
// template A<int>::A(int);

struct Y {
   template<class T> void f(T);
};

template<class T> void Y::f(T) { }

template void Y::f(int,int);   // C3190

template<class OT> class X {
   template<class T> void f2(T,OT);
};

template<class OT> template<class T> void X<OT>::f2(T,OT) {}

template void X<float>::f2<int>(int,char);   // C3190
// try one of the following lines instead
// template void X<char>::f2(int, char);
// template void X<char>::f2<int>(int,char);
// template void X<char>::f2<>(int,char);
```