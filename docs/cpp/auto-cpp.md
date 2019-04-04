---
title: auto (c + +)
ms.date: 11/04/2016
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
ms.openlocfilehash: 3d77a17d490f8d7680f095367c309ce0e4f366b7
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776338"
---
# <a name="auto-c"></a>auto (c + +)

초기화 식에서 선언된 변수의 형식을 추론합니다.

## <a name="syntax"></a>구문

```
auto declarator initializer;
```

```
[](auto param1, auto param2) {};
```

## <a name="remarks"></a>설명

합니다 **자동** 키워드에 해당 형식을 추론 하도록 선언 된 변수 또는 람다 식 매개 변수의 초기화 식을 사용 하도록 컴파일러에 지시 합니다.

사용 하는 것이 좋습니다는 **자동** 대부분의 상황에 대 한 키워드-실제로 변환 하려는 경우가 아니면, 이러한 혜택을 제공 하기 때문에:

- **견고성:** 식의 형식이 변경 되 면-여기에 함수 반환 형식이 변경 되 면-도 작동 합니다.

- **성능:** 변환 작업 없이 되도록 보장할 수 있습니다.

- **사용 편의성:** 형식 이름 맞춤법 문제 및 오타를 걱정할 필요가 없습니다.

- **효율성:** 코딩 하는 것은 더 효율적일 수 있습니다.

변환의 경우는 데 사용할 하지 않을 수 있습니다 **자동**:

- 특정 형식을 원하는 경우 다른 항목은 사용할 수 없습니다.

- 식 템플릿 도우미 형식-예를 들어 `(valarray+valarray)`합니다.

사용 하 여 **자동** 키워드 대신 사용 하 여 형식 변수를 선언 및 초기화 식을 지정 합니다. 수정할 수는 또한 합니다 **자동** 키워드와 같은 지정자와 선언 자를 사용 하 여 **const**를 **volatile**, 포인터 (`*`), 참조 (`&`), 및 rvalue 참조 (`&&`). 컴파일러는 초기화 식을 계산하고 해당 정보를 사용하여 변수의 형식을 추론합니다.

초기화 식은 할당 (등호 구문), 직접 초기화 (함수-스타일 구문)이 될 수는 [new 연산자](new-operator-cpp.md) 식 또는 초기화 식 수는  *에 대 한 범위-선언* 의 매개 변수를 [범위에 대 한 문 (c + +)를 기준으로](../cpp/range-based-for-statement-cpp.md) 문입니다. 자세한 내용은 [이니셜라이저](../cpp/initializers.md) 및이 문서의 코드 예제입니다.

합니다 **자동** 키워드는 형식에 대 한 자리 표시자 이지만 그 자체가 형식입니다. 따라서 합니다 **자동** 키워드의 캐스트 또는 연산자와 같은 사용할 수 없습니다 [sizeof](../cpp/sizeof-operator.md) 하 고 (C + + CLI) [typeid](../extensions/typeid-cpp-component-extensions.md)합니다.

## <a name="usefulness"></a>유용성

합니다 **자동** 키워드는 복잡 한 형식의 변수를 선언 하는 간단한 방법입니다. 예를 들어 사용할 수 있습니다 **자동** 초기화 식이 템플릿, 함수에 대 한 포인터 또는 멤버에 대 한 포인터를 포함 하는 위치 변수를 선언 합니다.

사용할 수도 있습니다 **자동** 선언 하 고 람다 식에 변수를 초기화 합니다. 람다 식의 형식은 컴파일러에만 알려져 있기 때문에 직접 변수 유형을 선언할 수 없습니다. 자세한 내용은 [람다 식의 예](../cpp/examples-of-lambda-expressions.md)합니다.

## <a name="trailing-return-types"></a>후행 반환 형식

사용할 수 있습니다 **자동**함께 합니다 **decltype** 형식 지정자를 템플릿 라이브러리를 작성 하는 방법입니다. 사용 하 여 **자동** 하 고 **decltype** 반환 하는 템플릿 함수를 선언 하 형식이 해당 템플릿 인수의 형식에 종속 됩니다. 또는 사용 하 여 **자동** 하 고 **decltype** 다른 함수에 대 한 호출을 래핑한 후 다른 함수의 반환 형식 무엇이 반환 하는 템플릿 함수를 선언 하 합니다. 자세한 내용은 [decltype](../cpp/decltype-cpp.md)합니다.

## <a name="references-and-cv-qualifiers"></a>참조 및 cv 한정자

사용 하 여 유의 **자동** 참조, const 한정자 및 volatile 한정자를 삭제 합니다. 다음 예제를 참조하세요.

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

