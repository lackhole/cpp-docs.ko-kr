---
title: C++ 규칙 향상
ms.date: 03/26/2019
ms.technology: cpp-language
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 6a0e296e4a5542c1aad848c55d35d3e40244478d
ms.sourcegitcommit: b72a10a7b12e722fd91a17406b91b270026f763a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2019
ms.locfileid: "58899449"
---
# <a name="c-conformance-improvements-in-visual-studio-2017-versions-150-153improvements153-155improvements155-156improvements156-157improvements157-158update158-159improvements159"></a>Visual Studio 2017 버전 15.0, [15.3](#improvements_153), [15.5](#improvements_155), [15.6](#improvements_156), [15.7](#improvements_157), [15.8](#update_158), [15.9](#improvements_159)의 C++ 규칙 향상

Microsoft Visual C++ 컴파일러는 일반화된 constexpr을 지원하고 집계에 NSDMI를 사용할 수 있기 때문에 이제 C++14 표준에 추가된 기능을 완벽히 갖췄습니다. 하지만 아직까지 C++11 표준 기능과 C++98 표준 기능이 몇 가지 부족합니다. 컴파일러의 현재 상태를 보여 주는 테이블은 [Visual C++ Language Conformance](../visual-cpp-language-conformance.md)(Visual C++ 언어 규칙)를 참조하세요.

## <a name="c11"></a>C++11

### <a name="expression-sfinae-support-in-more-libraries"></a>더 많은 라이브러리의 SFINAE 식 지원

Visual C++ 컴파일러는 decltype 및 constexpr 식이 템플릿 매개 변수로 나타날 수 있는 템플릿 인수 감소 및 대체에 필요한 SFINAE 식에 대한 지원을 계속 개선하고 있습니다. 자세한 내용은 [Expression SFINAE improvements in Visual Studio 2017 RC](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3)(Visual Studio 2017 RC의 SFINAE 식 향상)를 참조하세요.

## <a name="c-14"></a>C++ 14

### <a name="nsdmi-for-aggregates"></a>집계용 NSDMI

집계는 사용자 제공 생성자가 없고, 개인 또는 보호된 비정적 데이터 멤버가 없고, 기본 클래스가 없고, 가상 함수가 없는 배열 또는 클래스입니다. C++14부터 집계에 멤버 이니셜라이저가 포함될 수 있습니다. 자세한 내용은 [Member initializers and aggregates](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html)(멤버 이니셜라이저 및 집계)를 참조하세요.

### <a name="extended-constexpr"></a>확장된 constexpr

constexpr로 선언된 식은 이제 특정 종류의 선언, if 및 switch 문, loop 문 및 수명이 constexpr 식 계산 내에서 시작된 개체의 변형을 포함할 수 있습니다. 또한 더 이상 constexpr 비정적 멤버 함수가 암시적으로 생성될 필요가 없습니다. 자세한 내용은 [Relaxing constraints on constexpr functions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)(constexpr 함수에 대한 제약 조건 완화)를 참조하세요.

## <a name="c17"></a>C++17

### <a name="terse-staticassert"></a>간결한 static_assert

static_assert용 메시지 매개 변수는 선택 사항입니다. 자세한 내용은 [Extending static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)(static_assert 확장, v2)를 참조하세요.

### <a name="fallthrough-attribute"></a>[[fallthrough]] 특성

**/std:c++17** 모드에서 [[fallthrough]] 특성은 switch 문의 컨텍스트에서 제어 이동 동작이 의도된 컴파일러에 대한 힌트로 사용될 수 있습니다. 이 특성을 사용하면 컴파일러가 해당하는 경우에 경고를 실행하지 않습니다. 자세한 내용은 [Wording for [[fallthrough]] attribute](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf)([[fallthrough]] 특성에 대한 표현)를 참조하세요.

### <a name="generalized-range-based-for-loops"></a>일반화된 범위 기반 for 루프

