---
title: 컴파일러 오류 C2143
ms.date: 11/04/2016
f1_keywords:
- C2143
helpviewer_keywords:
- C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
ms.openlocfilehash: ed4bc7eea85e5263d59817082caed99bde3d75d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353484"
---
# <a name="compiler-error-c2143"></a>컴파일러 오류 C2143

구문 오류: 'token2' 전에 ' token1' 누락

컴파일러 특정 토큰 (즉, 공백 문자 이외의 언어 요소)를 예상 하 고 다른 토큰이 발견 합니다.

확인 합니다 [ C++ 언어 참조](../../cpp/cpp-language-reference.md) 코드 구문이 잘못 되지 않는 확인 합니다. 컴파일러 문제를 발생 시키는 줄을 발견 한 후이 오류를 보고, 때문에 여러 줄 코드의 오류를 확인 합니다.

C2143은 다양 한 상황에서 발생할 수 있습니다.

다음 예제와 같이 이름(`::`, `->` 및 `.`)을 정규화할 수 있는 연산자 다음에 키워드 `template`이 와야 하는 경우에 발생할 수 있습니다.

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143
    {
    };
};
```

기본적으로 C++는 `Ty::PutFuncType`이 템플릿이 아니라고 가정하기 때문에 다음 `<`는 보다 작음 기호로 해석됩니다.  꺾쇠 괄호로 올바르게 구문 분석될 수 있도록 `PutFuncType`이 템플릿임을 컴파일러에 명시적으로 알려야 합니다. 이 오류를 해결하려면 다음과 같이 종속 형식의 이름에서 `template` 키워드를 사용합니다.

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct
    {
    };
};
```

C2143 발생할 수 있습니다 때 **/clr** 되 고 `using` 지시문에 구문 오류가:

```cpp
// C2143a.cpp
// compile with: /clr /c
using namespace System.Reflection;   // C2143
using namespace System::Reflection;
```

또한 사용 하지 않고 CLR 구문을 사용 하 여 소스 코드 파일을 컴파일하는 하려는 하는 경우 발생할 수 있습니다 **/clr**:

```cpp
// C2143b.cpp
ref struct A {   // C2143 error compile with /clr
   void Test() {}
};

int main() {
   A a;
   a.Test();
}
```

`if` 문 다음에 오는 첫 번째 비공백 문자는 왼쪽 괄호여야 합니다. 컴파일러는 다른 변환할 수 없습니다.

```cpp
// C2143c.cpp
int main() {
   int j = 0;

   // OK
   if (j < 25)
      ;

   if (j < 25)   // C2143
}
```

C2143은 오류가 검색된 줄 또는 윗줄 중 하나에서 닫는 중괄호, 괄호 또는 세미콜론이 누락된 경우 발생할 수 있습니다.

```cpp
// C2143d.cpp
// compile with: /c
class X {
   int member1;
   int member2   // C2143
} x;
```

또는 클래스 선언에 잘못된 태그가 있는 경우:

```cpp
// C2143e.cpp
class X {
   int member;
} x;

class + {};   // C2143 + is an invalid tag name
class ValidName {};   // OK
```

또는 레이블이 문에 첨부되지 않은 경우. 레이블을 자체적으로 배치 해야 하는 경우 예를 들어, 복합 문의 끝에 연결할 null 문:

```cpp
// C2143f.cpp
// compile with: /c
void func1() {
   // OK
   end1:
      ;

   end2:   // C2143
}
```

형식에 정규화 되지 않은 호출이 수행 될 때 오류가 발생할 수 있습니다는 C++ 표준 라이브러리:

```cpp
// C2143g.cpp
// compile with: /EHsc /c
#include <vector>
static vector<char> bad;   // C2143
static std::vector<char> good;   // OK
```

또는 `typename` 키워드가 누락된 경우:

```cpp
// C2143h.cpp
template <typename T>
struct X {
   struct Y {
      int i;
   };
   Y memFunc();
};
template <typename T>
X<T>::Y X<T>::memFunc() {   // C2143
// try the following line instead
// typename X<T>::Y X<T>::memFunc() {
   return Y();
}
```

또는 명시적 인스턴스화를 정의하려고 한 경우:

```cpp
// C2143i.cpp
// compile with: /EHsc /c
// template definition
template <class T>
void PrintType(T i, T j) {}

template void PrintType(float i, float j){}   // C2143
template void PrintType(float i, float j);   // OK
```

C 프로그램에서 함수의 시작 부분에서 변수를 선언 해야 하 고 함수 선언 되지 않은 명령을 실행 한 후 선언할 수 없습니다.

```C
// C2143j.c
int main()
{
    int i = 0;
    i++;
    int j = 0; // C2143
}
```
