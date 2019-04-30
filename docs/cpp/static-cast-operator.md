---
title: static_cast 연산자
ms.date: 11/04/2016
f1_keywords:
- static_cast_cpp
helpviewer_keywords:
- static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
ms.openlocfilehash: dca6d5297379e6ddc1c70dba80f35f2f55672e49
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267130"
---
# <a name="staticcast-operator"></a>static_cast 연산자

변환는 *식* 의 형식으로 *유형-id* 식에 있는 형식에만 기반 합니다.

## <a name="syntax"></a>구문

```
static_cast <type-id> ( expression )
```

## <a name="remarks"></a>설명

표준 C++에서는 변환의 안전성을 보장하기 위해 런타임 형식 검사가 수행되지 않습니다. C++/CX에서는 컴파일 시간 및 런타임 검사가 수행됩니다. 자세한 내용은 [캐스팅](casting.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

합니다 **static_cast** 파생된 클래스에 대 한 포인터가 기본 클래스에 대 한 포인터의 변환과 같은 연산에 대 한 연산자를 사용할 수 있습니다. 이러한 변환이 항상 안전한 것은 아닙니다.

사용할 일반적 **static_cast** 정수로 또는 정수를 부동 소수점 수, 하 열거형 같은 숫자 데이터 형식을 변환 하려는 경우 특정 데이터 형식 변환에 관련 된 합니다. **static_cast** 변환은 만큼 안전 **dynamic_cast** 변환 하므로 **static_cast** 는 없는 런타임 형식 검사를 **dynamic_cast** 수행 하지 않습니다. **dynamic_cast** 모호한 포인터에 실패 하는 동안는 **static_cast** nothing이 위험할 수 있습니다; 잘못 된 것 처럼 반환 합니다. 하지만 **dynamic_cast** 변환은 안전 하며 **dynamic_cast** 포인터 또는 참조 및 런타임 형식 확인 작동 오버 헤드가 합니다. 자세한 내용은 [dynamic_cast 연산자](../cpp/dynamic-cast-operator.md)합니다.

다음에 나오는 예제에서 `D* pd2 = static_cast<D*>(pb);` 줄은 `D`에서 `B`에 있지 않은 필드와 메서드를 가질 수 있기 때문에 안전하지 않습니다. 그러나 `B* pb2 = static_cast<B*>(pd);`는 항상 모든 `D`를 포함하기 때문에 `B` 줄의 변환은 안전합니다.

```cpp
// static_cast_Operator.cpp
// compile with: /LD
class B {};

class D : public B {};

void f(B* pb, D* pd) {
   D* pd2 = static_cast<D*>(pb);   // Not safe, D can have fields
                                   // and methods that are not in B.

   B* pb2 = static_cast<B*>(pd);   // Safe conversion, D always
                                   // contains all of B.
}
```

와 달리 [dynamic_cast](../cpp/dynamic-cast-operator.md), 없습니다 런타임 검사에 사용 되는 **static_cast** 변환 `pb`합니다. `pb`가 가리키는 개체는 유형 `D`의 개체가 아닐 수 있으며, 이 경우 `*pd2`를 사용하는 것은 매우 위험합니다. 예를 들어 `D` 클래스가 아닌 `B` 클래스의 멤버인 함수를 호출하면 액세스 위반이 발생할 수 있습니다.

합니다 **dynamic_cast** 하 고 **static_cast** 연산자 클래스 계층 구조 전체에서 포인터를 이동 합니다. 그러나 **static_cast** 캐스트 문에서 제공 된 정보에 대해서만 의존 하 고 안전 하지 않을 수 있으므로 수 있습니다. 예를 들어:

```cpp
// static_cast_Operator_2.cpp
// compile with: /LD /GR
class B {
public:
   virtual void Test(){}
};
class D : public B {};

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);
   D* pd2 = static_cast<D*>(pb);
}
```

`pb`가 `D` 형식의 개체를 가리킬 경우 `pd1` 및 `pd2`는 동일한 값을 얻습니다. 또한 `pb == 0`일 경우 같은 값을 얻습니다.

하는 경우 `pb` 형식의 개체를 가리키는 `B` 완전 하 고 `D` 클래스를 **dynamic_cast** 0을 반환을 충분히 알고 있어야 합니다. 그러나 **static_cast** 프로그래머의 어설션에 의존 하는 `pb` 형식의 개체를 가리키는 `D` 단순히는에 대 한 포인터를 반환 하 고 `D` 개체입니다.

따라서 **static_cast** 암시적 변환의 역함수 값을 수행할 수 있습니다,이 경우에 결과가 정의 되지 않습니다. 결과를 확인 하는 프로그래머에 게 중단 되는 **static_cast** 안전 하 게 변환 됩니다.

이 동작은 클래스 형식 이외의 형식에도 적용됩니다. 예를 들어 **static_cast** 는 정수를 변환할 수는 **char**합니다. 그러나 결과 **char** 전체를 저장할 충분 한 비트가 없을 **int** 값입니다. 마찬가지로 남아 있는지 확인 하려면 프로그래머에 게 결과 **static_cast** 안전 하 게 변환 됩니다.

합니다 **static_cast** 연산자 표준 변환 및 사용자 정의 변환을 비롯 한 모든 암시적 변환 하는 데 사용할 수도 있습니다. 예를 들어:

```cpp
// static_cast_Operator_3.cpp
// compile with: /LD /GR
typedef unsigned char BYTE;

void f() {
   char ch;
   int i = 65;
   float f = 2.5;
   double dbl;

   ch = static_cast<char>(i);   // int to char
   dbl = static_cast<double>(f);   // float to double
   i = static_cast<BYTE>(ch);
}
```

합니다 **static_cast** 연산자 열거형 형식을 명시적으로 정수 값을 변환할 수 있습니다. 정수 계열 형식의 값이 열거형 값 범위에 속하지 않으면 결과 열거형 값이 정의되지 않습니다.

합니다 **static_cast** 연산자 대상 형식의 null 포인터 값으로 null 포인터 값을 변환 합니다.

모든 식 명시적 의해 void 형식으로 변환 될 수는 **static_cast** 연산자입니다. 대상 void 형식은 선택적으로 포함할 수는 **상수**, **volatile**, 또는 **__unaligned** 특성.

합니다 **static_cast** 연산자 떨어져 캐스팅할 수 없습니다는 **const**를 **volatile**, 또는 **__unaligned** 특성입니다. 참조 [const_cast 연산자](../cpp/const-cast-operator.md) 이러한 특성을 제거 하는 방법은 합니다.

**C++/CLI:** 재배치 가비지 수집기 사용의 상단에서 확인 되지 않은 캐스팅을 수행 하는 위험으로 인해 **static_cast** 올바르게 작동 한다고 확신할 때 성능에 중요 코드에서 이어야만 합니다. 사용 해야 하는 경우 **static_cast** 릴리스 모드에서 사용 하 여 대체 [safe_cast](../extensions/safe-cast-cpp-component-extensions.md) 성공을 위해 디버그 빌드의 합니다.

## <a name="see-also"></a>참고자료

[캐스팅 연산자](../cpp/casting-operators.md)<br/>
[키워드(C++)](../cpp/keywords-cpp.md)