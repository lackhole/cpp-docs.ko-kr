---
title: decltype (C++)
ms.date: 11/04/2016
f1_keywords:
- decltype_cpp
helpviewer_keywords:
- operators [C++], decltype
- decltype operator
- operators [C++], type of an expression
- operators [C++], deduce expression type
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
ms.openlocfilehash: 6c1c91aec7d974836b1ec031a1e8b38e8abb65ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399085"
---
# <a name="decltype--c"></a>decltype (C++)

합니다 **decltype** 형식 지정자는 지정 된 식의 형식을 생성 합니다. 합니다 **decltype** 형식 지정자를 함께 합니다 [auto 키워드](../cpp/auto-cpp.md), 템플릿 라이브러리를 작성 하는 개발자에 게 주로 유용 합니다. 사용 하 여 **자동** 하 고 **decltype** 반환 하는 템플릿 함수를 선언 하 형식이 해당 템플릿 인수의 형식에 종속 됩니다. 또는 사용 하 여 **자동** 하 고 **decltype** 다른 함수에 대 한 호출을 래핑한 다음 래핑된 함수의 반환 형식을 반환 하는 템플릿 함수를 선언 합니다.

## <a name="syntax"></a>구문

```
decltype( expression )
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*expression*|식입니다. 자세한 내용은 [식을](../cpp/expressions-cpp.md)합니다.|

## <a name="return-value"></a>반환 값

형식의 합니다 *식* 매개 변수입니다.

## <a name="remarks"></a>설명

합니다 **decltype** 시각적 개체의 형식 지정자는 C++ 2010 이상 버전에서는 네이티브 또는 관리 코드를 사용 하 여 사용할 수 있습니다. `decltype(auto)`(C++14)는 Visual Studio 2015 이상에서 지원됩니다.

컴파일러의 형식을 확인 하려면 다음 규칙을 사용 합니다 *식* 매개 변수입니다.

- 경우는 *식* 매개 변수는 식별자 또는 [클래스 멤버 액세스](../cpp/member-access-operators-dot-and.md)를 `decltype(expression)` 으로 명명 된 엔터티 형식이 *식*합니다. 엔터티가 없는 경우 또는 *식* 매개 변수 오버 로드 된 함수 집합에 이름을, 컴파일러가 오류 메시지를 생성 합니다.

- 경우는 *식을* 매개 변수는 함수 또는 오버 로드 된 연산자 함수를 호출 `decltype(expression)` 함수의 반환 형식입니다. 오버로드된 연산자를 묶는 괄호는 무시됩니다.

- 경우는 *식* 매개 변수는는 [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)를 `decltype(expression)` 의 형식인 *식*합니다. 경우는 *식* 매개 변수는는 [lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md), `decltype(expression)` 는 [lvalue 참조](../cpp/lvalue-reference-declarator-amp.md) 유형과 *식*.

다음 코드 예제에서는의 몇 가지 용도 **decltype** 형식 지정자입니다. 먼저 다음 문을 코딩한 것으로 가정합니다.

```cpp
int var;
const int&& fx();
struct A { double x; }
const A* a = new A();
```

다음으로, 네 개의에서 반환 되는 형식 검사 **decltype** 다음 표에 문입니다.

|문|형식|노트|
|---------------|----------|-----------|
|`decltype(fx());`|`const int&&`|[rvalue 참조](../cpp/rvalue-reference-declarator-amp-amp.md) 에 **const int**합니다.|
|`decltype(var);`|**int**|`var` 변수의 형식입니다.|
|`decltype(a->x);`|**double**|멤버 액세스의 형식입니다.|
|`decltype((a->x));`|`const double&`|내부 괄호를 사용하면 문이 멤버 액세스가 아니라 식으로 평가됩니다. 이므로 `a` 으로 선언 되는 `const` 포인터 형식에 대 한 참조는 **const double**합니다.|

## <a name="decltype-and-auto"></a>Decltype 및 Auto

C++14에서는에서 사용할 수 있습니다 `decltype(auto)` 반환 형식이 템플릿 함수를 선언 하려면 후행 반환 형식이 없는 해당 템플릿 인수의 형식에 종속 됩니다.

C + + 11에서 사용할 수 있습니다 합니다 **decltype** 와 함께 후행 반환 형식에 지정자를 입력 합니다 **자동** 키워드, 해당 반환 형식이 템플릿 함수를 선언 하는 서식 파일의 형식에 종속 인수입니다. 예를 들어, 템플릿 함수의 반환 형식이 템플릿 인수의 형식에 종속되는 것을 보여 주는 다음 코드 예제를 살펴보세요. 코드 예제에서는 *알 수 없는* 자리 표시자는 반환 형식을 지정할 수 없음을 나타냅니다.

```cpp
template<typename T, typename U>
UNKNOWN func(T&& t, U&& u){ return t + u; };
```

도입 된 **decltype** 템플릿 함수가 반환 하는 식의 형식은 획득 하는 개발자를 사용 하는 형식 지정자입니다. 사용 하 여는 *대체 함수 선언 구문* 나중에 표시 된 합니다 **자동** 키워드 및 **decltype** 형식 지정자를 선언 하는  *컴파일하면 지정* 형식을 반환 합니다. 컴파일하면 지정되는 반환 형식은 코딩 시가 아니라 선언이 컴파일될 때 결정됩니다.

다음 프로토타입에서는 대체 함수 선언의 구문을 보여 줍니다. **const** 하 고 **volatile** 한정자 및 **throw** [예외 사양이](../cpp/exception-specifications-throw-cpp.md) 는 선택 사항. 합니다 *function_body* 자리 표시자는 함수가 수행 지정 하는 복합 문을 나타냅니다. 모범 코딩 사례는를 *식* 자리 표시자를 **decltype** 문 지정 된 식과 일치 해야 합니다 **반환** 문, 있는 경우를 *function_body*합니다.

**자동** *function_name* **(** *매개 변수*<sub>opt</sub> **)**  **const**<sub>opt</sub> **volatile**<sub>opt</sub> **->** **decltype (** *식을* **)** **throw**<sub>opt</sub> **{** *function_body* **};**

다음 코드 예제에서는 `myFunc` 템플릿 함수의 컴파일하면 지정되는 반환 형식이 `t` 및 `u` 템플릿 인수의 형식에 따라 결정됩니다. 모범 코딩 사례, 코드 또한이 예제에서는 rvalue 참조 및 `forward` 지 함수 템플릿을 *완벽 전달*합니다. 자세한 내용은 [RValue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.

```cpp
//C++11
template<typename T, typename U>
auto myFunc(T&& t, U&& u) -> decltype (forward<T>(t) + forward<U>(u))
        { return forward<T>(t) + forward<U>(u); };

