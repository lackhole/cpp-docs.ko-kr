---
title: C++ 규칙 향상
ms.date: 05/16/2019
description: Visual Studio 2019의 Microsoft C++는 C++20 언어 표준을 완전하게 준수하는 방향으로 진행 중입니다.
ms.technology: cpp-language
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 02b778f10ad94342c922a4e79a856cc2a7d53076
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66451210"
---
# <a name="c-conformance-improvements-in-visual-studio-2019-rtw-and-version-161improvements161"></a>Visual Studio 2019 RTW 및 버전 [16.1](#improvements_161)의 C++ 규칙 향상

## <a name="improvements-in-visual-studio-2019-rtw"></a>Visual Studio 2019 RTW의 개선 사항

Visual Studio 2019 RTW에는 Microsoft C++ 컴파일러(MSVC)의 다음과 같은 규칙 개선, 버그 수정 및 동작 변경 내용이 포함되어 있습니다.

**참고:** C++20 기능은 컴파일러와 IntelliSense 모두에 대해 C++20 구현이 완료될 때까지 `/std:c++latest` 모드에서 사용할 수 있습니다. 이때 `/std:c++20` 컴파일러 모드가 도입됩니다.

### <a name="improved-modules-support-for-templates-and-error-detection"></a>템플릿 및 오류 검색에 대한 향상된 모듈 지원

모듈은 이제 공식적으로 C++20 표준에 속합니다. Visual Studio 2017 버전 15.9에는 향상된 지원이 추가되었습니다. 자세한 내용은 [MSVC 2017 버전 15.9를 사용하여 C++ 모듈의 템플릿 지원 및 오류 검색 향상](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/)을 참조하세요.

### <a name="modified-specification-of-aggregate-type"></a>집계 유형의 수정된 사양