이전 예에서 myAuto가 int, int 참조 되지 있으므로 출력은 `11 11`이 아니라 `11 12` 참조 한정자에 의해 삭제 되지 해야 하는 경우에 해당 것 처럼 **자동**합니다.

## <a name="type-deduction-with-braced-initializers-c14"></a>중괄호로 묶인된 이니셜라이저 (C + + 14)를 사용 하 여 형식 추론

다음 코드 예제에서는 중괄호를 사용 하 여 자동 변수를 초기화 하는 방법을 보여 줍니다. A 및 B와 C 간의 차이 확인 하 고 5.

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

다음 표에서 사용에 대 한 제한 된 **자동** 키워드 및 컴파일러에서 내보내는 해당 진단 오류 메시지입니다.

|오류 번호|설명|
|------------------|-----------------|
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|합니다 **자동** 다른 형식 지정자를 사용 하 여 키워드를 함께 사용할 수 없습니다.|
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|선언 된 기호는 **자동** 키워드에는 이니셜라이저가 있어야 합니다.|
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|잘못 사용 하 여 **자동** 형식을 선언 하는 키워드입니다. 예를 들어 메서드 반환 형식 또는 배열을 선언했습니다.|
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|매개 변수 또는 템플릿 인수를 사용 하 여 선언할 수 없습니다는 **자동** 키워드입니다.|
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|메서드 또는 템플릿 매개 변수를 선언할 수 없습니다는 **자동** 키워드입니다.|
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|초기화되기 전에 기호를 사용할 수 없습니다. 실제로, 이는 변수를 사용하여 자신을 초기화할 수 없음을 의미합니다.|
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|선언 된 형식으로 캐스팅할 수 없습니다는 **자동** 키워드입니다.|
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|선언 된 선언 자 목록의 모든 기호는 **자동** 키워드는 같은 형식으로 확인 해야 합니다. 자세한 내용은 [선언 및 정의](declarations-and-definitions-cpp.md)합니다.|
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|합니다 [sizeof](../cpp/sizeof-operator.md) 하 고 [typeid](../extensions/typeid-cpp-component-extensions.md) 연산자를 사용 하 여 선언 된 기호에 적용할 수 없습니다는 **자동** 키워드입니다.|

## <a name="examples"></a>예제

이러한 코드 조각을 설명 하는 방법의 일부를 **자동** 키워드를 사용할 수 있습니다.

다음 선언은 동일합니다. 첫 번째 문에서 변수 `j` 형식으로 선언 된 **int**합니다. 두 번째 문에서 변수 `k` 형식으로 추론 되었습니다 **int** 초기화 식 (0)가 정수 이므로 합니다.

```cpp
int j = 0;  // Variable j is explicitly type int.
auto k = 0; // Variable k is implicitly type int because 0 is an integer.
```

다음 선언은 동일하지만 두 번째 선언이 첫 번째 선언보다 간단합니다. 사용 하 여 가장 중요 한 이유 중 하나를 **자동** 키워드는 단순성입니다.

```cpp
map<int,list<string>>::iterator i = m.begin();
auto i = m.begin();
```

다음 코드 조각 형식의 변수를 선언 `iter` 하 고 `elem` 때 합니다 **에 대 한** 및 범위 **에 대 한** 루프가 시작 합니다.

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

다음 코드 조각을 사용 하는 **새** 포인터를 선언 하는 연산자 및 포인터 선언 합니다.

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

변수를 초기화 하는 다음 코드 조각 `x` 형식으로 **int**가변 `y` 입력에 대 한 참조를 **const int**, 및 변수 `fp` 함수에 대 한 포인터 형식을 반환 하 **int**합니다.

```cpp
int f(int x) { return x; }
int main()
{
    auto x = f(0);
    const auto & y = f(1);
    int (*p)(int x);
    p = f;
    auto fp = p;
    //...
}
```

## <a name="see-also"></a>참고자료

[auto 키워드](../cpp/auto-keyword.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[/Zc:auto(변수 형식 추론)](../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof 연산자](../cpp/sizeof-operator.md)<br/>
[typeid(C++ 구성 요소 확장)](../extensions/typeid-cpp-component-extensions.md)<br/>
[operator new](new-operator-cpp.md)<br/>
[선언 및 정의](declarations-and-definitions-cpp.md)<br/>
[람다 식의 예](../cpp/examples-of-lambda-expressions.md)<br/>
[이니셜라이저](../cpp/initializers.md)<br/>
[decltype](../cpp/decltype-cpp.md)