//C++14
template<typename T, typename U>
decltype(auto) myFunc(T&& t, U&& u)
        { return forward<T>(t) + forward<U>(u); };
```

## <a name="decltype-and-forwarding-functions-c11"></a>Decltype 및 전달 함수(C++11)

전달 함수는 다른 함수에 대한 호출을 래핑합니다. 해당 인수 또는 이러한 인수를 포함하는 식의 결과를 다른 함수로 전달하는 함수 템플릿을 고려해 보십시오. 또한 전달 함수는 다른 함수를 호출한 결과를 반환합니다. 이 시나리오에서 전달 함수의 반환 형식은 래핑된 함수의 반환 형식과 동일해야 합니다.

이 시나리오에서는 없이 적절 한 형식 식을 쓸 수 없습니다는 **decltype** 형식 지정자입니다. 합니다 **decltype** 형식 지정자는 함수 참조 형식을 반환 하는 여부에 대 한 필요한 정보를 잃지 않기 때문에 제네릭 전달 함수를 사용 합니다. 전달 함수의 코드 예제는 이전 `myFunc` 템플릿 함수 예제를 참조하세요.

## <a name="example"></a>예제

다음 코드 예제는 템플릿 함수 `Plus()`의 컴파일하면 지정되는 반환 형식을 선언합니다. 합니다 `Plus` 함수를 사용 하 여 두 피연산자 처리 합니다 **operator +** 오버 로드 합니다. 따라서 `Plus` 함수의 반환 형식 및 더하기 연산자(+)에 대한 해석은 함수 인수의 형식에 따라 달라집니다.

```cpp
// decltype_1.cpp
// compile with: cl /EHsc decltype_1.cpp

#include <iostream>
#include <string>
#include <utility>
#include <iomanip>

using namespace std;

template<typename T1, typename T2>
auto Plus(T1&& t1, T2&& t2) ->
   decltype(forward<T1>(t1) + forward<T2>(t2))
{
   return forward<T1>(t1) + forward<T2>(t2);
}

class X
{
   friend X operator+(const X& x1, const X& x2)
   {
      return X(x1.m_data + x2.m_data);
   }

public:
   X(int data) : m_data(data) {}
   int Dump() const { return m_data;}
private:
   int m_data;
};

int main()
{
   // Integer
   int i = 4;
   cout <<
      "Plus(i, 9) = " <<
      Plus(i, 9) << endl;

   // Floating point
   float dx = 4.0;
   float dy = 9.5;
   cout <<
      setprecision(3) <<
      "Plus(dx, dy) = " <<
      Plus(dx, dy) << endl;

   // String
   string hello = "Hello, ";
   string world = "world!";
   cout << Plus(hello, world) << endl;

   // Custom type
   X x1(20);
   X x2(22);
   X x3 = Plus(x1, x2);
   cout <<
      "x3.Dump() = " <<
      x3.Dump() << endl;
}
```

```Output
Plus(i, 9) = 13
Plus(dx, dy) = 13.5
Hello, world!
x3.Dump() = 42
```

## <a name="example"></a>예제

**Visual Studio 2017 이상:** 템플릿에 인스턴스화가 아니라 선언 하는 경우 컴파일러가 decltype 인수를 구문 분석 합니다. 따라서 decltype 인수에 독립적 특수화가 있는 경우 이 특수화는 인스턴스화 시점으로 연기되지 않고 즉시 처리되며 결과 오류가 이 시점에 진단됩니다.

다음 예제에서는 선언 시점에 발생한 컴파일러 오류를 보여 줍니다.

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT> class IsCallable
{
public:
   struct BadType {};
   template <class U>
   static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>
   template <class U>
   static BadType Test(...);
   static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

## <a name="requirements"></a>요구 사항

Visual C++ 2010 이상 버전

`decltype(auto)` Visual Studio 2015 이상이 필요합니다.