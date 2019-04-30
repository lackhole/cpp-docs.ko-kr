---
title: constexpr(C++)
ms.date: 04/06/2018
f1_keywords:
- constexpr_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
ms.openlocfilehash: 3ab3b75589864c95cb345be57db39c028a02f8db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399098"
---
# <a name="constexpr-c"></a>constexpr(C++)

키워드 **constexpr**는 C++11에서 도입되었으며 C++14에서 향상되었습니다. *상수 식*을 뜻합니다. 와 같은 **const**, 코드 값을 수정 하려고 하는 경우 컴파일러 오류가 발생 되도록 변수에 적용할 수 있습니다. **const**와는 달리 **constexpr**는 함수와 클래스 생성자에 적용할 수도 있습니다. **constexpr** 함을 나타냅니다 값 또는 반환 값이 상수입니다. 가능한 경우 컴파일 타임에 계산 됩니다.

**constexpr** 정수 값은 템플릿 인수 및 배열 선언과 같은 const 정수가 필요할 때마다 사용될 수 있습니다. 그리고 값이 런타임 대신 컴파일 시간에 계산될 때, 프로그램을 보다 빠르게 돌아가게 하고 보다 적은 메모리를 사용하도록 도움을 줍니다.

컴파일 시간 상수 계산 및 컴파일 시간에 미치는 잠재적 영향의 복잡성을 최소화 하려면 표준 C + + 14 필요를 상수 식의 형식을 [리터럴 형식](trivial-standard-layout-and-pod-types.md#literal_types)합니다.

## <a name="syntax"></a>구문

> **constexpr** *리터럴 형식이* *식별자* ** = ** *상수-식* **;** 
>  **constexpr** *리터럴 형식이* *식별자* **{** *상수 식 * **}** **;** 
>  **constexpr** *리터럴 형식이* *식별자* **(** *params* **)** **;** 
>  **constexpr** *ctor* **(** *params* **)** **;**

## <a name="parameters"></a>매개 변수

*params*<br/>
하나 이상의 매개 변수는 각 리터럴 형식 이어야 하며 그 자체가 상수 식 이어야 합니다.

## <a name="return-value"></a>반환 값

Constexpr 변수 또는 함수는 [리터럴 형식](trivial-standard-layout-and-pod-types.md#literal_types)을 반환해야 합니다.

## <a name="constexpr-variables"></a>constexpr 변수

Const 및 constexpr 변수 간의 주요 차이점은 const 변수의 초기화는 런타임까지 지연 될 수 있습니다. Constexpr 변수는 컴파일 타임 초기화 되어야 합니다.  모든 constexpr 변수는 const입니다.

- 변수가 리터럴 형식이며 초기화되었다면 **constexpr**로 선언될 수 있습니다. 초기화를 생성자에서 수행하는 경우 생성자는 **constexpr**로 선언되어야만 합니다.

- 참조하는 개체가 상수 식으로 초기화되고 초기화 중에 호출되는 암시적 변환도 모두 상수 식인 경우 참조를 constexpr로 선언할 수 있습니다.

- 모든 **constexpr** 변수나 함수의 선언에는 **constexpr** 지정자가 있어야 합니다.

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a> constexpr 함수

A **constexpr** 함수는 반환 값인 경우 필요한 코드를 사용 하는 컴파일 시간에 계산할 수 있습니다. 코드를 사용 해야 반환 값은 컴파일 타임에 예를 들어 초기화를 **constexpr** 변수 또는 비형식 템플릿 인수를 제공 합니다. 해당 인수가 **constexpr** 값을 **constexpr** 함수는 컴파일 시간 상수를 생성 합니다. 비-를 사용 하 여 호출 하는 경우**constexpr** 인수 또는 해당 값이 아닌 컴파일 타임에 필요한, 일반 함수 처럼 런타임에 값을 생성 합니다. (이 이중 동작은 같은 함수의 **constexpr** 및 비-**constexpr** 버전을 각각 작성하지 않아도 되게 합니다.)

**constexpr** 함수 또는 생성자는 암시적으로 **인라인**입니다.

constexpr 함수에는 다음 규칙이 적용됩니다.

- **constexpr** 함수는 [리터럴 형식](trivial-standard-layout-and-pod-types.md#literal_types)만을 허용하거나 반환해야 합니다.

- **constexpr** 함수는 재귀적일 수 있습니다.

- [가상](../cpp/virtual-cpp.md)이 될 수 없습니다. 바깥쪽 클래스에 있는 경우 모든 가상 기본 클래스 생성자를 constexpr로 정의할 수 없습니다.

- 본문은 `= default` 또는 `= delete`로 정의할 수 있습니다.

- 본문에는 **goto** 문이나 try 블록이 포함될 수 없습니다.

- constexpr이 아닌 템플릿의 명시적 특수화를 **constexpr**로 선언할 수 있습니다.

- **constexpr** 템플릿의 명시적 특수화도 **constexpr**일 필요는 없습니다.

다음 규칙이 Visual Studio 2017 이상의 **constexpr** 함수에 적용됩니다.

- **if** 및 **switch** 문을 포함할 수 있으며 **for**, 범위 기반 for, **while**, **do-while**을 포함한 모든 반복문을 포함할 수 있습니다.

- 지역 변수 선언을 포함할 수 있지만 변수는 초기화되어야 하고 리터럴 형식이여야 하며 정적 또는 쓰레드 로컬일 수 없습니다. 로컬로 선언 된 변수는 const 일 필요는 없습니다 및 변경할 수 있습니다.

- Constexpr 비정적 멤버 함수는 암시적으로 const될 필요가 없습니다.

```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Visual Studio 디버거에서 최적화 되지 않은 디버깅 빌드를 디버그 하는 경우 알 수 있는지 여부를 **constexpr** 함수 내에 중단점을 배치 하 여 컴파일 시간에 평가 되는 합니다. 중단점이 적중할 경우 함수는 런타임에 호출되었으며,  그렇지 않다면 함수는 컴파일 시간에 호출되었습니다.

## <a name="extern-constexpr"></a>extern constexpr

[/zc: externconstexpr](../build/reference/zc-externconstexpr.md) 컴파일러 옵션은 컴파일러가 **extern constexpr**을 사용하여 선언된 변수에 [외부 링크](../c-language/external-linkage.md)()가 적용되게 합니다. 이전 버전의 Visual Studio에서와 기본적으로 혹은 **/Zc:externConstexpr-** 가 지정된 경우 Visual Studio는 **extern** 키워드가 사용 중이라도 내부 링크를 **constexpr** 변수에 적용합니다. **/zc: externconstexpr** 옵션은 Visual Studio 2017 업데이트 15.6 부터 사용할 수 있으며 기본적으로는 꺼져 있습니다. /permissive- 옵션은 /zc: externconstexpr을 활성화하지 않습니다.

## <a name="example"></a>예제

다음 예와 **constexpr** 변수, 함수 및 사용자 정의 형식입니다. Main ()의 마지막 문에서 **constexpr** 멤버 함수 getvalue () 값을 컴파일 타임에 알려질 필요가 없기 때문 런타임에 호출 됩니다.

```cpp
#include <iostream>

using namespace std;

// Pass by value
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};

// Pass by reference
constexpr float exp2(const float& x, const int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
};

// Compile-time computation of array length
template<typename T, int N>
constexpr int length(const T(&ary)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n*fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue()
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    // foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    // Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    // Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;

}
```

## <a name="requirements"></a>요구 사항

Visual Studio 2015

## <a name="see-also"></a>참고자료

[선언 및 정의](../cpp/declarations-and-definitions-cpp.md)<br/>
[const](../cpp/const-cpp.md)