집계 유형의 사양이 C++20에서 변경되었습니다([사용자가 선언한 생성자로 집계 금지](https://wg21.link/p1008r1) 참조). Visual Studio 2019의 `/std:c++latest`에서 사용자가 선언한 생성자가 있는 클래스(예: `= default` 또는 `= delete`로 선언된 생성자 포함)는 집계가 아닙니다. 이전에는 사용자가 제공한 생성자만 클래스가 집계되지 못하도록 합니다. 이 변경으로 인해 이러한 형식을 초기화할 수 있는 방법이 제한됩니다.

다음 코드는 Visual Studio 2017에서 오류 없이 컴파일되지만 `/std:c++latest` 아래의 Visual Studio 2019에서는 C2280 및 C2440 오류를 발생시킵니다.

```cpp
struct A
{
    A() = delete; // user-declared ctor
};

struct B
{
    B() = default; // user-declared ctor
    int i = 0;
};

A a{}; // ill-formed in C++20, previously well-formed
B b = { 1 }; // ill-formed in C++20, previously well-formed
```

### <a name="partial-support-for-operator-"></a>연산자에 대한 부분 지원 <=>

[P0515R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0515r3.pdf) C++20에서는 "우주선 연산자"라고도 하는 `<=>` 3방향 비교 연산자를 소개합니다. `/std:c++latest` 모드의 Visual Studio 2019는 현재 허용되지 않는 구문 오류를 발생시켜 연산자에 대한 부분 지원을 도입합니다. 예를 들어 다음 코드는 Visual Studio 2017에서 오류 없이 컴파일되지만 `/std:c++latest` 아래의 Visual Studio 2019에서는 여러 오류가 발생합니다.

```cpp
struct S
{
       bool operator<=(const S&) const { return true; }
};

template <bool (S::*)(const S&) const>
struct U { };
int main(int argc, char** argv)
{
       U<&S::operator<=> u; // In Visual Studio 2019 raises C2039, 2065, 2146.
}
```

오류를 방지하려면 최종 괄호 앞에 잘못된 줄의 공백(`U<&S::operator<= > u;`)을 삽입합니다.

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>일치하지 않는 cv 한정자가 있는 유형에 대한 참조

MSVC는 이전에 최상위 수준 아래에 일치하지 않는 cv 한정자가 있는 형식의 참조를 직접 바인딩할 수 있었습니다. 이는 참조에 의해 언급된 것으로 추정되는 const 데이터의 수정을 허용할 수 있으며, 컴파일러는 이제 표준에서 요구하는 대로 임시로 만듭니다. Visual Studio 2017에서 다음 코드는 경고 없이 컴파일됩니다. Visual Studio 2019에서 컴파일러는 *경고 C4172: \<func:#1 "?PData@X@@QBEABQBXXZ"> 로컬 변수 또는 임시*  주소를 반환합니다.

```cpp
struct X
{
    const void* const& PData() const
    {
        return _pv;
    }

    void* _pv;
};

int main()
{
    X x;
    auto p = x.PData(); // C4172
}
```
### <a name="reinterpretcast-from-an-overloaded-function"></a>`reinterpret_cast` 오버로드된 함수에서

`reinterpret_cast`에 대한 인수는 오버로드된 함수의 주소가 허용되는 컨텍스트 중 하나가 아닙니다. 다음 코드는 Visual Studio 2017에서 오류 없이 컴파일되지만 Visual Studio 2019에서는 *C2440: '오버로드된 함수'에서 'fp'로 변환될 수 없음*을 발생시킵니다.

```cpp
int f(int) { return 1; }
int f(float) { return .1f; }
using fp = int(*)(int);

int main()
{
    fp r = reinterpret_cast<fp>(&f);
}
```

오류를 방지하려면 이 시나리오에 허용된 캐스트를 사용합니다.

```cpp
int f(int);
int f(float);
using fp = int(*)(int);

int main()
{
    fp r = static_cast<fp>(&f); // or just &f;
}
```

### <a name="lambda-closures"></a>람다 클로저

C++14에서 람다 클로저 형식은 리터럴이 아닙니다. 이 규칙의 기본 결과는 람다가 `constexpr` 변수에 할당되지 않을 수 있다는 것입니다. 다음 코드는 Visual Studio 2017에서 오류 없이 컴파일되지만 Visual Studio 2019에서는 *C2127: 'l': 비상수 식으로 'constexpr' 엔터티의 불법 초기화*를 발생시킵니다.

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

오류를 방지하려면 `constexpr` 한정자를 제거하거나 규칙 모드를 `/std:c++17`로 변경합니다.

### <a name="stdcreatedirectory-failure-codes"></a>std::create_directory 실패 코드

C++20에서 [P1164](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1164r1.pdf)를 무조건으로 구현했습니다. 이렇게 하면 대상이 이미 실패한 디렉터리인지 여부를 확인하기 위해 `std::create_directory`가 변경됩니다. 이전에는 모든 ERROR_ALREADY_EXISTS 형식 오류가 success-but-directory-not-created 코드로 변경되었습니다.

### <a name="operatorstdostream-nullptrt"></a>연산자<<(std::ostream, nullptr_t)

[LWG 2221](https://cplusplus.github.io/LWG/issue2221)당 스크림에 nullptrs를 쓰기 위해 `operator<<(std::ostream, nullptr_t)`을 추가했습니다. 

### <a name="additional-parallel-algorithms"></a>추가 병렬 알고리즘

`is_sorted`, `is_sorted_until`, `is_partitioned`, `set_difference`, `set_intersection`, `is_heap` 및 `is_heap_until`의 새 병렬 버전.

### <a name="atomic-initialization"></a>원자성 초기화

[P0883 "원자성 초기화 수정"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0883r1.pdf)은 `std::atomic`을 변경하여 포함된 T를 기본 초기화하는 대신 값을 초기화합니다. 이 수정 내용은 Microsoft Standard Library에서 Clang/LLVM을 사용할 때 활성화됩니다. 현재 Microsoft C++ 컴파일러에서 constexpr 처리 중인 버그에 대한 해결 방법으로 사용할 수 없습니다.

### <a name="removecvref-and-removecvreft"></a>remove_cvref 및 remove_cvref_t

[P0550](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf)에서 `remove_cvref` 및 `remove_cvref_t` 형식 특성을 구현했습니다. 이러한 특성은 함수 및 배열이 손상되지 않는 유형에서 포인터(`std::decay` 및 `std::decay_t`와는 달리)로 참조 및 cv 한정자를 제거합니다.

### <a name="feature-test-macros"></a>기능 테스트 매크로

[P0941R2 - feature-test 매크로](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html)는 `__has_cpp_attribute`에 대한 지원으로 완료되었습니다. Feature-test 매크로는 모든 표준 모드에서 지원됩니다.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>사용자 선언 생성자를 사용하여 집계 금지

[C++20 P1008R1 - 사용자 선언 생성자를 사용하여 집계 금지](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf)가 완료되었습니다.

## <a name="improvements_161"></a> Visual Studio 2019 버전 16.1의 개선 사항

### <a name="char8t"></a>char8_t

[P0482r6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html). C++20은 UTF-8 코드 단위를 나타내는 데 사용되는 새로운 문자 형식을 추가합니다. C++20의 u8 문자열 리터럴에는 이전에 있었던 `const char[N]` 대신 `const char8_t[N]` 유형이 있습니다. [N2231](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n2231.htm)의 C 표준에 대해 유사한 변경이 제안되었습니다. char8_t 이전 버전과의 호환성 수정에 대한 제안은 [P1423r0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1423r0.html)에서 제공됩니다. Microsoft C++ 컴파일러는 **/Zc:char8_t** 컴파일러 옵션을 지정할 때 Visual Studio 2019 버전 16.1에서 char8_t에 대한 지원을 추가합니다. 향후 **/Zc:char8_t-** 를 통해 C++17 동작으로 되돌릴 수 있는 [/std:c++latest](../../build/reference/std-specify-language-standard-version.md)로 지원될 예정입니다. IntelliSense를 지원하는 EDG 컴파일러는 아직 이를 지원하지 않으므로 실제 컴파일에 영향을 주지 않는 잘못된 IntelliSense 전용 오류가 표시됩니다.

#### <a name="example"></a>예제

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtypeidentity-metafunction-and-stdidentity-function-object"></a>std::type_identity 메타 함수 및 std:: identity 함수 개체

[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf). 사용되지 않는 `std::identity` 클래스 템플릿 확장이 제거되었으며 C++20 `std::type_identity` 메타 함수 및 `std::identity` 함수 개체로 대체되었습니다. 둘 다 [/std:c++latest](../../build/reference/std-specify-language-standard-version.md)에서만 사용할 수 있습니다. 

다음 예제에서는 Visual Studio 2017에서 `std::identity`(\<type_traits>에서 정의됨)에 대한 사용 중단 경고 C4996을 생성합니다. 

```cpp
#include <type_traits>

using T = std::identity<int>::type;
T x, y = std::identity<T>{}(x);
int i = 42;
long j = std::identity<long>{}(i);
```

다음 예제에서는 새 `std::identity`(\<functional>에서 정의됨)를 `std::type_identity`와 함께 사용하는 방법을 보여줍니다.

```cpp
#include <type_traits>
#include <functional>

using T = std::type_identity<int>::type;
T x, y = std::identity{}(x);
int i = 42;
long j = static_cast<long>(i);
```

### <a name="syntax-checks-for-generic-lambdas"></a>일반 람다에 대한 구문 검사

새 람다 프로세서는 [/std:c++latest](../../build/reference/std-specify-language-standard-version.md) 또는 **/experimental:newLambdaProcessor**를 사용하는 다른 언어 모드 아래의 일반 람다에서 몇 가지 규칙 모드 구문 검사를 활성화합니다. 

Visual Studio 2017에서 이 코드는 경고 없이 컴파일되지만 Visual Studio 2019에서는 *C2760 구문 오류: 예기치 않은 토큰 '\<id-expr>', expected 'id-expression'* 오류가 생성됩니다.

```cpp
void f() {
    auto a = [](auto arg) {
        decltype(arg)::Type t;
    };
}
```

다음 예제는 올바른 구문을 보여주고, 이제 컴파일러에 의해 적용됩니다.

```cpp
void f() {
    auto a = [](auto arg) {
        typename decltype(arg)::Type t;
    };
}
```

### <a name="argument-dependent-lookup-for-function-calls"></a>함수 호출에 대한 인수 종속 조회

[P0846R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0846r0.html)(C++20) 명시적 템플릿 인수를 사용하는 함수 호출 식에 대한 인수 종속 조회를 통해 함수 템플릿을 찾는 기능이 향상되었습니다. **/std:c++latest**가 필요합니다.

### <a name="designated-initialization"></a>지정된 초기화

[P0329R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf)(C++20) 지정된 초기화를 통해 `Type t { .member = expr }` 구문을 사용하여 지정된 멤버를 집계 초기화에서 선택할 수 있습니다. **/std:c++latest**가 필요합니다.

### <a name="new-and-updated-standard-library-functions-c20"></a>신규 및 업데이트된 표준 라이브러리 함수(C++20)

- `basic_string` 및 `basic_string_view`에 대한 `starts_with()` 및 `ends_with()`.
- 연관 컨테이너에 대한 `contains()`.
- ` list` 및 `forward_list`에 대한 `remove()`, `remove_if()` 및 `unique()`가 이제 `size_type`을 반환합니다.
- `shift_left()` 및 `shift_right()`가 \<algorithm>에 추가되었습니다.

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019-rtw"></a>Visual Studio 2019 RTW의 버그 수정 및 동작 변경

### <a name="correct-diagnostics-for-basicstring-range-constructor"></a>Basic_string 범위 생성자에 대한 올바른 진단

Visual Studio 2019에서 `basic_string` 범위 생성자는 더 이상 `static_cast`를 사용하여 컴파일러 진단을 표시하지 않습니다. 다음 코드는 `out`을 초기화할 때 `wchar_t`에서 `char`로 데이터가 손실될 수 있음에도 불구하고 Visual Studio 2017에서 경고 없이 컴파일됩니다.

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end());
```

Visual Studio 2019에서 *C4244: 'argument': 데이터 손실이 가능한 'wchar_t'에서 'const _Elem'으로 변환*이 발생합니다. 경고를 방지하려면 다음 예제와 같이 std::string을 초기화할 수 있습니다.

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>/clr 또는 /ZW 아래에 += 및 -=에 대한 잘못된 호출 이제 올바르게 검색됩니다.

Visual Studio 2017에 버그가 도입되어 컴파일러는 자동으로 오류를 무시하고 `/clr` 또는 `/ZW`에서 += 및 -=에 대한 잘못된 호출 코드를 생성하지 않습니다. 다음 코드는 Visual Studio 2017에서 오류 없이 컴파일되지만 Visual Studio 2019에서는 *오류 C2845: 'System::string ^': 이 형식에서는 포인터 산술이 허용되지 않음*을 올바르게 발생시킵니다.

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // C2845 in VS2019
}
```

이 예제에서 오류를 방지하려면 ToString() 메서드(`s += E::e.ToString();`)와 함께 연산자를 사용합니다.

### <a name="initializers-for-inline-static-data-members"></a>인라인 정적 데이터 멤버에 대한 이니셜라이저

이제 `inline` 및 `static constexpr` 이니셜라이저 내에서 잘못된 멤버 액세스가 올바르게 검색됩니다. 다음 예제에서는 Visual Studio 2017에서 오류 없이 컴파일되지만 `/std:c++17` 모드 아래에 Visual Studio 2019에서는 *오류 C2248: 'X' 클래스에 선언된 프라이빗 멤버에 액세스할 수 없음*을 발생시킵니다.

```cpp
struct X
{
    private:
        static inline const int c = 1000;
};

struct Y : X
{
    static inline int d = c; // C2248 in Visual Studio 2019
};
```

오류를 방지하려면 `X::c` 멤버를 보호됨으로 선언합니다.

```cpp
struct X
{
    protected:
        static inline const int c = 1000;
};
```

### <a name="c4800-reinstated"></a>C4800 복원

MSVC는 너무 성가시고 억제할 수 없는 bool에 암시적 변환에 대한 성능 경고 C4800을 사용하여 Visual Studio 2017에서 제거했습니다. 그러나 Visual Studio 2017의 수명 주기 동안 해결 중인 유용한 사례에 대한 많은 피드백을 받았습니다. Visual Studio 2019에 세심하게 맞춤형된 C4800과 함께 동반되는 C4165를 다시 가져왔으며 둘 다 명시적 캐스팅이나 적절한 형식의 0과 비교하여 쉽게 표시되지 않습니다. C4800은 off-by-default 수준 4 경고이고 C4165는 off-by-default 수준 3 경고입니다. 둘 다 `/Wall` 컴파일러 옵션을 사용하여 검색할 수 있습니다.

다음 예제에서는 `/Wall`에서 C4800 및 C4165를 발생시킵니다.

```cpp
bool test(IUnknown* p)
{
    bool valid = p; // warning C4800: Implicit conversion from 'IUnknown*' to bool. Possible information loss
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return hr; // warning C4165: 'HRESULT' is being converted to 'bool'; are you sure this is what you want?
}
```

이전 예제에서 경고를 방지하려면 다음과 같은 코드를 작성하면 됩니다.

```cpp
bool test(IUnknown* p)
{
    bool valid = p != nullptr; // OK
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return SUCCEEDED(hr);  // OK
}
```

### <a name="local-class-member-function-doesnt-have-a-body"></a>로컬 클래스 멤버 함수에 본문이 없습니다.

Visual Studio 2017에서 *C4822: 로컬 클래스 멤버 함수에 본문이 없음*은 컴파일러 옵션 `/w14822`가 명시적으로 설정된 경우에만 발생합니다. `/Wall`에는 표시되지 않습니다. Visual Studio 2019에서 C4822는 `/w14822`를 명시적으로 설정하지 않고도 `/Wall`에서 검색할 수 있도록 하는 off-by-default 경고입니다.

```cpp
void foo()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-constexpr-if-statements"></a>constexpr if 문을 포함하는 함수 템플릿 본문

`if constexpr` 문을 포함하는 템플릿 함수 본문에 일부 `/permissive-` 구문 분석 관련 검사가 활성화되어 있습니다. 예를 들어 Visual Studio 2017에서 다음 코드는 C*7510: 'Type': 종속 형식 이름의 사용은 'typename' 접두사가 있어야 함*을 생성합니다. 이는 `/permissive-` 옵션이 설정되지 않은 경우에만 해당됩니다. Visual Studio 2019에서는 `/permissive-` 옵션이 설정되었는지 여부에 관계없이 동일한 코드가 오류를 발생시킵니다.

```cpp
template <typename T>

int f()
{
    T::Type a; // error C7510

    if constexpr (T::val)
    {
        return 1;
    }
    else
    {
        return 2;
    }
}

struct X
{
    using Type = X;
    constexpr static int val = 1;
};

int main()
{
    return f<X>();
}

```

이 오류를 방지하려면 `a` 선언 `typename T::Type a;`에 `typename` 키워드를 추가합니다.

### <a name="inline-assembly-code-is-not-supported-in-a-lambda-expression"></a>인라인 어셈블리 코드는 람다 식에서 지원되지 않습니다.

Visual C++ 팀은 최근 람다 내에서 인라인 어셈블러를 사용하면 런타임 시 'ebp'(반환 주소 레지스터)가 손상될 수 있는 보안 문제를 인식하게 되었습니다. 악의적인 공격자가 이 시나리오를 활용할 수 있습니다. 이 문제의 특성, 인라인 어셈블러가 x86에서만 지원된다는 사실과 인라인 어셈블러와 다른 컴파일러 간의 불량한 상호 작용을 고려할 때, 이 문제에 대한 가장 안전한 솔루션은 람다 식 내에서 인라인 어셈블러를 허용하지 않는 것입니다.

참고: 'wild'에서 접했던 람다 식 내에서 인라인 어셈블러의 유일한 사용은 반환 주소를 캡처하는 것이 목적이었습니다. 이 시나리오에서는 컴파일러 고유의 `_ReturnAddress()`를 사용하여 모든 플랫폼에서 반환 주소를 캡처할 수 있습니다.

다음 코드는 Visual Studio 2017 15.9 및 Visual Studio 2019에서 *C7552: 인라인 어셈블러는 람다에서 지원되지 않음*을 생성합니다.

```cpp
#include <cstdio>

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;

    auto lambda = [&]
    {
        __asm {

            mov eax, x
            mov y, eax
        }
    };

    lambda();
    return y;
}
```

오류를 방지하려면 다음 예제와 같이 어셈블리 코드를 명명된 함수로 이동합니다.

```cpp
#include <cstdio>

void g(int& x, int& y)
{
    __asm {
        mov eax, x
        mov y, eax
    }
}

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;
    auto lambda = [&]
    {
        g(x, y);
    };
    lambda();
    return y;
}

