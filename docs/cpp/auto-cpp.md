---
title: auto (C++)
ms.date: 11/04/2016
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
ms.openlocfilehash: 8af2aceb2964a5ec3adcbb0b0accab0b051ff48c
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303377"
---
# <a name="auto-c"></a>auto (C++)

초기화 식에서 선언된 변수의 형식을 추론합니다.

## <a name="syntax"></a>구문

```
auto declarator initializer;
```

```
[](auto param1, auto param2) {};
```

## <a name="remarks"></a>주의

**Auto** 키워드는 선언 된 변수 또는 람다 식 매개 변수의 초기화 식을 사용 하 여 해당 형식을 추론 하도록 컴파일러에 지시 합니다.

이러한 혜택을 제공 하기 때문에 대부분의 경우에는 **자동** 키워드를 사용 하 여 변환 하지 않는 것이 좋습니다.

- **견고성:** 식의 형식이 변경 된 경우 (함수 반환 형식이 변경 되는 경우 포함)에만 작동 합니다.

- **성능:** 변환이 발생 하지 않을 것으로 보장 됩니다.

- **유용성:** 형식 이름 철자 문제 및 오타가 걱정 하지 않아도 됩니다.

- **효율성:** 코딩을 보다 효율적으로 수행할 수 있습니다.

**Auto**를 사용 하지 않을 수 있는 변환 사례는 다음과 같습니다.

- 특정 형식을 원하는 경우 다른 항목은 사용할 수 없습니다.

- 식 템플릿 도우미 형식 (예: `(valarray+valarray)`).

**Auto** 키워드를 사용 하려면 형식 대신이 키워드를 사용 하 여 변수를 선언 하 고 초기화 식을 지정 합니다. 또한 **const**, **volatile**, 포인터 (`*`), 참조 (`&`) 및 rvalue 참조 (`&&`)와 같은 지정자와 선언 자를 사용 하 여 **auto** 키워드를 수정할 수 있습니다. 컴파일러는 초기화 식을 계산하고 해당 정보를 사용하여 변수의 형식을 추론합니다.

초기화 식은 할당 (등호 구문), 직접 초기화 (함수 스타일 구문), [operator new](new-operator-cpp.md) 식 또는 초기화 식이 [범위 기반 for statement (C++)](../cpp/range-based-for-statement-cpp.md) 문의 *범위 선언* 매개 변수가 될 수 있습니다. 자세한 내용은이 문서의 뒷부분에 나오는 [이니셜라이저](../cpp/initializers.md) 및 코드 예제를 참조 하세요.

**Auto** 키워드는 형식에 대 한 자리 표시자 이지만 자체 형식이 아닙니다. 따라서 **auto** 키워드는 [sizeof](../cpp/sizeof-operator.md) 및 (/cli의 경우 C++) [typeid](../extensions/typeid-cpp-component-extensions.md)와 같은 캐스트 또는 연산자에서 사용할 수 없습니다.

## <a name="usefulness"></a>유용성

**Auto** 키워드는 복잡 한 형식의 변수를 선언 하는 간단한 방법입니다. 예를 들어 **auto** 를 사용 하 여 초기화 식에 템플릿, 함수에 대 한 포인터 또는 멤버에 대 한 포인터를 포함 하는 변수를 선언할 수 있습니다.

**Auto** 를 사용 하 여 람다 식에 대 한 변수를 선언 하 고 초기화할 수도 있습니다. 람다 식의 형식은 컴파일러에만 알려져 있기 때문에 직접 변수 유형을 선언할 수 없습니다. 자세한 내용은 [람다 식의 예](../cpp/examples-of-lambda-expressions.md)를 참조 하세요.

## <a name="trailing-return-types"></a>후행 반환 형식

**Auto**를 **decltype** 형식 지정자와 함께 사용 하 여 템플릿 라이브러리를 작성할 수 있습니다. **Auto** 및 **decltype** 을 사용 하 여 반환 형식이 해당 템플릿 인수의 형식에 종속 되는 템플릿 함수를 선언 합니다. 또는 **auto** 와 **decltype** 을 사용 하 여 다른 함수에 대 한 호출을 래핑하는 템플릿 함수를 선언한 다음 다른 함수의 반환 형식을 반환 합니다. 자세한 내용은 [decltype](../cpp/decltype-cpp.md)를 참조 하세요.

## <a name="references-and-cv-qualifiers"></a>참조 및 cv 한정자

**자동** 삭제 참조, const 한정자 및 volatile 한정자를 사용 합니다. 다음 예를 살펴 보십시오.

```cpp
// cl.exe /analyze /EHsc /W4
#include <iostream>

using namespace std;

int main( )
{
    int count = 10;
    int& countRef = count;
    auto myAuto = countRef;

    countRef = 11;
    cout << count << " ";

    myAuto = 12;
    cout << count << endl;
}
```

이전 예제에서 myAuto는 int 참조가 아닌 int 이므로 참조 한정자가 **auto**에 의해 삭제 되지 않은 경우와 같이 출력은 `11 11``11 12` 되지 않습니다.

## <a name="type-deduction-with-braced-initializers-c14"></a>중괄호로 묶인 이니셜라이저를 사용 하 여 형식 추론 (c + + 14)

다음 코드 예제에서는 중괄호를 사용 하 여 자동 변수를 초기화 하는 방법을 보여 줍니다. B와 C 간의 차이와 A와 E 사이의 차이를 확인 합니다.

```cpp
#include <initializer_list>

int main()
{
    // std::initializer_list<int>
    auto A = { 1, 2 };

    // std::initializer_list<int>
    auto B = { 3 };

    // int
    auto C{ 4 };

    // C3535: cannot deduce type for 'auto' from initializer list'
    auto D = { 5, 6.7 };

    // C3518 in a direct-list-initialization context the type for 'auto'
    // can only be deduced from a single initializer expression
    auto E{ 8, 9 };

    return 0;
}
```

