---
title: 컴파일러 오류 C3849
ms.date: 11/04/2016
f1_keywords:
- C3849
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
ms.openlocfilehash: ec6725472d31b0b2ade0cd73da4440036239fde3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381061"
---
# <a name="compiler-error-c3849"></a>컴파일러 오류 C3849

함수 형식을 호출할 'type' 형식의 식에 사용 가능한 연산자 오버 로드를 모든 숫자에 대 한 const 및/또는 volatile 한정자가 손실

지정된 된 const volatile 형식 사용 하 여 변수 멤버 같거나 큰 const volatile 한정자가 정의 된 함수를 호출할만 수 있습니다.

이 오류를 해결 하려면 적절 한 멤버 함수를 제공 합니다. 변환으로 인해 손실 한정 변환 const 또는 volatile 한정 된 개체에서 실행할 수 없습니다. 한정자를 얻을 수 있습니다 하지만 변환에 한정자가 손실 됩니다.

다음 샘플에서는 c3849:

```
// C3849.cpp
void glbFunc3(int i, char c)
{
   i;
}
typedef void (* pFunc3)(int, char);

void glbFunc2(int i)
{
   i;
}

typedef void (* pFunc2)(int);

void glbFunc1()
{
}
typedef void (* pFunc1)();

struct S4
{
   operator ()(int i)
   {
      i;
   }

   operator pFunc1() const
   {
      return &glbFunc1;
   }

   operator pFunc2() volatile
   {
      return &glbFunc2;
   }

   operator pFunc3()
   {
      return &glbFunc3;
   }

   // operator pFunc1() const volatile
   // {
   //    return &glbFunc1;
   // }
};

int main()
{
   // Cannot call any of the 4 overloads of "operator ()(.....)" and
   // "operator pFunc()" because none is declared as "const volatile"
   const volatile S4 s4;  // can only call cv member functions of S4
   s4();   // C3849 to resolve, uncomment member function
}
```