Range-based for 루프에 더 이상 동일한 유형의 begin() 및 end() 반환 개체가 필요하지 않습니다. 이는 end()가 [range-v3](https://github.com/ericniebler/range-v3)의 범위에서 사용된 sentinel과 completed-but-not-quite-published 범위 기술 사양을 반환할 수 있게 해줍니다. 자세한 내용은 [Generalizing the Range-Based For Loop](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)(범위 기반 for 루프 일반화)를 참조하세요.

## <a name="improvements_153"></a> Visual Studio 2017 버전 15.3의 개선 사항

### <a name="constexpr-lambdas"></a>constexpr 람다

이제 상수 식에서 람다 식을 사용할 수 있습니다. 자세한 내용은 [C++의 constexpr 람다 식](../../cpp/lambda-expressions-constexpr.md)을 참조하세요.

### <a name="if-constexpr-in-function-templates"></a>함수 템플릿의 if constexpr

함수 템플릿에 컴파일 시간 분기가 가능하도록 `if constexpr` 문이 포함될 수 있습니다. 자세한 내용은 [if constexpr 문](../../cpp/if-else-statement-cpp.md#if_constexpr)을 참조하세요.

### <a name="selection-statements-with-initializers"></a>이니셜라이저를 사용하는 선택 문

`if` 문은 문 자체 내의 블록 범위에서 변수를 소개하는 이니셜라이저를 포함할 수 있습니다. 자세한 내용은 [이니셜라이저가 있는 if 문](../../cpp/if-else-statement-cpp.md#if_with_init)을 참조하세요.

### <a name="maybeunused-and-nodiscard-attributes"></a>[[maybe_unused]] 및 [[nodiscard]] 특성

새 특성은 엔터티를 사용하지 않을 때 경고를 억제시키거나 함수 호출의 반환 값을 무시하는 경우 경고를 만듭니다. 자세한 내용은 [C++ 특성](../../cpp/attributes.md)을 참조하세요.

### <a name="using-attribute-namespaces-without-repetition"></a>반복 없이 특성 네임스페이스 사용

특성 목록에서 단일 네임스페이스 식별자만 사용하는 새 구문입니다. 자세한 내용은 [C++ 특성](../../cpp/attributes.md)을 참조하세요.

### <a name="structured-bindings"></a>구조적 바인딩

이제 단일 선언에서 값이 배열, std::tuple 또는 std::pair이거나 모든 공용 비정적 데이터 멤버가 있는 경우 구성 요소에 대한 개별 이름을 포함하는 값을 저장할 수 있습니다. 자세한 내용은 [구조적 바인딩](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf) 및 [함수에서 여러 값 반환](../../cpp/functions-cpp.md#multi_val)을 참조하세요.

### <a name="construction-rules-for-enum-class-values"></a>enum 클래스 값에 대한 생성 규칙

이제 해당 정의에서 열거형을 소개하지 않고 소스에서 목록 초기화 구문을 사용하는 경우 범위가 지정된 열거형의 기본 형식에서 열거형 자체로의 암시적/비축소 변환이 있습니다. 자세한 내용은 [enum 클래스 값의 생성 규칙](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf) 및 [열거형](../../cpp/enumerations-cpp.md#no_enumerators)을 참조하세요.

### <a name="capturing-this-by-value"></a>값 기준 \*this 캡처

람다 식의 `*this` 개체는 이제 값을 기준으로 캡처할 수 있습니다. 이렇게 하면 병렬 및 비동기 작업, 특히 최신 컴퓨터 아키텍처에서 람다가 호출되는 시나리오를 사용할 수 있습니다. 자세한 내용은 [[=,\*this]로 값 기준 \*this 람다 캡처(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)를 참조하세요.

### <a name="removing-operator-for-bool"></a>bool 형식 operator++ 제거

`operator++` 더 이상 `bool` 형식에서 지원되지 않습니다. 자세한 내용은 [사용되지 않는 operator++(bool) 제거(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html)를 참조하세요.

### <a name="removing-deprecated-register-keyword"></a>사용되지 않는 "register" 키워드 제거

이전에 더 이상 사용되지 않고(컴파일러에서 무시된) `register` 키워드가 이제 언어에서 제거되었습니다. 자세한 내용은 [사용되지 않는 register 키워드 제거(영문)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html)를 참조하세요.

Visual Studio 2015, 업데이트 3까지 규칙 향상의 전체 목록은 [Visual C++ What's New 2003 through 2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015)(2003부터 2015까지 Visual C++의 새로운 기능)를 참조하세요.

## <a name="improvements_155"></a>  Visual Studio 2017 버전 15.5의 개선 사항

[14]로 표시된 기능은 **/std:c++14** 모드에서도 무조건 사용할 수 있습니다.

### <a name="new-compiler-switch-for-extern-constexpr"></a>extern constexpr을 위한 새로운 컴파일러 스위치

이전 버전의 Visual Studio에서는 `constexpr` 변수에 `extern`이 표시된 경우에도 컴파일러가 항상 해당 변수에 내부 링크를 제공했습니다. Visual Studio 2017 15.5 버전에서 새 컴파일러 스위치[/Zc:externConstexpr](../../build/reference/zc-externconstexpr.md)는 올바른 표준 준수 동작을 활성화합니다. 자세한 내용은 [extern constexpr 링크](#extern_linkage)를 참조하세요.

### <a name="removing-dynamic-exception-specifications"></a>동적 예외 사양 제거

[P0003R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html) C++11에서는 동적 예외 사양이 사용되지 않았습니다. 이 기능은 C++17에서 제거되었지만 사용되지 않는 `throw()` 사양이 여전히 `noexcept(true)`에 대한 별칭으로 엄격히 유지됩니다. 자세한 내용은 [동적 예외 사양 제거 및 noexcept](#noexcept_removal)를 참조하세요.

### <a name="notfn"></a>not_fn()

[P0005R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html) `not_fn`은 `not1` 및 `not2`를 대체합니다.

### <a name="rewording-enablesharedfromthis"></a>enable_shared_from_this 다시 표시

C++11에서 [P0033R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html) `enable_shared_from_this`가 추가되었습니다. C++17 표준은 특정 코너 케이스를 더 잘 처리하도록 사양을 업데이트합니다. [14]

### <a name="splicing-maps-and-sets"></a>맵 및 집합 스플라이스

[P0083R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf) 이 기능은 연관 컨테이너에서 노드(예: map, set, unordered\_map, unordered\_set)의 추출을 지원하며, 추출된 노드는 수정한 뒤 동일한 컨테이너나 동일한 노드 형식을 사용하는 다른 컨테이너에 다시 삽입할 수 있습니다. (일반적인 사용 사례는 `std::map`에서 노드를 추출하고 키를 변경하고 다시 삽입하는 것입니다.)

### <a name="deprecating-vestigial-library-parts"></a>남아 있는 라이브러리 파트 사용 중단

[P0174R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html) C++ 표준 라이브러리의 몇 가지 기능은 수 년에 걸쳐 새로운 기능으로 대체되었거나 별로 유용하지 않거나 문제가 있는 것으로 확인되었습니다. 이러한 기능은 공식적으로 C++17에서 사용되지 않습니다.

### <a name="removing-allocator-support-in-stdfunction"></a>std::function에서 할당자 지원 제거

[P0302R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html) C++17 이전에는 클래스 템플릿 `std::function`에 할당자 인수를 사용하는 몇 가지 생성자가 있었습니다. 그러나 이 컨텍스트에서 할당자를 사용하는 것이 문제가 되었고, 의미 체계는 불확실했습니다. 따라서 이러한 생성자는 제거되었습니다.

### <a name="fixes-for-notfn"></a>not_fn()에 대한 수정 사항

[P0358R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html) `std::not_fn`에 대해 조정된 표현은 래퍼 호출 시 값 범주가 전파되도록 지원합니다.

### <a name="sharedptrt-sharedptrtn"></a>shared_ptr\<T[]>, shared_ptr\<T[N]>

[P0414R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html) 라이브러리 기본 사항에서 C++17로 `shared_ptr` 변경 사항 병합. [14]

### <a name="fixing-sharedptr-for-arrays"></a>배열에 대한 shared_ptr 해결

[P0497R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html) 배열에 대한 shared_ptr 지원 해결입니다. [14]

### <a name="clarifying-insertreturntype"></a>명확히 insert_return_type 설명

[P0508R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html) 고유한 키가 포함된 연관 컨테이너와 고유한 키가 포함된 불규칙 컨테이너에는 중첩 형식 `insert_return_type`을 반환하는 멤버 함수 `insert`가 있습니다. 이 반환 형식은 이제 컨테이너의 반복기와 노드 형식에서 매개 변수화되는 형식의 특수화로 정의됩니다.

### <a name="inline-variables-for-the-stl"></a>STL에 대한 인라인 변수

[P0607R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)

### <a name="annex-d-features-deprecated"></a>부록 D 기능 사용 중단

C++ 표준의 부록 D에는 사용이 중단된 모든 기능이 포함되어 있습니다(`shared_ptr::unique()`, `<codecvt>` 및 `namespace std::tr1` 포함). **/std:c++17** 컴파일러 스위치가 설정되면 부록 D의 거의 모든 표준 라이브러리 기능이 사용되지 않는 것으로 표시됩니다. 자세한 내용은 [부록 D의 표준 라이브러리 기능이 사용되지 않는 것으로 표시됩니다](#annex_d)를 참조하세요.

`<experimental/filesystem>`의 `std::tr2::sys` 네임스페이스는 이제 기본적으로 **/std:c++14** 하에서 사용 중단 경고를 생성하며, **/std:c++17** 하에서 기본적으로 제거됩니다.

비표준 확장(클래스 내 명시적 특수화)을 방지하여 iostreams의 규칙이 개선되었습니다.

표준 라이브러리에서는 이제 변수 템플릿을 내부적으로 사용합니다.

형식 시스템의 noexcept 추가 및 dynamic-exception-specifications 제거를 포함한 C++17 변경 사항에 따라 표준 라이브러리가 업데이트되었습니다.

## <a name="improvements_156"></a>  Visual Studio 2017 버전 15.6의 개선 사항

### <a name="c17-library-fundamentals-v1"></a>C++17 라이브러리 기본 사항 V1

[P0220R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html)은 C++17에 대한 라이브러리 기본 사항 기술 사양을 표준으로 통합합니다. \<experimental/tuple>, \<experimental/optional>, \<experimental/functional>, \<experimental/any>, \<experimental/string_view> , \<experimental/memory>, \<experimental/memory_resource> 및 \<experimental/algorithm>에 대한 업데이트를 다룹니다.

### <a name="c17-improving-class-template-argument-deduction-for-the-stl"></a>C++17 STL에 대한 클래스 템플릿 인수 추론 향상

[P0739R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html) `adopt_lock_t`를 `scoped_lock`에 대한 매개 변수 목록의 앞으로 이동하여 `scoped_lock`의 일관된 사용을 활성화합니다. 복사 할당을 활성화하기 위해 `std::variant` 생성자가 더 많은 경우에서 오버로드 확인에 참여하도록 합니다.

## <a name="improvements_157"></a> Visual Studio 2017 버전 15.7의 개선 사항

### <a name="c17-rewording-inheriting-constructors"></a>C++17 상속 생성자 다시 표시

[P0136R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html)은 생성자의 이름을 지정하는 **using** 선언에서 이제 추가 파생된 클래스 생성자를 선언하는 대신 파생된 클래스의 초기화를 볼 수 있는 해당 기본 클래스 생성자를 만들도록 지정합니다. 이는 C++14에서의 변경 내용입니다. Visual Studio 2017 버전 15.7 이상의 **/std:c++17** 모드에서 C++14에서 유효하고 상속 생성자를 사용하는 코드는 유효하지 않을 수 있거나 다른 의미 체계를 가질 수 있습니다.

다음 예제에서는 C++14 동작을 보여 줍니다.

```cpp
struct A {
    template<typename T>
    A(T, typename T::type = 0);
    A(int);
};

struct B : A {
    using A::A;
    B(int n) = delete; // Error C2280
};

B b(42L); // Calls B<long>(long), which calls A(int)
          //  due to substitution failure in A<long>(long).
```

다음 예제에서는 Visual Studio 15.7에서 **/std:c++17** 동작을 보여 줍니다.

```cpp
struct A {
    template<typename T>
    A(T, typename T::type = 0);
    A(int);
};

struct B : A {
    using A::A;
    B(int n)
    {
        //do something
    }
};

B b(42L); // now calls B(int)
```

자세한 내용은 [생성자](../../cpp/constructors-cpp.md#inheriting_constructors)를 참조하세요.

### <a name="c17-extended-aggregate-initialization"></a>C++17 확장된 집계 초기화

[P0017R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)

기본 클래스의 생성자가 공용이 아니지만 파생된 클래스에 액세스할 수 있는 경우 Visual Studio version 15.7의 **/std:c++17** 모드에서 파생된 형식의 개체를 초기화하기 위해 더 이상 빈 중괄호를 사용할 수 없습니다.

다음 예제에서는 C++14 준수 동작을 보여 줍니다.

```cpp
struct Derived;

struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {};

Derived d1; // OK. No aggregate init involved.
Derived d2 {}; // OK in C++14: Calls Derived::Derived()
               // which can call Base ctor.
```

C++17에서 `Derived`는 이제 집계 형식으로 간주되므로 전용 기본 생성자를 통한 `Base`의 초기화는 확장된 집합체 초기화 규칙의 일부로 직접 발생합니다. 이전에 `Base` 전용 생성자는 `Derived` 생성자를 통해 호출되었으며 friend 선언으로 인해 성공했습니다.

다음 예제에서는 **/std:c++17** 모드의 Visual Studio 버전 15.7에서 C++17 동작을 보여 줍니다.

```cpp
struct Derived;

struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {
    Derived() {} // add user-defined constructor
                 // to call with {} initialization
};

Derived d1; // OK. No aggregate init involved.

Derived d2 {}; // error C2248: 'Base::Base': cannot access
               // private member declared in class 'Base'
```

### <a name="c17-declaring-non-type-template-parameters-with-auto"></a>C++17 자동으로 비형식 템플릿 매개 변수 선언

[P0127R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)

**/std:c++17** 모드에서 컴파일러는 이제 **자동**으로 선언된 비형식 템플릿 인수의 형식을 추론할 수 있습니다.

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

이 새로운 기능의 한가지 영향은 유효한 C++14 코드는 유효하지 않을 수 있거나 서로 다른 의미 체계를 가질 수 있다는 것입니다. 예를 들어 이전에 유효하지 않았던 일부 오버로드는 이제 유효합니다. 다음 예제에서는 `foo(p)`에 대한 호출이 `foo(void*);`로 바인딩되기 때문에 컴파일하는 C++14 코드를 보여 줍니다. Visual Studio 2017 버전 15.7의 **/std:c++17** 모드에서 `foo` 함수 템플릿은 가장 일치하는 것입니다.

```cpp
template <int N> struct A;
template <typename T, T N> int foo(A<N>*) = delete;

void foo(void *);

void bar(A<0> *p)
{
    foo(p); // OK in C++14
}
```

다음 예제에서는 **/std:c++17** 모드의 Visual Studio 15.7에서 C++17 코드를 보여 줍니다.

```cpp
template <int N> struct A;
template <typename T, T N> int foo(A<N>*);

void foo(void *);

void bar(A<0> *p)
{
    foo(p); // C2280: 'int foo<int,0>(A<0>*)': attempting to reference a deleted function
}
```

### <a name="c17-elementary-string-conversions-partial"></a>C++17 기본 문자열 변환(부분)

[P0067R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html) 정수와 문자열 간 및 부동 소수점 숫자와 문자열 간의 전환에 대한 하위 수준, 로캘 무관 함수입니다. (현재 Visual Studio 15.7 미리 보기 2에서 정수에 대해서만 지원됩니다.)

### <a name="c20-avoiding-unnecessary-decay-partial"></a>C++20 불필요한 decay 방지(부분)

[P0777R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf) "decay"의 개념과 const 또는 참조 한정자의 단순한 제거 간의 차이를 추가합니다.  새 형식 특성 `remove_reference_t`는 일부 컨텍스트에서 `decay_t`를 대체합니다. `remove_cvref_t`에 대한 지원은 Visual Studio 2017 버전 15.7 미리 보기 2에서 아직 구현되지 않았습니다.

### <a name="c17-parallel-algorithms"></a>C++17 병렬 알고리즘

[P0024R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html) 병렬 처리 TS는 약간의 수정으로 표준으로 통합됩니다.

### <a name="c17-hypotx-y-z"></a>C++17 hypot(x, y, z)

[P0030R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf) 각각 세 개의 입력 매개 변수를 갖는 **float**, **double** 및 **long double** 형식에 대해 `std::hypot`로 세 개의 새로운 오버로드를 추가합니다.

### <a name="c17-filesystem"></a>C++17 \<filesystem>

[P0218R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html) 몇 가지 단어 수정으로 파일 시스템 TS를 표준으로 채택합니다.

### <a name="c17-mathematical-special-functions"></a>C++17 수학 특수 함수

[P0226R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) 수학 특수 함수에 대한 이전 기술 사양을 표준 \<cmath> 헤더로 채택합니다.

### <a name="c17-deduction-guides-for-the-stl"></a>C++17 STL에 대한 추론 가이드

[P0433R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html) 클래스 탬플릿 인수 추론에 대한 지원을 추가하는 [P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)의 C++17 도입의 이점을 활용하기 위해 STL로 업데이트합니다.

### <a name="c17-repairing-elementary-string-conversions"></a>C++17 기본 문자열 변환 복구

[P0682R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0682r1.html) P0067R5의 새 기본 문자열 변환 기능에서 새 헤더 \<charconv>로 이동하고 `std::error_code` 대신 `std::errc`를 사용하여 오류 처리 변경을 포함하는 다른 개선 사항을 만듭니다.

### <a name="c17-constexpr-for-chartraits-partial"></a>C++17 char_traits에 대한 constexpr(부분)

[P0426R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html) 상수 식에서 `std::string_view`를 사용할 수 있도록 `std::traits_type` 멤버 함수 `length`, `compare` 및 `find`로 변경합니다. (Visual Studio 2017 버전 15.6에서 Clang/LLVM에 대해서만 지원됩니다. 버전 15.7 미리 보기 2에서 ClXX에 대해서도 지원이 거의 완료되었습니다.)

## <a name="improvements_159"></a> Visual Studio 2017 버전 15.9의 개선 사항

### <a name="left-to-right-evaluation-order-for-operators-----and-"></a>연산자 ->*, [], >>, <<의 왼쪽에서 오른쪽으로 계산 순서

C++17부터 연산자 ->*, [], >> 및 \<\<의 피연산자는 왼쪽에서 오른쪽 순으로 계산해야 합니다. 컴파일러가 이 순서를 보장할 수 없는 두 가지 경우는 다음과 같습니다.
- 피연산자 식 중 하나가 값으로 전달된 개체이거나 값으로 전달된 개체를 포함하는 경우, 또는
- **/clr**을 사용하여 컴파일할 때 피연산자 중 하나가 개체 또는 배열 요소의 필드인 경우.

컴파일러는 왼쪽에서 오른쪽으로 계산을 보장할 수 없는 경우 경고 [C4866](https://docs.microsoft.com/cpp/error-messages/compiler-warnings/c4866?view=vs-2017)을 생성합니다. 이 경고는 **/std:c++17** 이상이 지정된 경우에만 생성됩니다. 이러한 연산자의 왼쪽에서 오른쪽으로 순서 요구 사항이 C++17에서 도입되었기 때문입니다.

이 경고를 해결하려면 먼저 피연산자 계산으로 순서에 종속되는 부작용이 발생하는 경우처럼 피연산자의 왼쪽에서 오른쪽으로 계산이 필요한지 고려합니다. 대부분의 경우 피연산자가 계산되는 순서는 눈에 띄는 영향을 미치지 않습니다. 계산 순서가 왼쪽에서 오른쪽이어야 하는 경우, 대신 const 참조로 피연산자를 전달할 수 있는지 여부를 고려합니다. 이렇게 변경하면 다음 코드 샘플에서 경고가 제거됩니다.

```cpp
// C4866.cpp
// compile with: /w14866 /std:c++17

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x) : x(x) {}
    HasCopyConstructor(const HasCopyConstructor& h) : x(h.x) { }
};

int operator>>(HasCopyConstructor a, HasCopyConstructor b) { return a.x >> b.x; }

// This version of operator>> does not trigger the warning:
// int operator>>(const HasCopyConstructor& a, const HasCopyConstructor& b) { return a.x >> b.x; }

int main()
{
    HasCopyConstructor a{ 1 };
    HasCopyConstructor b{ 2 };

    a>>b;        // C4866 for call to operator>>
};
```

## <a name="bug-fixes-in-visual-studio-versions-150-153update153-155update155-157update157-158update158-and-159update159"></a>Visual Studio 버전 15.0, [15.3](#update_153), [15.5](#update_155), [15.7](#update_157), [15.8](#update_158) 및 [15.9](#update_159)의 버그 수정

### <a name="copy-list-initialization"></a>Copy-list-initialization

Visual Studio 2017에서는 Visual Studio 2015에서 파악되지 않았고 크래시나 정의되지 않은 런타임 동작을 일으킬 수 있는 이니셜라이저 목록을 사용한 개체 만들기에 관련된 컴파일러 오류를 정확히 발생시킵니다. N4594 13.3.1.7p1에 따라 copy-list-initialization에서 컴파일러는 오버로드 확인을 위해 명시적 생성자를 고려해야 하지만 실제로 오버로드가 선택되면 오류를 발생시켜야 합니다.

다음 두 가지 예제는 Visual Studio 2015에서 컴파일되지만 Visual Studio 2017에서 컴파일되지 않습니다.

```cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 }; // error C3445: copy-list-initialization of 'A' cannot use an explicit constructor
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot convert from 'int' to 'const A &'

}
```

오류를 수정하려면 직접 초기화를 사용합니다.

```cpp
A a1{ 1 };
const A& a2{ 1 };
```

Visual Studio 2015에서 컴파일러는 일반 copy-initialization과 같은 방식으로 copy-list-initialization을 잘못 처리했고 오버로드 확인을 위해 생성자 변환만 고려했습니다. 다음 예제에서 Visual Studio 2015에서는 MyInt(23)를 선택하지만 Visual Studio 2017에서는 정확히 오류를 발생시킵니다.

```cpp
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyStore {
    explicit MyStore(int initialCapacity);
};

struct MyInt {
    MyInt(int i);
};

struct Printer {
    void operator()(MyStore const& s);
    void operator()(MyInt const& i);
};

void f() {
    Printer p;
    p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```

이 예제는 이전 예제와 비슷하지만 다른 오류를 발생시킵니다. 이 예제는 Visual Studio 2015에서는 성공하지만 Visual Studio 2017(C2668 포함)에서는 실패합니다.

```cpp
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```

### <a name="deprecated-typedefs"></a>사용되지 않는 형식 정의

Visual Studio 2017에서는 이제 클래스 또는 구조체에서 선언된 사용되지 않는 형식 정의에 대한 올바른 경고를 실행합니다. 다음 예제는 Visual Studio 2015에서는 경고 없이 컴파일되지만 Visual Studio 2017에서는 C4996를 생성합니다.

```cpp
struct A
{
    // also for __declspec(deprecated)
    [[deprecated]] typedef int inttype;
};

int main()
{
    A::inttype a = 0; // C4996 'A::inttype': was declared deprecated
}
```

### <a name="constexpr"></a>constexpr

Visual Studio 2017에서는 조건부 계산 연산의 왼쪽 피연산자가 constexpr 컨텍스트에서 유효하지 않을 경우 정확히 오류를 발생시킵니다. 다음 코드는 Visual Studio 2017이 아닌 Visual Studio 2015에서 컴파일합니다(C3615 constexpr 함수 ‘f’는 상수 식이 될 수 없음).

```cpp
template<int N>
struct array
{
    int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615
}
```

오류를 수정하려면 `array::size()` 함수를 `constexpr`로 선언하거나 `f`에서 `constexpr` 한정자를 제거합니다.

### <a name="class-types-passed-to-variadic-functions"></a>variadic 함수에 전달된 클래스 형식

Visual Studio 2017에서 printf와 같이 variadic 함수에 전달된 클래스 또는 구조체는 일반적으로 복사 가능합니다. 해당 개체를 전달할 때 컴파일러는 비트 복사본을 만들기만 하고 생성자 또는 소멸자를 호출하지 않습니다.

```cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function.
                        // note: the constructor and destructor will not be called;
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```

오류를 수정하려면 일반적으로 복사 가능한 형식을 반환하는 멤버 함수를 호출하거나

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

정적 캐스트를 수행하여 개체를 변환한 후 전달합니다.

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

CString을 사용하여 빌드 및 관리되는 문자열의 경우 제공된 `operator LPCTSTR()`를 사용하여 CString 개체를 서식 문자열에 필요한 C 포인터에 캐스트해야 합니다.

```cpp
CString str1;
CString str2 = _T("hello!");
str1.Format(_T("%s"), static_cast<LPCTSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>클래스 생성의 cv 한정자

Visual Studio 2015에서는 컴파일러가 생성자 호출을 통해 클래스 개체를 생성할 때 cv 한정자를 잘못 무시하는 경우가 있습니다. 이로 인해 잠재적으로 크래시 또는 예기치 않은 런타임 동작이 발생할 수 있습니다. 다음 예제는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017에서는 컴파일러 오류를 발생시킵니다.

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

오류를 수정하려면 `operator int()`를 `const`로 선언합니다.

### <a name="access-checking-on-qualified-names-in-templates"></a>템플릿의 정규화된 이름에 대한 액세스 검사

이전 버전의 컴파일러는 일부 템플릿 컨텍스트에서 정규화된 이름에 대한 액세스 검사를 수행하지 않았습니다. 이는 이름에 액세스할 수 없기 때문에 대체에 실패할 것으로 예상되는 경우 예상되는 SFINAE 동작을 방해할 수 있습니다. 따라서 컴파일러가 연산자의 잘못된 오버로드를 잘못 호출하기 때문에 잠재적으로 런타임에 크래시나 예기치 않은 동작이 발생했을 수 있습니다. Visual Studio 2017에서는 컴파일러 오류가 발생합니다. 구체적인 오류는 달라질 수 있지만 일반적으로 오류는 “C2672 일치하는 오버로드된 함수가 없습니다.”입니다. 다음 코드는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017에서는 오류를 발생시킵니다.

```cpp
#include <type_traits>

template <class T> class S {
    typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x);

int main()
{
    f(10); // C2672: No matching overloaded function found.
}
```

### <a name="missing-template-argument-lists"></a>누락된 템플릿 인수 목록

Visual Studio 2015 이하에서는 템플릿이 템플릿 매개 변수 목록에 나타날 때(예: 기본 템플릿 인수 또는 형식 없는 템플릿 매개 변수의 일부로) 컴파일러가 누락된 템플릿 인수 목록을 진단하지 않았습니다. 이로 인해 컴파일러 크래시나 예기치 않은 런타임 동작을 포함하여 예기치 않은 동작이 발생할 수 있습니다. 다음 코드는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017에서는 오류를 생성합니다.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>SFINAE 식

SFINAE 식을 지원하기 위해 이제 컴파일러는 템플릿이 인스턴스화가 아니라 선언될 때 decltype 인수를 구문 분석합니다. 따라서 decltype 인수에 독립적 특수화가 있는 경우 이 특수화는 인스턴스화 시점으로 연기되지 않고 즉시 처리되며 결과 오류가 이 시점에 진단됩니다.

다음 예제에서는 선언 시점에 발생한 컴파일러 오류를 보여 줍니다.

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT>
class IsCallable
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

### <a name="classes-declared-in-anonymous-namespaces"></a>익명 네임스페이스에 선언된 클래스

C++ 표준에 따라 익명 네임스페이스 내에 선언된 클래스는 내부 링크가 있으므로 내보낼 수 없습니다. Visual Studio 2015 이전 버전에서는 이 규칙이 적용되지 않았습니다. Visual Studio 2017에서는 이 규칙이 부분적으로 적용됩니다. 다음 예제에서는 Visual Studio 2017에서 "오류 C2201: const anonymous namespace::S1::vftable: 가져오거나 내보내려면 외부 링크가 있어야 합니다." 오류를 발생시킵니다.

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>값 클래스 멤버에 대한 기본 이니셜라이저(C++/CLI)

Visual Studio 2015 이하에서는 컴파일러가 값 클래스 멤버에 대한 기본 멤버 이니셜라이저를 허용하지만 무시했습니다. 값 클래스의 기본 초기화는 항상 멤버를 0으로 초기화하고 기본 생성자는 허용되지 않습니다. Visual Studio 2017에서는 기본 멤버 이니셜라이저가 이 예제에 표시된 대로 컴파일러 오류를 발생시킵니다.

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // is not allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>기본 인덱서(C++/CLI)

Visual Studio 2015 이하에서는 컴파일러가 기본 속성을 기본 인덱서로 잘못 식별하는 경우가 있었습니다. 속성에 액세스하는 데 식별자 `default`를 사용하여 문제를 해결할 수 있었습니다. `default`가 C++11에서 키워드로 도입된 이후 해결 방법 자체가 문제가 되었습니다. 따라서 Visual Studio 2017에서는 해결 방법이 필요했던 버그가 수정되었고 이제 컴파일러는 `default`가 클래스에 대한 기본 속성에 액세스하는 데 사용될 경우 오류를 발생시킵니다.

```cpp
//class1.cs

using System.Reflection;
using System.Runtime.InteropServices;

namespace ClassLibrary1
{
    [DefaultMember("Value")]
    public class Class1
    {
        public int Value
        {
            // using attribute on the return type triggers the compiler bug
            [return: MarshalAs(UnmanagedType.I4)]
            get;
        }
    }
    [DefaultMember("Value")]
    public class Class2
    {
        public int Value
        {
            get;
        }
    }
}

// code.cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value; // error
       r1->default;
       r2->Value;
       r2->default; // error
}
```

Visual Studio 2017에서는 이름을 사용하여 값 속성에 둘 다 액세스할 수 있습니다.

```cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="update_153"></a> Visual Studio 2017 버전 15.3의 버그 수정

### <a name="calls-to-deleted-member-templates"></a>삭제된 멤버 템플릿에 대한 호출

Visual Studio의 이전 버전에서는 경우에 따라 컴파일러가 런타임에 충돌을 일으킬 수 있는 삭제된 멤버 템플릿에 대한 잘못된 형식의 호출에 관련된 오류를 내보내지 못합니다. 다음 코드는 C2280 "'int S\<int>::f\<int>(void)': 삭제된 함수를 참조하려고 합니다."를 생성합니다.

```cpp
template<typename T>
struct S {
   template<typename U> static int f() = delete;
};

void g()
{
   decltype(S<int>::f<int>()) i; // this should fail
}
```

오류를 해결하려면 i를 `int`로 선언합니다.

### <a name="pre-condition-checks-for-type-traits"></a>형식 특성에 대한 전제 조건 검사

Visual Studio 2017 버전 15.3에서는 표준을 더 엄격하게 따르도록 형식 특성에 대한 전제 조건 검사가 향상되었습니다. 해당 검사는 할당 가능합니다. 다음 코드는 Visual Studio 2017 버전 15.3에서 C2139를 생성합니다.

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>네이티브에서 관리로의 마샬링에 대한 새로운 컴파일러 경고 및 런타임 검사

관리되는 함수에서 네이티브 함수로 호출하려면 마샬링이 필요합니다. CLR는 마샬링을 수행하지만 C++ 의미 체계를 이해하지 못합니다. 네이티브 개체를 값으로 전달하면 CLR는 개체의 복사 생성자를 호출하거나 런타임에 정의되지 않은 동작을 생성할 수 있는 BitBlt를 사용합니다.

이제 컴파일러는 컴파일 시간에 삭제된 복사 생성자를 포함하는 네이티브 개체가 네이티브 경계와 관리되는 경계 사이에 값으로 전달됨을 알 수 있는 경우 경고를 내보냅니다. 컴파일러가 컴파일 시간에 알 수 없는 경우 컴파일러는 잘못된 형식의 마샬링이 수행될 때 프로그램이 즉시 `std::terminate`를 호출하도록 런타임 검사를 삽입합니다. Visual Studio 2017 15.3에서 다음 코드는 경고 C4606을 생성합니다. "'A': 네이티브 및 관리 경계에서 인수를 값별로 전달하려면 유효한 복사 생성자가 필요합니다. 이 생성자가 없으면 런타임 동작이 정의되지 않습니다.”

```cpp
class A
{
public:
   A() : p_(new int) {}
   ~A() { delete p_; }

   A(A const &) = delete;
   A(A &&rhs) {
   p_ = rhs.p_;
}

private:
   int *p_;
};

#pragma unmanaged

void f(A a)
{
}

#pragma managed

int main()
{
    f(A()); // This call from managed to native requires marshalling. The CLR doesn't understand C++ and uses BitBlt, which results in a double-free later.
}
```

오류를 해결하려면 `#pragma managed` 지시문을 제거하여 호출자를 네이티브로 표시하고 마샬링을 피합니다.

### <a name="experimental-api-warning-for-winrt"></a>WinRT에 대한 실험적 API 경고

실험 및 피드백용으로 릴리스된 WinRT API는 `Windows.Foundation.Metadata.ExperimentalAttribute`로 데코레이트됩니다. Visual Studio 2017 버전 15.3에서는 컴파일러에서 특성을 발견하면 C4698 경고를 생성합니다. 이전 Windows SDK 버전의 몇몇 API는 이미 특성으로 데코레이트되었고 이러한 API를 호출하면 이제 이 컴파일러 경고가 트리거됩니다. 최신 Windows SDK에서는 모든 제공된 형식에서 특성이 제거되지만 이전 SDK를 사용 중인 경우에는 모든 제공된 형식 호출에 대해 이러한 경고를 표시하지 않아야 합니다.

다음 코드는 경고 C4698을 생성합니다. “‘Windows::Storage::IApplicationDataStatics2::GetForUserAsync’는 평가 목적으로만 제공되며 향후 업데이트에서 변경되거나 제거될 수 있습니다.”

```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync(); //C4698
```

이 경고를 사용하지 않도록 설정하려면 #pragma를 추가합니다.

```cpp
#pragma warning(push)
#pragma warning(disable:4698)

Windows::Storage::IApplicationDataStatics2::GetForUserAsync();

#pragma warning(pop)
```

### <a name="out-of-line-definition-of-a-template-member-function"></a>템플릿 멤버 함수의 확장 정의

Visual Studio 2017 버전 15.3에서는 클래스에서 선언되지 않은 템플릿 멤버 함수의 확장 정의를 발견하면 오류를 생성합니다. 다음 코드는 오류 C2039를 생성합니다. ‘f’:이 ‘S’의 멤버가 아닙니다.

```cpp
struct S {};

template <typename T>
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
```

오류를 해결하려면 클래스에 선언을 추가합니다.

```cpp
struct S {
    template <typename T>
    void f(T t);
};
template <typename T>
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>“this” 포인터의 주소를 가져오려고 합니다.

C++에서 `this`는 X에 대한 형식 포인터의 prvalue입니다. `this`의 주소를 가져오거나 lvalue 참조에 바인딩할 수 없습니다. 이전 버전의 Visual Studio에서는 컴파일러를 통해 캐스트를 수행하여 이 제한 사항을 회피할 수 있습니다. Visual Studio 2017 버전 15.3에서는 컴파일러에서 C2664 오류를 생성합니다.

### <a name="conversion-to-an-inaccessible-base-class"></a>액세스할 수 없는 기본 클래스로의 변환

Visual Studio 2017 버전 15.3에서는 형식을 액세스할 수 없는 기본 클래스로 변환하려고 할 때 오류를 생성합니다. 이제는 컴파일러에서 "오류 C2243: 'type cast': 변환('D *'에서 'B *'(으)로)이 있지만 액세스할 수 없습니다."를 발생시킵니다. 다음 코드는 형식이 잘못되었고 런타임에 충돌을 일으킬 수 있습니다. 이제 컴파일러는 다음과 같은 코드를 발견할 때 C2243을 생성합니다.

```cpp
#include <memory>

class B { };
class D : B { }; // C2243. should be public B { };

void f()
{
   std::unique_ptr<B>(new D());
}
```

### <a name="default-arguments-are-not-allowed-on-out-of-line-definitions-of-member-functions"></a>기본 인수는 멤버 함수의 확장 정의에서 허용되지 않음

템플릿 클래스의 멤버 함수에 대한 확장 정의에는 기본 인수를 사용할 수 없습니다. 컴파일러에서 **/permissive** 아래에 경고를, **/permissive-** 아래에 하드 오류를 발생시킵니다.

이전 버전의 Visual Studio에서는 다음과 같은 잘못된 코드로 인해 잠재적으로 런타임 크래시가 발생할 수 있었습니다. Visual Studio 2017 버전 15.3은 경고 C5034를 생성합니다. 'A\<T>::f': 클래스 템플릿 멤버의 확장 정의에는 기본 인수가 포함될 수 없습니다.

```cpp
template <typename T>
struct A {
    T f(T t, bool b = false);
};

template <typename T>
T A<T>::f(T t, bool b = false) // C5034
{
    // ...
}
```

오류를 해결하려면 `= false` 기본 인수를 제거합니다.

### <a name="use-of-offsetof-with-compound-member-designator"></a>복합 멤버 지정자와 함께 offsetof 사용

Visual Studio 2017 버전 15.3에서 *m*이 "복합 멤버 지정자"인 `offsetof(T, m)`를 사용하면 **/Wall** 옵션으로 컴파일할 때 경고가 발생합니다. 다음 코드는 형식이 잘못되었고 런타임에 크래시가 발생할 수 있습니다. Visual Studio 2017 버전 15.3에서 "경고 C4841: 비표준 확장이 사용됨: 복합 멤버 지정자가 offsetof에 사용되었습니다."를 생성합니다.

```cpp
struct A {
   int arr[10];
};

// warning C4841: non-standard extension used: compound member designator in offsetof
constexpr auto off = offsetof(A, arr[2]);
```

코드를 수정하려면 pragma를 사용하여 경고를 사용하지 않도록 설정하거나 `offsetof`를 사용하지 않도록 코드를 변경합니다.

```cpp
#pragma warning(push)
#pragma warning(disable: 4841)
constexpr auto off = offsetof(A, arr[2]);
#pragma warning(pop)
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>정적 데이터 멤버 또는 멤버 함수와 함께 offsetof 사용

Visual Studio 2017 버전 15.3에서 *m*이 정적 데이터 멤버 또는 멤버 함수를 참조하는 `offsetof(T, m)`를 사용하면 오류가 발생합니다. 다음 코드는 “오류 C4597: 정의되지 않은 동작: offsetof가 멤버 함수 ‘foo’에 적용되었습니다.” 및 “오류 C4597: 정의되지 않은 동작: offsetof가 정적 데이터 멤버 ‘bar’에 적용되었습니다.”를 생성합니다.

```cpp
#include <cstddef>

struct A {
   int foo() { return 10; }
   static constexpr int bar = 0;
};

constexpr auto off = offsetof(A, foo);
constexpr auto off2 = offsetof(A, bar);
```

이 코드는 형식이 잘못되었고 런타임에 크래시가 발생할 수 있습니다. 오류를 해결하려면 정의되지 않은 동작을 더 이상 호출하지 않도록 코드를 변경합니다. 이는 C++ 표준에서 허용되지 않는 이식할 수 없는 코드입니다.

### <a name="declspec"></a> declspec 특성에 대한 새로운 경고

Visual Studio 2017 버전 15.3에서는 `__declspec(...)`가 `extern "C"` 링크 사양 앞에 적용되면 컴파일러에서 더 이상 특성을 무시하지 않습니다. 이전 버전에서는 컴파일러가 런타임 의미를 가질 수 있는 특성을 무시합니다. **/Wall** 및 **/WX** 옵션이 설정되면 다음 코드는 “경고 C4768: 링크 사양 앞의 __declspec 특성은 무시됩니다.”를 생성합니다.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

경고를 해결하려면 extern “C”를 먼저 삽입합니다.

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

이 경고는 15.3에서 기본적으로 꺼져 있지만 15.5에서는 기본적으로 켜져 있으며, **/Wall** **/WX**로 컴파일된 코드에만 영향을 줍니다.

### <a name="decltype-and-calls-to-deleted-destructors"></a>decltype 및 삭제된 소멸자 호출

이전 버전의 Visual Studio에서 컴파일러는 삭제된 소멸자 호출이 ‘decltype’과 연결된 식의 컨텍스트에서 발생한 시점을 검색하지 않았습니다. Visual Studio 2017 버전 15.3에서 다음 코드는 "오류 C2280: 'A\<T>::~A(void)': 삭제된 함수를 참조하려고 시도 중"을 생성합니다.

```cpp
template<typename T>
struct A
{
   ~A() = delete;
};

template<typename T>
auto f() -> A<T>;

template<typename T>
auto g(T) -> decltype((f<T>()));

void h()
{
   g(42);
}
```

### <a name="uninitialized-const-variables"></a>초기화되지 않은 const 변수

Visual Studio 2017 RTW 릴리스에는 ‘const’ 변수가 초기화되지 않으면 C++ 컴파일러가 진단을 실행하지 않는 재발 문제가 있었습니다. 이 재발 문제는 Visual Studio 2017 버전 15.3에서 수정되었습니다. 다음 코드는 이제 "경고 C4132: 'Value': const 개체를 초기화해야 합니다."를 생성합니다.

```cpp
const int Value; //C4132
```

오류를 해결하려면 `Value`에 값을 할당합니다.

### <a name="empty-declarations"></a>빈 선언

Visual Studio 2017 버전 15.3에서는 이제 기본 제공 형식이 아닌 모든 형식의 빈 선언에 대해 경고를 생성합니다. 다음 코드는 모든 네 가지 선언에 대한 수준 2 C4091 경고를 생성합니다.

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };

int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

경고를 제거하려면 빈 선언을 주석으로 처리하거나 제거합니다. 명명되지 않은 개체에 부작용(예: RAII)을 포함하려면 개체에 이름을 지정해야 합니다.

경고는 **/Wv:18**에서는 제외되고 기본적으로 경고 수준 W2에서 켜집니다.

### <a name="stdisconvertible-for-array-types"></a>배열 형식에 대한 std::is_convertible

이전 버전의 컴파일러는 배열 형식에 대한 [std::is_convertible](../../standard-library/is-convertible-class.md)에 대해 잘못된 결과를 제공했습니다. 따라서 라이브러리 작성자는 `std::is_convertible<...>` 형식 특성을 사용할 때 특별히 Visual C++ 컴파일러를 사용해야 했습니다. 다음 예제에서는 정적 어설션이 이전 버전의 Visual Studio에서는 통과하지만 Visual Studio 2017 업데이트 버전 15.3에서는 실패합니다.

```cpp
#include <type_traits>

using Array = char[1];

static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

`std::is_convertible<From, To>` 가상의 함수 정의가 올바른 형식으로 되어 있는지 확인하는 방법으로 계산됩니다.

```cpp
   To test() { return std::declval<From>(); }
```

### <a name="private-destructors-and-stdisconstructible"></a>비공개 소멸자 및 std::is_constructible

이전 버전의 컴파일러에서는 [std::is_constructible](../../standard-library/is-constructible-class.md)의 결과를 결정할 때 소멸자가 비공개인지 여부를 무시했습니다. 그러나 지금은 비공개 여부를 고려합니다. 다음 예제에서는 정적 어설션이 이전 버전의 Visual Studio에서는 통과하지만 Visual Studio 2017 업데이트 버전 15.3에서는 실패합니다.

```cpp
#include <type_traits>

class PrivateDtor {
   PrivateDtor(int) { }
private:
   ~PrivateDtor() { }
};

// This assertion used to succeed. It now correctly fails.
static_assert(std::is_constructible<PrivateDtor, int>::value);
```

비공개 소멸자는 형식을 non-constructible로 만듭니다. `std::is_constructible<T, Args...>` 다음 선언이 작성된 것처럼 계산됩니다.

```cpp
   T obj(std::declval<Args>()...)
```

이 호출은 소멸자 호출을 의미합니다.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: 모호한 오버로드 확인

이전 버전의 컴파일러에서는 선언 및 인수 종속성 조회를 모두 사용하여 여러 후보를 찾을 때 모호성을 검색하지 못하는 경우가 종종 있었습니다. 그러면 잘못된 오버로드를 선택하고 예기치 않은 런타임 동작이 발생할 수 있습니다. 다음 예제에서는 Visual Studio 2017 버전 15.3에서 "C2668 'f': 오버로드된 함수에 대한 호출이 모호합니다."를 정확히 발생시킵니다.

```cpp
namespace N {
   template<class T>
   void f(T&, T&);

   template<class T>
   void f();
}

template<class T>
void f(T&, T&);

struct S {};
void f()
{
   using N::f;

   S s1, s2;
   f(s1, s2); // C2668
}
```

`::f()`를 호출하려는 경우 코드를 수정하려면 사용 중인 `N::f` 문을 제거합니다.

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: 로컬 함수 선언 및 인수 종속 조회

로컬 함수 선언은 바깥쪽 범위에 있는 함수 선언을 숨기고 인수 종속 조회를 사용하지 않도록 설정합니다. 그러나 이 경우에는 이전 버전의 컴파일러가 인수 종속 조회를 수행했으므로 잘못된 오버로드를 선택하고 예기치 않은 런타임 동작이 발생할 가능성이 있습니다. 일반적으로 오류는 로컬 함수 선언의 잘못된 시그니처 때문입니다. 다음 예제에서는 Visual Studio 2017 버전 15.3이 "C2660 'f': 함수는 2개의 매개 변수를 사용하지 않습니다."을 정확히 발생시킵니다.

```cpp
struct S {};
void f(S, int);

void g()
{
   void f(S); // C2660 'f': function does not take 2 arguments:
   // or void f(S, int);
   S s;
   f(s, 0);
}
```

이 문제를 해결하려면 `f(S)` 시그니처를 변경하거나 제거합니다.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: 이니셜라이저 목록에서 초기화 순서

클래스 구성원은 이니셜라이저 목록에 나타나는 순서가 아니라 선언된 순서대로 초기화됩니다. 이전 버전의 컴파일러는 이니셜라이저 목록의 순서가 선언 순서와 다른 경우 경고를 표시하지 않았습니다. 이로 인해 한 구성원의 초기화가 이미 초기화되고 있는 목록의 다른 구성원에 종속되는 경우에는 정의되지 않은 런타임 동작이 발생할 수 있었습니다. 다음 예제에서는 Visual Studio 2017 버전 15.3(**/Wall** 포함)에서 "C5038: 'A::y' 데이터 멤버가 'A::y' 데이터 멤버 다음에 초기화됩니다."라는 경고를 발생시킵니다.

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

문제를 해결하려면 선언과 같은 순서가 되도록 이니셜라이저 목록을 정렬합니다. 하나 또는 두 이니셜라이저가 기본 클래스 구성원을 참조하는 경우 유사한 경고가 발생합니다.

이 경고는 기본적으로 사용하지 않도록 설정되어 있으며 **/Wall**로 컴파일된 코드에만 영향을 줍니다.

## <a name="update_155"></a> Visual Studio 2017 15.5 버전의 버그 수정 및 기타 동작 변경

### <a name="partial-ordering-change"></a>부분 순서 변경

컴파일러는 이제 다음 코드를 올바르게 거부하고 올바른 오류 메시지를 제공합니다.

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(const T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);    // C2668
}
```

```Output
t161.cpp
t161.cpp(16): error C2668: 'f': ambiguous call to overloaded function
t161.cpp(8): note: could be 'int f<int*>(const T &)'
        with
        [
            T=int*
        ]
t161.cpp(2): note: or       'int f<int>(int*)'
t161.cpp(16): note: while trying to match the argument list '(int*)'
```

위의 예에서 문제는 형식에 두 가지 차이점이 있다는 것입니다(const 및 non-const와 pack 및 non-pack). 컴파일러 오류를 제거하려면 차이점 중 하나를 제거합니다. 이렇게 하면 컴파일러가 함수의 순서를 명확하게 지정할 수 있습니다.

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);
}
```

### <a name="exception-handlers"></a>예외 처리기

배열 또는 함수 형식에 대한 참조 처리기는 모든 예외 개체에 일치하지 않습니다. 컴파일러는 이제 이 규칙을 올바르게 적용하고 수준 4 경고를 생성합니다. 또한 **/Zc:strictStrings**가 사용될 경우 `char*` 또는 `wchar_t*` 처리기를 더 이상 문자열 리터럴에 일치시키지 않습니다.

```cpp
int main()
{
    try {
        throw "";
    }
    catch (int (&)[1]) {} // C4843 (This should always be dead code.)
    catch (void (&)()) {} // C4843 (This should always be dead code.)
    catch (char*) {} // This should not be a match under /Zc:strictStrings
}
```

```Output
warning C4843: 'int (&)[1]': An exception handler of reference to array or function type is unreachable, use 'int*' instead
warning C4843: 'void (__cdecl &)(void)': An exception handler of reference to array or function type is unreachable, use 'void (__cdecl*)(void)' instead
```

다음 코드에서는 오류를 방지합니다.

```cpp
catch (int (*)[1]) {}
```

### <a name="tr1"></a>std::tr1 namespace is deprecated

비표준 `std::tr1` 네임스페이스는 이제 C++14 및 C++17 모드에서 사용되지 않는 것으로 표시됩니다. Visual Studio 2017 15.5 버전에서 다음 코드를 실행하면 C4996이 발생합니다.

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::tr1::function<int (int, int)> f = std::plus<int>(); //C4996
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

```Output
warning C4996: 'std::tr1': warning STL4002: The non-Standard std::tr1 namespace and TR1-only machinery are deprecated and will be REMOVED. You can define _SILENCE_TR1_NAMESPACE_DEPRECATION_WARNING to acknowledge that you have received this warning.
```

이 오류를 해결하려면 `tr1` 네임스페이스에 대한 참조를 제거합니다.

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::function<int (int, int)> f = std::plus<int>();
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

### <a name="annex_d"></a>부록 D의 표준 라이브러리 기능이 사용되지 않는 것으로 표시됩니다.

**/std:c++17** 모드 컴파일러 스위치가 설정되면 부록 D의 거의 모든 표준 라이브러리 기능이 사용되지 않는 것으로 표시됩니다.

Visual Studio 2017 15.5 버전에서 다음 코드를 실행하면 C4996이 발생합니다.

```cpp
#include <iterator>

class MyIter : public std::iterator<std::random_access_iterator_tag, int> {
public:
    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

```Output
warning C4996: 'std::iterator<std::random_access_iterator_tag,int,ptrdiff_t,_Ty*,_Ty &>::pointer': warning STL4015: The std::iterator class template (used as a base class to provide typedefs) is deprecated in C++17. (The <iterator> header is NOT deprecated.) The C++ Standard has never required user-defined iterators to derive from std::iterator. To fix this warning, stop deriving from std::iterator and start providing publicly accessible typedefs named iterator_category, value_type, difference_type, pointer, and reference. Note that value_type is required to be non-const, even for constant iterators. You can define _SILENCE_CXX17_ITERATOR_BASE_CLASS_DEPRECATION_WARNING or _SILENCE_ALL_CXX17_DEPRECATION_WARNINGS to acknowledge that you have received this warning.
```

이 오류를 해결하려면 다음 코드에 설명된 것처럼 경고 텍스트의 지침을 따르세요.

```cpp
#include <iterator>

class MyIter {
public:
    typedef std::random_access_iterator_tag iterator_category;
    typedef int value_type;
    typedef ptrdiff_t difference_type;
    typedef int* pointer;
    typedef int& reference;

    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

### <a name="unreferenced-local-variables"></a>참조되지 않은 지역 변수

Visual Studio 15.5에서는 다음 코드에 표시된 것처럼 C4189 경고가 더 많은 경우에 내보내집니다.

```cpp
void f() {
    char s[2] = {0}; // C4189. Either use the variable or remove it.
}
```

```Output
warning C4189: 's': local variable is initialized but not referenced
```

이 오류를 해결하려면 사용되지 않는 변수를 제거합니다.

### <a name="single-line-comments"></a>단일 줄 주석

Visual Studio 2017 15.5 버전에서는 C 컴파일러에서 더 이상 C4001 및 C4179 경고를 내보내지 않습니다. 이전에는 이러한 경고가 **/Za** 컴파일러 스위치하에서만 내보내졌습니다.  C99 이후로 단일 줄 주석이 표준에 포함되었으므로 이러한 경고는 더 이상 필요하지 않습니다.

```cpp
/* C only */
#pragma warning(disable:4001) //C4619
#pragma warning(disable:4179)
// single line comment
//* single line comment */
```

```Output
warning C4619: #pragma warning: there is no warning number '4001'
```

코드가 이전 버전과 호환될 필요가 없는 경우 C4001/C4179 비표시 오류(Suppression)를 제거하여 경고를 방지할 수 있습니다. 코드가 이전 버전과 호환되어야 할 경우 C4619만 표시되지 않게 합니다.

```C

/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```

### <a name="declspec-attributes-with-extern-c-linkage"></a>외부 "C" 링크가 있는 __declspec 특성

이전 버전의 Visual Studio에서는 `extern "C"` 링크 사양 앞에 `__declspec(...)` 가 적용된 경우 컴파일러가 `__declspec(...)` 특성을 무시했습니다. 이 동작은 사용자가 의도하지 않은 코드 생성을 유발했으며 런타임에도 영향을 줄 가능성이 있었습니다. 이 경고는 Visual Studio 15.3 버전에서 추가되었지만 기본적으로 꺼져 있었습니다. Visual Studio 2017 15.5 버전에서 이 경고는 기본적으로 활성화되어 있습니다.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

```Output
warning C4768: __declspec attributes before linkage specification are ignored
```

이 오류를 해결하려면 __declspec 특성 앞에 링크 사양을 추가하세요.

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

이 새로운 경고 C4768은 Visual Studio 2017 15.3 이하 버전과 함께 제공된 일부 Windows SDK 헤더에서 표시됩니다(예: RS2 SDK라고도 하는 10.0.15063.0 버전). 그러나 이후 버전의 Windows SDK 헤더(특히 ShlObj.h 및 ShlObj_core.h)는 이 경고를 생성하지 않도록 수정되었습니다. Windows SDK 헤더에서 이 경고가 발생하면 이러한 작업을 수행할 수 있습니다.

1. Visual Studio 2017 버전 15.5 릴리스와 함께 제공된 최신 Windows SDK로 전환합니다.

1. Windows SDK 헤더 문의 #include 주위에 있는 경고를 끕니다.

```cpp
   #pragma warning (push)
   #pragma warning(disable:4768)
   #include <shlobj.h>
   #pragma warning (pop)
   ```

### <a name="extern_linkage"></a>extern constexpr 링크

이전 버전의 Visual Studio에서는 `constexpr` 변수에 `extern`이 표시된 경우에도 컴파일러가 항상 해당 변수에 내부 링크를 제공했습니다. Visual Studio 2017 15.5 버전에서 새 컴파일러 스위치(**/Zc:externConstexpr**)는 올바른 표준 준수 동작을 활성화합니다. 결국 이는 기본값이 됩니다.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

헤더 파일에 `extern constexpr`로 선언된 변수가 포함되어 있으면 중복 선언을 올바르게 결합하기 위해 해당 변수에 `__declspec(selectany)`를 표시해야 합니다.

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>불완전한 클래스 형식에는 typeid를 사용할 수 없습니다.

이전 버전의 Visual Studio에서는 컴파일러가 다음 코드를 잘못 허용하여 형식 정보가 잘못될 가능성이 있었습니다. Visual Studio 2017 15.5 버전에서는 컴파일러에서 오류를 올바르게 생성합니다.

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdisconvertible-target-type"></a>std::is_convertible target type

`std::is_convertible` 대상 유형이 유효한 반환 형식이어야 합니다. 이전 버전의 Visual Studio에서는 컴파일러가 추상 형식을 잘못 허용하여 오버로드 확인이 잘못되고 의도하지 않은 런타임 동작이 발생할 가능성이 있었습니다.  이제 다음 코드는 C2338을 올바르게 생성합니다.

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D, B>::value, "fail"); // C2338 in 15.5
```

오류를 방지하려면 `is_convertible` 사용 시 포인터 형식을 비교해야 합니다. 하나의 형식이 추상적일 경우 non-pointer-type 비교가 실패할 수 있기 때문입니다.

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D *, B *>::value, "fail");
```

### <a name="noexcept_removal"></a> 동적 예외 사양 제거 및 noexcept

C++17에서 `throw()`는 `noexcept`에 대한 별칭이고, `throw(<type list>)` 및 `throw(...)`가 제거되었으며 특정 형식에 `noexcept`가 포함될 수 있습니다. 따라서 C++14 이하를 준수하는 코드와 소스 호환성 문제가 발생할 수 있습니다. 전체적으로 C++17 모드를 사용 중일 때 **/Zc:noexceptTypes-** 스위치를 사용하여 `noexcept`의 C++14 버전으로 되돌릴 수 있습니다. 이렇게 하면 모든 `throw()` 코드를 동시에 다시 작성할 필요 없이 C++17에 부합하도록 소스 코드를 업데이트할 수 있습니다.

또한 컴파일러는 이제 새로운 경고 C5043과 관련하여 C++17 모드의 선언이나 **/permissive-** 를 사용하여 더 많은 불일치 예외 사양을 진단합니다.

다음 코드는 Visual Studio 2017 버전 15.5에서 **/std:c++17** 스위치가 적용될 때 C5043 및 C5040을 생성합니다.

```cpp
void f() throw(); // equivalent to void f() noexcept;
void f() {} // warning C5043
void g() throw(); // warning C5040

struct A {
    virtual void f() throw();
};

struct B : A {
    virtual void f() { } // error C2694
};
```

여전히 **/std:c++17**을 사용 중일 때 오류를 제거하려면 명령줄에 **/Zc:noexceptTypes-** 스위치를 추가하거나 다음 예제에 나와 있는 것처럼 `noexcept`를 사용하도록 코드를 업데이트하세요.

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A {
    virtual void f() noexcept;
};

struct B : A {
    virtual void f() noexcept { }
};
```

### <a name="inline-variables"></a>인라인 변수

constexpr 정적 데이터 멤버는 이제 암시적으로 인라인이므로 이제 클래스 내 선언으로 정의됩니다. constexpr 정적 데이터 멤버에 대한 확장 정의는 이제 중복되며 사용되지 않습니다. Visual Studio 2017 버전 15.5에서 **/std:c++17** 스위치가 적용되면 다음 코드는 이제 경고 C5041 *'크기': constexpr 정적 데이터 멤버에 대한 확장 정의는 C++17에서 필요하지 않거나 사용되지 않습니다*를 유발합니다.

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-declspec-warning-c4768-now-on-by-default"></a>extern "C" __declspec(...) 경고 C4768이 이제 기본적으로 켜짐

이 경고는 Visual Studio 2017 15.3 버전에서 추가되었지만 기본적으로 꺼져 있었습니다. Visual Studio 2017 버전 15.5에서 이는 기본적으로 켜져 있습니다. 자세한 내용은 [declspec 특성에 대한 새로운 경고](#declspec)를 참조하세요.

### <a name="defaulted-functions-and-declspecnothrow"></a>기본값으로 설정된 함수 및 __declspec(nothrow)

컴파일러는 이전에 해당 기본/멤버 함수가 예외를 허용할 경우 기본값으로 설정된 함수를 `__declspec(nothrow)`로 선언하도록 허용했습니다. 이 동작은 C++ 표준과 반대되며 런타임 시 정의되지 않은 동작을 유발할 수 있습니다. 이 표준에서는 예외 사양 불일치가 있을 경우 이러한 함수를 삭제된 것으로 정의하도록 요구합니다.  **/std:c++17** 하에서 다음 모드는 C2280 *삭제된 함수를 참조하려고 합니다. 명시적 예외 사양이 암시적 선언의 명시적 예외 사양과 호환되지 않으므로 함수가 암시적으로 삭제되었습니다.* 를 유발합니다.

```cpp
struct A {
    A& operator=(const A& other) { // No exception specification; this function may throw.
        ...
    }
};

struct B : public A {
    __declspec(nothrow) B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1; // error C2280
}
```

이 코드를 수정하려면 기본값으로 설정된 함수에서 __declspec(nothrow)를 제거하거나 `= default`를 제거하고 필요한 모든 예외 처리와 함께 함수에 대한 정의를 제공합니다.

```cpp
struct A {
    A& operator=(const A& other) {
        // ...
    }
};

struct B : public A {
    B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1;
}
```

### <a name="noexcept-and-partial-specializations"></a>noexcept 및 부분 특수화

형식 시스템에서 noexcept를 사용하면 pointers-to-noexcept-functions에 대한 부분 특수화 누락으로 인해 일치하는 특정 "호출 가능" 형식이 컴파일하지 못하거나 기본 템플릿을 선택하지 못할 수 있습니다.

이러한 경우 noexcept 함수 포인터 및 멤버 함수에 대한 noexcept 포인터를 처리할 추가 부분 특수화를 추가해야 합니다. 이러한 오버로드는 **/std:c++17** 모드에서만 적합합니다. C++14와 호환성을 유지해야 하고, 다른 사람이 사용할 코드를 작성 중인 경우 `#ifdef` 지시문 내에서 이러한 새 오버로드를 보호해야 합니다. 자체 포함 모듈에서 작업 중인 경우 `#ifdef` 가드를 사용하는 대신 **/Zc:noexceptTypes-** 스위치를 사용하여 컴파일할 수 있습니다.

다음 코드는 **/std:c++14** 하에서 컴파일하지만 "오류 C2027:정의되지 않은 형식 'A\<T>'"와 함께 **/std:c++17** 하에서 실패합니다.

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // C2027
}
```

다음 코드는 컴파일러가 새로운 부분 특수화 `A<void (*)() noexcept>`를 선택하기 때문에 **/std:c++17** 하에서 성공합니다.

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <>
struct A<void(*)() noexcept>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // OK
}
```

## <a name="update_157"></a> Visual Studio 2017 15.7 버전의 버그 수정 및 기타 동작 변경

### <a name="c17-default-argument-in-the-primary-class-template"></a>C++17 기본 클래스 템플릿의 기본 인수

이 동작 변경은 [클래스 템플릿 - P0091R3에 대한 템플릿 인수 추론](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)에 대한 사전 조건이며 Visual Studio 2017 버전 15.7의 최신 미리 보기에서 완전히 지원될 예정입니다.

이전에 컴파일러는 기본 클래스 템플릿의 기본 인수를 무시했습니다.

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int = 0) {} // Re-definition necessary
```

**/std:c++17** 모드의 Visual Studio 2017 버전 15.7에서 기본 인수는 무시되지 않습니다.

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int) {} // Default argument is used
```

### <a name="dependent-name-resolution"></a>종속 이름 확인

이 동작 변경은 [클래스 템플릿 - P0091R3에 대한 템플릿 인수 추론](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)에 대한 사전 조건이며 Visual Studio 2017 버전 15.7의 최신 미리 보기에서 완전히 지원될 예정입니다.

다음 예제에서 Visual Studio 15.6 이하 버전의 컴파일러는 기본 클래스 템플릿에서 `D::type`을 `B<T>::type`으로 확인합니다.

```cpp
template<typename T>
struct B {
    using type = T;
};

template<typename T>
struct D : B<T*> {
    using type = B<T*>::type;
};
```

**/std:c++17** 모드의 Visual Studio 2017 버전 15.7은 D의 `using` 문에 `typename` 키워드가 필요합니다. `typename`이 없으면 컴파일러가 경고 C4346: *'B<T\*>::type': 종속 이름은 type이 아님* 및 오류 C2061: *구문 오류: 식별자 'type'* 을 발생시킵니다.

```cpp
template<typename T>
struct B {
    using type = T;
};

template<typename T>
struct D : B<T*> {
    using type = typename B<T*>::type;
};
```

### <a name="c17-nodiscard-attribute---warning-level-increase"></a>C++17 [[nodiscard]] 특성 - 경고 수준 증가

Visual Studio 2017 버전 15.7의 **/std:c++17** 모드에서 C4834의 경고 레벨("'nodiscard' 특성이 포함된 함수의 반환 값을 버리는 중")은 W3에서 W1로 증가되었습니다. `void`로 캐스트하거나 **/wd:4834**를 컴파일러로 전달하여 경고를 해제할 수 있습니다.

```cpp
[[nodiscard]] int f() { return 0; }

int main() {
    f(); // warning: discarding return value
         // of function with 'nodiscard'
}
```

### <a name="variadic-template-constructor-base-class-initialization-list"></a>Variadic 템플릿 생성자 기본 클래스 초기화 목록

Visual Studio의 이전 버전에서는 템플릿 인수가 누락된 variadic 템플릿 생성자 기본 클래스 초기화 목록이 오류 없이 잘못 허용되었습니다. Visual Studio 2017 버전 15.7에서는 컴파일러 오류가 발생합니다.

Visual Studio 2017 버전 15.7의 다음 코드 예제에서는 *오류 C2614: D\<int>: 잘못된 멤버 초기화: 'B'는 기본 또는 멤버가 아님*이 발생합니다.

```cpp
template<typename T>
struct B {};

template<typename T>
struct D : B<T>
{

    template<typename ...C>
    D() : B() {} // C2614. Missing template arguments to B.
};

D<int> d;
```

오류를 수정하려면 B() 식을 B\<T>()로 변경하세요.

### <a name="constexpr-aggregate-initialization"></a>constexpr 집계 초기화

이전 버전의 C++ 컴파일러가 constexpr 집계 초기화를 잘못 처리했습니다. aggregate-init-list에 요소가 너무 많은 잘못된 코드를 허용했으며 잘못된 codegen을 생성했습니다. 다음 코드는 이러한 코드의 예제입니다.

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = {
        { 1, 2 },
        { 3, 4 }
    };
    return 0;
}
```

Visual Studio 2017 버전 15.7 업데이트 3 이상에서는 이전 예제에서 현재 ‘C2078 이니셜라이저가 너무 많음’이 발생합니다. 다음 예제는 코드를 수정하는 방법을 보여 줍니다. 중첩된 brace-init-lists를 사용하여 `std::array`를 초기화할 때 내부 배열에 자체 braced-list를 제공합니다.

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = {{ // note double braces
        { 1, 2 },
        { 3, 4 }
    }}; // note double braces
    return 0;
}
```

## <a name="update_158"></a> Visual Studio 2017 15.8 버전의 버그 수정 및 동작 변경

Visual Studio 2017 버전 15.8의 모든 컴파일러 변경 사항은 버그 수정 및 동작 변경의 범주에 속하며, 아래에 나열되어 있습니다.

### <a name="typename-on-unqualified-identifiers"></a>정규화되지 않은 식별자의 형식 이름

[/permissive-](../../build/reference/permissive-standards-conformance.md) 모드에서는 별칭 템플릿 정의의 정규화되지 않은 식별자에 있는 의사 `typename` 키워드가 컴파일러에서 더 이상 허용되지 않습니다. 이제 C7511 *'T': 'typename' 키워드 뒤에는 정규화된 이름이 와야 합니다* 코드가 생성됩니다.

```cpp
template <typename T>
using  X = typename T;
```

이 오류를 해결하려면 두 번째 줄을 `using  X = T;`로 변경하기만 하면 됩니다.

### <a name="declspec-on-right-side-of-alias-template-definitions"></a>별칭 템플릿 정의의 오른쪽에 __declspec()

[__declspec](../../cpp/declspec.md)은 별칭 템플릿 정의의 오른쪽에 더 이상 허용되지 않습니다. 이것은 이전에 컴파일러에서 허용되었지만 완전히 무시되었으며 별칭이 사용될 때 사용 중단 경고가 발생하지 않습니다.

표준 C++ 특성 [\[\[사용되지 않음\]\]](../../cpp/attributes.md)이 대신 사용될 수 있으며 Visual Studio 2017 버전 15.6 기준으로 적용됩니다. 이제 C2760 *구문 오류: '__declspec'은 예기치 않은 토큰입니다. 필요한 토큰은 'type specifier'입니다.* 코드가 생성됩니다.

```cpp
template <typename T>
using X = __declspec(deprecated("msg")) T;
```

오류를 수정하려면 코드를 다음으로 변경합니다('=' 별칭 정의 앞에 속성 배치).

```cpp
template <typename T>
using  X [[deprecated("msg")]] = T;
```

### <a name="two-phase-name-lookup-diagnostics"></a>2단계 이름 조회 진단

2단계 이름 조회를 위해서는 템플릿 본문에 사용된 종속되지 않은 이름이 정의 시점에 템플릿에 표시될 수 있어야 합니다. 이전에는 Microsoft C++ 컴파일러가 인스턴스화 시점까지 찾을 수 없는 이름을 조회 안 함으로 남겨 두었습니다. 이제, 종속되지 않은 이름을 템플릿 본문에 바인드해야 합니다.

이것을 나타낼 수 있는 한 가지 방법은 종속 기본 클래스를 조회하는 것입니다. 이전에는 모든 형식이 해석될 때 인스턴스화 시간 동안 이름이 조회되기 때문에 컴파일러가 종속 기본 클래스에 정의된 이름의 사용을 허용했습니다. 이제 해당 코드는 오류로 처리됩니다. 이러한 경우 기본 클래스 형식으로 한정하거나 종속으로 지정하여 인스턴스화 시점에 변수가 조회되도록 할 수 있습니다(예: `this->` 포인터 추가).

**/permissive-** 모드에서는 다음 C3861: *'base_value': 식별자를 찾을 수 없습니다.* 코드가 발생합니다.

```cpp
template <class T>
struct Base {
    int base_value = 42;
};

template <class T>
struct S : Base<T> {
    int f() {
        return base_value;
    }
};
```

이 오류를 해결하려면 `return` 문을 `return this->base_value;`로 변경합니다.

**참고:** Boost python 라이브러리에는 오랫동안 [unwind_type.hpp](https://github.com/boostorg/python/blame/develop/include/boost/python/detail/unwind_type.hpp)의 템플릿 정방향 선언에 대한 MSVC 관련 해결 방법이 있었습니다. Visual Studio 2017 버전 15.8(_MSC_VER=1915)부터 [/permissive-](../../build/reference/permissive-standards-conformance.md) 모드에서 MSVC 컴파일러가 ADL(인수 종속성 이름 조회)을 올바로 수행하고 다른 컴파일러와 일치하므로 이 해결 방법 보호가 필요 없어졌습니다. ‘C3861: ‘unwind_type’: 식별자를 찾을 수 없습니다.’ 오류를 방지하려면 Boostorg 리포지토리에서 [PR 229](https://github.com/boostorg/python/pull/229)를 참조하여 헤더 파일을 업데이트하세요. [vcpkg](../../build/vcpkg.md) Boost 패키지를 이미 패치했으므로 vcpkg에서 Boost 소스를 가져오거나 업그레이드한 경우 패치를 별도로 적용할 필요가 없습니다.

### <a name="forward-declarations-and-definitions-in-namespace-std"></a>std 네임스페이스에서 정방향 선언 및 정의

C++ 표준에서는 사용자가 `std` 네임스페이스에 정방향 선언 또는 정의를 추가할 수 없습니다. `std` 네임스페이스 또는 std 네임스페이스 내의 네임스페이스에 선언 또는 정의를 추가하면 정의되지 않은 동작이 발생합니다.

향후 Microsoft는 일부 STL 형식이 정의된 위치를 변경할 예정입니다. 이 경우 `std` 네임스페이스에 정방향 선언을 추가하는 기존 코드가 중단됩니다. 새로운 경고, C4643을 통해 이러한 소스 문제를 파악할 수 있습니다. 이 경고는 **/default** 모드에서 사용하도록 설정되며 기본적으로 해제되어 있습니다. 이것은 **/Wall** 또는 **/WX**로 컴파일되는 프로그램에 영향을 줍니다.

이제 다음 코드는 C4643: *C++ 표준에서는 네임스페이스 std에서 'vector' 정방향 선언이 허용되지 않습니다*를 생성합니다.

```cpp
namespace std {
    template<typename T> class vector;
}
```

이 오류를 해결하려면 정방향 선언보다는 **include** 지시문을 사용합니다.

```cpp
#include <vector>
```

### <a name="constructors-that-delegate-to-themselves"></a>자신을 위임하는 생성자

C++ 표준은 위임하는 생성자가 자신을 위임할 때 컴파일러가 진단을 내보내야 한다고 제안합니다. [/std:c++17](../../build/reference/std-specify-language-standard-version.md) 및 [/std:c++latest](../../build/reference/std-specify-language-standard-version.md) 모드의 Microsoft C++ 컴파일러는 이제 C7535: *'X::X': 위임하는 생성자는 자신을 호출합니다*를 생성합니다.

이 오류가 없으면 다음 프로그램이 컴파일되지만 무한 루프가 생성됩니다.

```cpp
class X {
public:
    X(int, int);
    X(int v) : X(v){}
};
```

무한 루프를 방지하려면 다른 생성자에 위임합니다.

```cpp
class X {
public:

    X(int, int);
    X(int v) : X(v, 0) {}
};
```

### <a name="offsetof-with-constant-expressions"></a>상수 식이 있는 offsetof

지금까지 [offsetof](../../c-runtime-library/reference/offsetof-macro.md)는 [reinterpret_cast](../../cpp/reinterpret-cast-operator.md)가 필요한 매크로를 사용하여 구현되었습니다. 이는 상수 식을 필요로 하는 컨텍스트에서는 올바르지 않지만 Microsoft C++ 컴파일러는 일반적으로 허용합니다. STL의 일부로 제공되는 offsetof 매크로는 컴파일러 내장 함수(**__builtin_offsetof**)를 올바르게 사용하지만 많은 사람은 매크로 트릭을 사용하여 자신의 **offsetof**을 정의합니다.

Visual Studio 2017 버전 15.8에서 컴파일러는 reinterpret_casts가 기본 모드로 표시될 수 있는 영역을 제한하여 코드가 표준 C++ 동작을 준수하도록 합니다. [/permissive-](../../build/reference/permissive-standards-conformance.md) 아래에서는 제약 조건이 더욱 엄격합니다. 상수 식을 요구하는 위치에서 offsetof 결과를 사용하면 C4644 *상수 식에 매크로 기반 offsetof 패턴을 사용하는 것은 표준이 아닙니다. 대신 C++ 표준 라이브러리에 정의된 offsetof를 사용하십시오.* 또는 C2975 *템플릿 인수가 잘못되었습니다. 컴파일 시간 상수 식이 필요합니다.* 라는 경고를 생성하는 코드가 발생할 수 있습니다.

**/default** 및 **/std:c++17** 모드에서는 C4644가, **/permissive-** 모드에서는 C2975 코드가 발생합니다.

```cpp
struct Data {
    int x;
};

// Common pattern of user-defined offsetof
#define MY_OFFSET(T, m) (unsigned long long)(&(((T*)nullptr)->m))

int main()

{
    switch (0) {
    case MY_OFFSET(Data, x): return 0;
    default: return 1;
    }
}
```

이 오류를 해결하려면 \<cstddef>:를 통해 정의된 대로 **offsetof**를 사용하세요.

```cpp
#include <cstddef>

struct Data {
    int x;
};

int main()
{
    switch (0) {
    case offsetof(Data, x): return 0;
    default: return 1;
    }
}
```

### <a name="cv-qualifiers-on-base-classes-subject-to-pack-expansion"></a>팩 확장의 대상이 되는 기본 클래스의 CV 한정자

이전 버전의 Microsoft C++ 컴파일러는 기본 클래스가 팩 확장의 대상이 될 경우 기본 클래스에 cv 한정자가 있음을 감지하지 못했습니다.

Visual Studio 2017 버전 15.8의 **/permissive-** 모드에서는 C3770 *'const S': 유효한 기본 클래스가 아닙니다.* 코드가 발생합니다.

```cpp
template<typename... T>
class X : public T... { };

class S { };

int main()
{
    X<const S> x;
}
```

### <a name="template-keyword-and-nested-name-specifiers"></a>템플릿 키워드 및 중첩된 이름 지정자

**/permissive-** 모드에서 컴파일러는 종속된 중첩된 이름 지정자 뒤에 오는 경우 `template` 키워드가 템플릿 이름 앞에 오도록 요구합니다.

**/permissive-** 모드에서 다음 코드는 C7510: *'foo': 종속 템플릿 이름은 'template'과 함께 사용해야 합니다. 참고: 컴파일 중인 클래스 템플릿 인스턴스화 'X<T>'에 대한 참조를 확인하십시오.* 를 생성합니다.

```cpp
template<typename T> struct Base
{
    template<class U> void foo() {}
};

template<typename T>
struct X : Base<T>
{
    void foo()
    {
        Base<T>::foo<int>();
    }
};
```

이 오류를 해결하려면 다음 예제에서 표시된 대로 `template` 키워드를 `Base<T>::foo<int>();` 문에 추가합니다.

```cpp
template<typename T> struct Base
{
    template<class U> void foo() {}
};

template<typename T>
struct X : Base<T>
{
    void foo()
    {
        // Add template keyword here:
        Base<T>::template foo<int>();
    }
};
```
## <a name="update_159"></a> Visual Studio 2017 15.9 버전의 버그 수정 및 동작 변경

### <a name="identifiers-in-member-alias-templates"></a>멤버 별칭 템플릿의 식별자
멤버 별칭 템플릿 정의에서 사용된 식별자를 사용하기 전에 선언해야 합니다. 

이전 버전의 컴파일러에서 다음 코드가 허용되었습니다.

```cpp
template <typename... Ts>
struct A
{
  public:
    template <typename U>
    using from_template_t = decltype(from_template(A<U>{}));

  private:
    template <template <typename...> typename Type, typename... Args>
    static constexpr A<Args...> from_template(A<Type<Args...>>);
};

A<>::from_template_t<A<int>> a;
```

Visual Studio 2017 버전 15.9의 **/permissive-** 모드에서 컴파일러는 C3861: *'from_template': 식별자를 찾을 수 없음*을 발생시킵니다.

오류를 해결하려면 `from_template_t` 전에 `from_template`를 선언합니다.

### <a name="modules-changes"></a>모듈 변경

Visual Studio 2017 버전 15.9에서 모듈에 대한 명령줄 옵션이 모듈 생성과 모듈 소비 쪽 간에 일치하지 않을 때마다 컴파일러는 C5050를 발생시킵니다. 다음 예제에서는 두 가지 문제가 있습니다.

- 소비 쪽(main.cpp)에서 **/EHsc** 옵션이 지정되지 않습니다.
- C++ 버전은 생성 쪽에서 **/std:c++17**이고, 소비 쪽에서 **/std:c++14**입니다. 

```cmd
cl /EHsc /std:c++17 m.ixx /experimental:module
cl /experimental:module /module:reference m.ifc main.cpp /std:c++14
```

컴파일러는 다음 두 경우 모두에 대해 C5050을 생성합니다. *경고 C5050: 'm' 모듈을 가져오는 동안 호환되지 않는 환경: C++ 버전이 일치하지 않습니다.  현재 "201402" 모듈 버전 "201703"*

또한 .ifc 파일이 조작될 때마다 컴파일러는 C7536을 발생시킵니다. 모듈 인터페이스의 헤더에는 아래 내용의 SHA2 해시가 포함됩니다. 가져오기에서 .ifc 파일이 동일한 방식으로 해시된 다음, 헤더에서 제공된 해시에 대해 확인됩니다. 이러한 항목이 일치하지 않는 경우 오류 C7536이 발생합니다. *ifc가 무결성 검사에 실패했습니다.  예상된 SHA2: '66d5c8154df0c71d4cab7665bab4a125c7ce5cb9a401a4d8b461b706ddd771c6'*.

### <a name="partial-ordering-involving-aliases-and-non-deduced-contexts"></a>별칭 및 추론되지 않은 컨텍스트와 관련된 부분 순서

추론되지 않은 컨텍스트에서 별칭을 포함하는 부분 순서 지정 규칙의 구현에 차이가 있습니다. 다음 예제에서 Clang이 코드를 허용하는 반면 **/permissive-** 모드의 GCC 및 Microsoft C++ 컴파일러는 오류를 발생시킵니다. 

```cpp
#include <utility>
using size_t = std::size_t;

template <typename T>
struct A {};
template <size_t, size_t>
struct AlignedBuffer {};
template <size_t len>
using AlignedStorage = AlignedBuffer<len, 4>;

template <class T, class Alloc>
int f(Alloc &alloc, const AlignedStorage<T::size> &buffer)
{
    return 1;
}

template <class T, class Alloc>
int f(A<Alloc> &alloc, const AlignedStorage<T::size> &buffer)
{
    return 2;
}

struct Alloc
{
    static constexpr size_t size = 10;
};

int main()
{
    A<void> a;
    AlignedStorage<Alloc::size> buf;
    if (f<Alloc>(a, buf) != 2)
    {
        return 1;
    }

    return 0;
}
```

이전 예제는 C2668을 발생시킵니다.

```Output
partial_alias.cpp(32): error C2668: 'f': ambiguous call to overloaded function
partial_alias.cpp(18): note: could be 'int f<Alloc,void>(A<void> &,const AlignedBuffer<10,4> &)'
partial_alias.cpp(12): note: or       'int f<Alloc,A<void>>(Alloc &,const AlignedBuffer<10,4> &)'
        with
        [
            Alloc=A<void>
        ]
partial_alias.cpp(32): note: while trying to match the argument list '(A<void>, AlignedBuffer<10,4>)'
```

구현의 차이는 표준 단어 지정에서 회귀로 인한 것입니다. 여기서 중요 2235 문제에 대한 해결 방법이 이러한 오버로드를 정렬할 수 있는 일부 텍스트를 제거했습니다. 현재 C++ 표준은 이러한 함수를 부분적으로 정렬하는 메커니즘을 제공하지 않습니다. 따라서 모호하다고 여겨집니다.

대안으로 이 문제를 해결하려면 부분 순서 지정을 사용하지 않고 대신 SFINAE를 사용하여 특정 오버로드를 제거하는 것이 좋습니다. 다음 예제에서 `Alloc`가 `A`의 특수화인 경우 `IsA` 도우미 클래스를 사용하여 첫 번째 오버로드를 제거합니다.

```cpp
#include <utility>
using size_t = std::size_t;

template <typename T>
struct A {};
template <size_t, size_t>
struct AlignedBuffer {};
template <size_t len>
using AlignedStorage = AlignedBuffer<len, 4>;

template <typename T> struct IsA : std::false_type {};
template <typename T> struct IsA<A<T>> : std::true_type {};

template <class T, class Alloc, typename = std::enable_if_t<!IsA<Alloc>::value>>
int f(Alloc &alloc, const AlignedStorage<T::size> &buffer)
{
    return 1;
}

template <class T, class Alloc>
int f(A<Alloc> &alloc, const AlignedStorage<T::size> &buffer)
{
    return 2;
}

struct Alloc
{
    static constexpr size_t size = 10;
};

int main()
{
    A<void> a;
    AlignedStorage<Alloc::size> buf;
    if (f<Alloc>(a, buf) != 2)
    {
        return 1;
    }

    return 0;
}
```

### <a name="illegal-expressions-and-non-literal-types-in-templated-function-definitions"></a>템플릿 지정된 함수 정의의 잘못된 식 및 비 리터럴 형식

잘못된 식 및 비 리터럴 형식은 이제 명시적으로 특수화된 템플릿 지정된 함수의 정의에서 바르게 진단됩니다. 이전에 이러한 오류는 함수 정의에 대해 내보내지 않았습니다. 그러나 잘못된 식 또는 비 리터럴 형식은 상수 식의 일부로 평가되는 경우에 진단됩니다. 

이전 버전의 Visual Studio에서 다음 코드는 경고 없이 컴파일됩니다.

```cpp
void g();
 
template<typename T>
struct S 
{
    constexpr void f();
};
  
template<>
constexpr void S<int>::f() 
{
    g(); // C3615 in 15.9
}
```

Visual Studio 2017 버전 15.9에서 코드는 다음 오류를 발생시킵니다. *오류 C3615: constexpr function 'S<int>::f'는 상수 식입니다. 참고: 오류는 정의되지 않은 함수 또는 하나의 선언되지 않은 'constexpr' 호출로 인해 발생했습니다. 참고: 'g'의 사용량을 확인합니다*. 이 오류를 방지하려면 함수 f()의 명시적 인스턴스화에서 `constexpr` 한정자를 제거합니다. 

## <a name="see-also"></a>참고 항목

[Visual C++ 언어 규칙](../visual-cpp-language-conformance.md)
