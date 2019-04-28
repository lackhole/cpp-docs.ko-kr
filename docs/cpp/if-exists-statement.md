---
title: __if_exists 문
ms.date: 11/04/2016
f1_keywords:
- __if_exists_cpp
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
ms.openlocfilehash: 9d5a0b24bb08a9485b2d212058fa8f0bd82e5842
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183676"
---
# <a name="ifexists-statement"></a>__if_exists 문

합니다 **__if_exists** 문은 지정된 된 식별자가 있는지 여부를 테스트 합니다. 식별자가 있는 경우 지정된 문 블록이 실행됩니다.

## <a name="syntax"></a>구문

```
__if_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*identifier*|존재 여부를 테스트할 식별자입니다.|
|*statements*|경우 실행할 하나 이상의 문이 *식별자* 존재 합니다.|

## <a name="remarks"></a>설명

> [!CAUTION]
>  가장 안정적인 결과 달성 하려면 사용 합니다 **__if_exists** 다음 제약 조건에 따라 문입니다.

- 적용 된 **__if_exists** 문, 템플릿이 아니라 단순 형식에만 합니다.

- 적용 된 **__if_exists** 문을 내부 또는 외부 클래스 식별자입니다. 적용 되지 않습니다 합니다 **__if_exists** 지역 변수에 문입니다.

- 사용 된 **__if_exists** 문은 함수의 본문에만. 함수 본문 외부에서 **__if_exists** 문은 완전히 정의 된 형식만 테스트할 수 있습니다.

- 오버로드된 함수에 대해 테스트할 때 특정 양식의 오버로드를 테스트할 수 없습니다.

보완 하는 **__if_exists** 문이 합니다 [__if_not_exists](../cpp/if-not-exists-statement.md) 문입니다.

## <a name="example"></a>예제

다음 예제에서는 템플릿을 사용하지만, 이는 권장되는 방법은 아닙니다.

```cpp
// the__if_exists_statement.cpp
// compile with: /EHsc
#include <iostream>

template<typename T>
class X : public T {
public:
   void Dump() {
      std::cout << "In X<T>::Dump()" << std::endl;

      __if_exists(T::Dump) {
         T::Dump();
      }

      __if_not_exists(T::Dump) {
         std::cout << "T::Dump does not exist" << std::endl;
      }
   }
};

class A {
public:
   void Dump() {
      std::cout << "In A::Dump()" << std::endl;
   }
};

class B {};

bool g_bFlag = true;

class C {
public:
   void f(int);
   void f(double);
};

int main() {
   X<A> x1;
   X<B> x2;

   x1.Dump();
   x2.Dump();

   __if_exists(::g_bFlag) {
      std::cout << "g_bFlag = " << g_bFlag << std::endl;
   }

   __if_exists(C::f) {
      std::cout << "C::f exists" << std::endl;
   }

   return 0;
}
```

## <a name="output"></a>출력

```Output
In X<T>::Dump()
In A::Dump()
In X<T>::Dump()
T::Dump does not exist
g_bFlag = 1
C::f exists
```

## <a name="see-also"></a>참고자료

[선택 문(C++)](../cpp/selection-statements-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[__if_not_exists 문](../cpp/if-not-exists-statement.md)