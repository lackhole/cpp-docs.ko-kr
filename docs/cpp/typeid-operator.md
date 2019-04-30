---
title: typeid 연산자
ms.date: 11/04/2016
helpviewer_keywords:
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
ms.openlocfilehash: b1185f48df4a941eb2a5d81bfa67d07cdf4387d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404665"
---
# <a name="typeid-operator"></a>typeid 연산자

## <a name="syntax"></a>구문

```
typeid(type-id)
typeid(expression)
```

## <a name="remarks"></a>설명

합니다 **typeid** 연산자를 사용 하면 런타임 시 결정 해야 하는 개체의 형식입니다.

결과인 **typeid** 되는 `const type_info&`합니다. 값이에 대 한 참조를 `type_info` 나타내는 개체를 *type-id 형식의* 또는 형식의 *식*형태에 따라 **typeid** 사용 됩니다. 참조 [type_info 클래스](../cpp/type-info-class.md) 자세한 내용은 합니다.

합니다 **typeid** 연산자는 관리 되는 형식 (추상 선언 자 또는 인스턴스) 사용 하지 않고 참조 하십시오 [typeid](../extensions/typeid-cpp-component-extensions.md) 에 대 한 내용은 <xref:System.Type> 지정 된 형식의 합니다.

합니다 **typeid** 연산자는 다형 클래스 형식의 l-value에 적용 될 때 런타임 검사를 제공 된 정적 정보로 개체의 true 형식을 확인할 수 없습니다 위치 합니다. 다음과 같은 경우가 여기에 해당합니다.

- 클래스에 대한 참조

- 포인터를 사용 하 여 역참조 \*

- 첨자 포인터(예: [ ]). 일반적으로 다형 형식의 포인터에 첨자를 사용하는 것은 안전하지 않습니다.

경우는 *식* 아직 개체가 실제로 기본 클래스에서 파생 된 형식의 기본 클래스 형식으로 요소를 `type_info` 파생된 클래스는 결과 대 한 참조입니다. 합니다 *식* 다형 형식 (가상 함수를 사용 하 여 클래스)을 가리켜야 합니다. 그렇지 않으면 결과 합니다 `type_info` 에서 참조 되는 정적 클래스에 대 한는 *식*합니다. 또한 가리키는 개체를 사용하도록 포인터를 역참조해야 합니다. 결과 포인터를 역참조 하지 않으면 됩니다는 `type_info` 없습니다 it를 가리키는 포인터에 대 한 합니다. 예를 들어:

```cpp
// expre_typeid_Operator.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <typeinfo.h>

class Base {
public:
   virtual void vvfunc() {}
};

class Derived : public Base {};

using namespace std;
int main() {
   Derived* pd = new Derived;
   Base* pb = pd;
   cout << typeid( pb ).name() << endl;   //prints "class Base *"
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"
   delete pd;
}
```

경우는 *식* 포인터를 역참조 하는 포인터의 값이 0 인지 **typeid** throw를 [bad_typeid exception](../cpp/bad-typeid-exception.md)합니다. 포인터가 유효한 개체를 가리키지 않을 경우는 `__non_rtti_object` 예외가 throw 되는 오류를 트리거한 RTTI를 분석 하려는 시도 나타냅니다 (예: 액세스 위반), 개체 어떤 이유로 든 올바르지 않으므로 (잘못 된 포인터 또는 코드를 컴파일하지 를사용하여[/GR](../build/reference/gr-enable-run-time-type-information.md)).

경우는 *식* 대 한 포인터도 아니고 개체의 기본 클래스에 대 한 참조는 결과를 `type_info` 참조의 정적 형식을 나타내는 *식*합니다. 합니다 *정적 형식* 식의 형식을 참조 하는 식의 컴파일 타임에 알려진 대로 합니다. 식의 정적 형식을 평가할 때 식의 의미 체계가 무시됩니다. 또한 식의 정적 형식을 결정할 때 가능할 경우 참조가 무시됩니다.

```cpp
// expre_typeid_Operator_2.cpp
#include <typeinfo>

int main()
{
   typeid(int) == typeid(int&); // evaluates to true
}
```

**typeid** 사용할 수도 있습니다 템플릿의 템플릿 매개 변수의 형식을 확인 하려면:

```cpp
// expre_typeid_Operator_3.cpp
// compile with: /c
#include <typeinfo>
template < typename T >
T max( T arg1, T arg2 ) {
   cout << typeid( T ).name() << "s compared." << endl;
   return ( arg1 > arg2 ? arg1 : arg2 );
}
```

## <a name="see-also"></a>참고자료

[런타임 형식 정보](../cpp/run-time-type-information.md)<br/>
[키워드(C++)](../cpp/keywords-cpp.md)