## <a name="restrictions-and-error-messages"></a>제한 사항 및 오류 메시지

다음 표에서는 **auto** 키워드의 사용에 대 한 제한 사항과 컴파일러가 내보내는 해당 진단 오류 메시지를 나열 합니다.

|오류 번호|설명|
|------------------|-----------------|
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|**Auto** 키워드는 다른 형식 지정자와 함께 사용할 수 없습니다.|
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|**Auto** 키워드를 사용 하 여 선언 된 기호에는 이니셜라이저가 있어야 합니다.|
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|**Auto** 키워드를 잘못 사용 하 여 형식을 선언 했습니다. 예를 들어 메서드 반환 형식 또는 배열을 선언했습니다.|
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|**Auto** 키워드를 사용 하 여 매개 변수 또는 템플릿 인수를 선언할 수 없습니다.|
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|**Auto** 키워드를 사용 하 여 메서드 또는 템플릿 매개 변수를 선언할 수 없습니다.|
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|초기화되기 전에 기호를 사용할 수 없습니다. 실제로, 이는 변수를 사용하여 자신을 초기화할 수 없음을 의미합니다.|
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|**Auto** 키워드를 사용 하 여 선언 된 형식으로 캐스팅할 수 없습니다.|
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|**Auto** 키워드를 사용 하 여 선언 된 선언 자 목록의 모든 기호는 동일한 형식으로 확인 되어야 합니다. 자세한 내용은 [선언 및 정의](declarations-and-definitions-cpp.md)를 참조 하세요.|
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|**Auto** 키워드를 사용 하 여 선언 된 기호에는 [sizeof](../cpp/sizeof-operator.md) 및 [typeid](../extensions/typeid-cpp-component-extensions.md) 연산자를 적용할 수 없습니다.|

## <a name="examples"></a>예

이러한 코드 조각은 **auto** 키워드를 사용할 수 있는 몇 가지 방법을 보여 줍니다.

다음 선언은 동일합니다. 첫 번째 문에서는 변수 `j` **int**형식으로 선언 됩니다. 두 번째 문에서는 초기화 식 (0)이 정수 이므로 변수 `k`를 **int** 형식으로 추론 합니다.

```cpp
int j = 0;  // Variable j is explicitly type int.
auto k = 0; // Variable k is implicitly type int because 0 is an integer.
```

다음 선언은 동일하지만 두 번째 선언이 첫 번째 선언보다 간단합니다. **Auto** 키워드를 사용 하는 가장 중요 한 이유 중 하나는 단순성입니다.

```cpp
map<int,list<string>>::iterator i = m.begin();
auto i = m.begin();
```

다음 코드 조각은 `iter` 변수의 형식과 **의 for** 및 range **for** 루프가 시작 될 때 `elem`를 선언 합니다.

```cpp
// cl /EHsc /nologo /W4
#include <deque>
using namespace std;

int main()
{
    deque<double> dqDoubleData(10, 0.1);

    for (auto iter = dqDoubleData.begin(); iter != dqDoubleData.end(); ++iter)
    { /* ... */ }

    // prefer range-for loops with the following information in mind
    // (this applies to any range-for with auto, not just deque)

    for (auto elem : dqDoubleData) // COPIES elements, not much better than the previous examples
    { /* ... */ }

    for (auto& elem : dqDoubleData) // observes and/or modifies elements IN-PLACE
    { /* ... */ }

    for (const auto& elem : dqDoubleData) // observes elements IN-PLACE
    { /* ... */ }
}
```

다음 코드 조각에서는 **new** 연산자와 포인터 선언을 사용 하 여 포인터를 선언 합니다.

```cpp
double x = 12.34;
auto *y = new auto(x), **z = new auto(&x);
```

다음 코드 조각은 각 선언문에서 여러 기호를 선언합니다. 각 명령문의 모든 기호는 동일한 형식으로 확인됩니다.

```cpp
auto x = 1, *y = &x, **z = &y; // Resolves to int.
auto a(2.01), *b (&a);         // Resolves to double.
auto c = 'a', *d(&c);          // Resolves to char.
auto m = 1, &n = m;            // Resolves to int.
```

다음 코드 조각은 조건부 연산자(`?:`)를 사용하여 변수 `x`를 정수 값을 200 값을 갖는 정수로 선언합니다.

```cpp
int v1 = 100, v2 = 200;
auto x = v1 > v2 ? v1 : v2;
```

다음 코드 조각에서는 변수 `x`를 **int**형식에 대 한 참조로, 변수 `y`를 **int 형식에**대 한 참조로 초기화 하 고 **int**형식을 반환 하는 함수에 대 한 `fp` 변수를 초기화 합니다.

```cpp
int f(int x) { return x; }
int main()
{
    auto x = f(0);
    const auto& y = f(1);
    int (*p)(int x);
    p = f;
    auto fp = p;
    //...
}
```

## <a name="see-also"></a>참고 항목

[auto 키워드](../cpp/auto-keyword.md)<br/>
[키워드](../cpp/keywords-cpp.md)<br/>
[/Zc:auto(변수 형식 추론)](../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof 연산자](../cpp/sizeof-operator.md)<br/>
[typeid](../extensions/typeid-cpp-component-extensions.md)<br/>
[operator new](new-operator-cpp.md)<br/>
[선언 및 정의](declarations-and-definitions-cpp.md)<br/>
[람다 식의 예](../cpp/examples-of-lambda-expressions.md)<br/>
[이니셜라이저](../cpp/initializers.md)<br/>
[decltype](../cpp/decltype-cpp.md)