int main()
{
    std::printf("%d\n", f());
}
```

### <a name="iterator-debugging-and-stdmoveiterator"></a>반복기 디버깅 및 std::move_iterator

반복기 디버깅 기능이 `std::move_iterator`를 적절하게 래핑 해제하도록 학습되었습니다. 예를 들어 `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)`는 이제 `memcpy` 빠른 경로에 참여할 수 있습니다.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>\<xkeycheck.h> 키워드 적용 수정

표준 라이브러리의 macro-ized 키워드 적용 \<xkeycheck.h>는 일반 메시지가 아닌 검색된 실제 문제 키워드를 내보내도록 수정되었습니다. 또한 C++20 키워드를 지원하고 IntelliSense를 속여 임의의 키워드를 매크로로 가리키는 것을 방지합니다.

### <a name="allocator-types-un-deprecated"></a>사용되지 않는 할당자 유형

`std::allocator<void>`, `std::allocator::size_type` 및 `std::allocator::difference_type`은 사용 중단되었습니다.

### <a name="correct-warning-for-narrowing-string-conversions"></a>문자열 변환을 좁히기 위한 올바른 경고

실수로 C4244를 축소하는 경고를 억제한 표준에 의해 요청되지 않은 가짜 `static_cast`가 std::string에서 제거되었습니다. 이제 `std::string::string(const wchar_t*, const wchar_t*)`를 호출하려고 하면 *C4244 "wchar_t를 char로 축소합니다."* 를 적절히 내보냅니다.

### <a name="various-filesystem-correctness-fixes"></a>다양한 \<filesystem> 정확성 수정

- 디렉터리의 마지막 쓰기 시간을 변경하려고 할 때 `std::filesystem::last_write_time` 오류가 수정되었습니다.
- 존재하지 않는 대상 경로를 제공할 때 `std::filesystem::directory_entry` 생성자는 이제 예외를 throw하는 대신 실패한 결과를 저장합니다.
- existing_p가 symlink일 때 기본 `CreateDirectoryExW` 함수가 `copy_symlink`를 수행하므로 `std::filesystem::create_directory` 2-매개 변수 버전이 1-매개 변수 버전을 호출하도록 변경되었습니다.
- `std::filesystem::directory_iterator`는 손상된 symlink가 발생할 때 더 이상 실패하지 않습니다.
- `std::filesystem::space`는 이제 상대 경로를 허용합니다.
- `std::filesystem::path::lexically_relative`는 [LWG 3096](https://cplusplus.github.io/LWG/issue3096)으로 보고된 후행 슬래시로 더 이상 혼동하지 않습니다.
- `std::filesystem::create_symlink`에서 슬래시가 있는 경로를 거부하는 `CreateSymbolicLinkW`를 해결했습니다.
- Windows 10 LTSB 1609에 존재하지만 실제로 파일을 삭제할 수 없는 POSIX 삭제 모드 `delete` 함수를 해결했습니다.
- `std::boyer_moore_searcher` 및 `std::boyer_moore_horspool_searcher`의 복사 생성자 및 복사 할당 연산자는 이제 실제로 항목을 복사합니다.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Windows 8 이상의 병렬 알고리즘

병렬 알고리즘 라이브러리는 이제 Windows 7 및 이전 가짜 버전을 항상 사용하는 대신 Windows 8 이상에서 실제 `WaitOnAddress` 제품군을 올바르게 사용합니다.

### <a name="stdsystemcategorymessage-whitespace"></a>std::system_category::message() 공백

`std::system_category::message()`는 이제 반환된 메시지에서 후행 공백을 삭제합니다.

### <a name="stdlinearcongruentialengine-divide-by-zero"></a>0으로 std::linear_congruential_engine 나누기

`std::linear_congruential_engine`이 0으로 나누도록 트리거하는 일부 조건이 수정되었습니다.

### <a name="fixes-for-iterator-unwrapping"></a>반복기 래핑 해제를 위한 수정

Visual Studio 2017 15.8(https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/에서 설명한 대로)에서 프로그래머와 사용자 통합을 위해 처음 노출된 반복기 래핑 해제 머신은 더 이상 표준 라이브러리 반복기에서 파생된 반복기를 래핑 해제하지 않습니다. 예를 들어 `std::vector<int>::iterator`에서 파생되고 동작을 사용자 지정하려는 사용자는 이제 포인터의 동작 대신 표준 라이브러리 알고리즘을 호출할 때 사용자 지정된 동작을 가져옵니다.
순서가 지정되지 않은 컨테이너 예약 함수는 이제 [LWG 2156](https://cplusplus.github.io/LWG/issue2156)에 설명된 대로 N 요소를 실제로 예약합니다.

### <a name="time-handling"></a>시간 처리

- 이전에는 동시성 라이브러리에 전달된 일부 시간 값이 오버플로되었습니다(예: `condition_variable::wait_for(seconds::max())`). 이러한 오버플로는 현재 수정되어 있으며 임의의 29일 주기의 동작을 변경했습니다(기본 Win32 API가 허용하는 uint32_t 밀리초가 오버플로된 경우).

- <ctime> 헤더는 이제 글로벌 네임스페이스에서 선언하는 것 외에도 네임스페이스 std에서 timespec 및 timespec_get을 올바르게 선언합니다.

### <a name="various-fixes-for-containers"></a>컨테이너에 대한 다양한 수정

- 많은 표준 라이브러리 내부 컨테이너 함수가 향상된 IntelliSense 환경을 위해 프라이빗으로 만들어 졌습니다. MSVC의 후속 릴리스에서는 멤버를 프라이빗으로 표시하기 위한 추가 수정 사항이 예상됩니다.

- `list`, `map` 및 `unordered_map`과 같은 노드 기반 컨테이너가 손상되는 예외 안전 정확성 문제가 해결되었습니다. `propagate_on_container_copy_assignment` 또는 `propagate_on_container_move_assignment` 재할당 작업 중에 컨테이너의 sentinel 노드를 이전 할당자로 해제하고 이전 할당자를 통해 POCCA/POCMA 할당을 수행한 다음, 새 할당자에서 sentinel 노드를 가져오려고 시도합니다. 이 할당이 실패한 경우 컨테이너가 손상되더라도 제거되지는 않습니다. sentinel 노드를 소유하는 것은 하드 데이터 구조가 변하지 않기 때문입니다. 이는 기존 sentinel 노드를 제거하기 전에 원본 컨테이너의 할당자에서 새 sentinel 노드를 할당하도록 수정되었습니다.

- 컨테이너는 `is_always_equal`로 선언된 할당자에 대해서도 `propagate_on_container_copy_assignment`, `propagate_on_container_move_assignment` 및 `propagate_on_container_swap`에 따라 할당자를 항상 복사/이동/스왑하도록 수정되었습니다.

- [P0083 "맵 및 집합 스플라이스"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)에 따라 rvalue 컨테이너를 허용하는 컨테이너 병합 및 추출 멤버 함수에 대한 오버로드 추가

### <a name="stdbasicistreamread-processing-of-rn--n"></a>\r\n => \n의 std::basic_istream::read 처리

`std::basic_istream::read`는 \r\n => \n 처리의 일부로 제공된 버퍼의 부분에 임시로 쓰지 않도록 수정되었습니다. 이로 인해 Visual Studio 2017 15.8에서 4K보다 큰 읽기에 대해 얻은 성능상의 장점 중 일부를 포기하지만, 문자당 3개의 가상 호출을 방지함으로써 효율성이 향상되었습니다.

### <a name="stdbitset-constructor"></a>std::bitset 생성자

`std::bitset`의 생성자는 큰 비트 집합에 대해 더 이상 1과 0을 역순으로 읽지 않습니다.

### <a name="stdpairoperator-regression"></a>std::pair::operator= 회귀

[LWG 2729 "Missing SFINAE on std::pair::operator=";](https://cplusplus.github.io/LWG/issue2729)를 구현할 때 도입된 `std::pair`의 할당 연산자의 회귀가 수정되었습니다. 이제 `std::pair`로 변환할 수 있는 형식을 다시 올바르게 허용합니다.

### <a name="non-deduced-contexts-for-addconstt"></a>add_const_t에 대해 추론되지 않은 컨텍스트

`add_const_t` 및 관련 함수가 추론되지 않은 컨텍스트로 간주되는 부 형식 특성 버그를 수정했습니다. 즉, `add_const_t`는 `const T`가 아니라 `typename add_const<T>::type`의 별칭이어야 합니다.

## <a name="see-also"></a>참고 항목

[Visual Studio 2019의 새로운 기능](../what-s-new-for-visual-cpp-in-visual-studio.md)