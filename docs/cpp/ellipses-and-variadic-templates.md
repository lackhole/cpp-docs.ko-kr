---
title: Ellipses 및 Variadic 템플릿
ms.date: 11/04/2016
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
ms.openlocfilehash: 387cf4478192cb9470804c219eee8046f8e47abe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392221"
---
# <a name="ellipses-and-variadic-templates"></a>Ellipses 및 Variadic 템플릿

이 문서에서는 줄임표를 사용 하는 방법을 보여 줍니다 (`...`) 사용 하 여 C++ variadic 템플릿. 줄임표는 C에서 다양 한 용도로 했습니다 및 C++입니다. 여기에 함수에 가변 인수 목록이 포함 됩니다. `printf()` C 런타임 라이브러리에서 함수는 가장 잘 알려진 예 중 하나입니다.

A *variadic 템플릿* 는 임의 개수의 인수를 지 원하는 클래스 또는 함수 템플릿입니다. 이 메커니즘에 특히 유용 C++ 라이브러리 개발자가 있으므로 클래스 템플릿과 함수 템플릿 모두에 적용 하 고 있으므로 다양 한 형식 안전 성과 특수 기능 및 유연성을 제공할 수 있습니다.

## <a name="syntax"></a>구문

줄임표는 variadic 템플릿에서 두 가지 방법으로 사용 됩니다. 매개 변수 이름의 왼쪽에 의미를 *매개 변수 팩*, 매개 변수 이름의 오른쪽에 별도 이름으로 매개 변수 팩을 확장 하 고 있습니다.

다음은 기본적인 예입니다 *variadic 템플릿 클래스* 정의 구문:

```cpp
template<typename... Arguments> class classname;
```

팩 및 확장 매개 변수의 경우 다음 예에서 같이 기본 설정에 따라 줄임표 주위에 공백을 추가할 수 있습니다.

```cpp
template<typename ...Arguments> class classname;
```

또는

```cpp
template<typename ... Arguments> class classname;
```

이 문서에서는 첫 번째 예제에 표시된 규칙(줄임표가 `typename`에 연결)을 사용합니다.

위의 예에서 *인수* 매개 변수 팩입니다. 클래스 `classname` 다음이 예와 같이 인수의 변수 숫자를 사용할 수 있습니다.

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
vtclass<long, std::vector<int>, std::string> vtinstance4;
```

Variadic 템플릿 클래스 정의 사용 하 여 하나 이상의 매개 변수가 필요할 수도 있습니다.

```cpp
template <typename First, typename... Rest> class classname;
```

다음은 기본적인 예입니다 *variadic 템플릿 함수* 구문:

```cpp
template <typename... Arguments> returntype functionname(Arguments... args);
```

합니다 *인수* 매개 변수 팩 사용에 대 한 확장 한 다음 다음 섹션에 표시 된 대로 **variadic 템플릿 이해**합니다.

Variadic 템플릿 함수 구문의 다른 형식을 사용할 수 있습니다-에 국한 되지 않음 이러한 예제를 포함 합니다.

```cpp
template <typename... Arguments> returntype functionname(Arguments&... args);
template <typename... Arguments> returntype functionname(Arguments&&... args);
template <typename... Arguments> returntype functionname(Arguments*... args);
```

와 같은 지정자 **const** 도 허용 됩니다.

```cpp
template <typename... Arguments> returntype functionname(const Arguments&... args);
```

Variadic 템플릿 클래스 정의 하나 이상의 매개 변수가 필요한 함수를 만들 수 있습니다.

```cpp
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);
```

Variadic 템플릿 사용은 `sizeof...()` 연산자 (이전의 관련이 `sizeof()` 연산자):

```cpp
template<typename... Arguments>
void tfunc(const Arguments&... args)
{
    constexpr auto numargs{ sizeof...(Arguments) };

    X xobj[numargs]; // array of some previously defined type X

    helper_func(xobj, args...);
}
```

## <a name="more-about-ellipsis-placement"></a>줄임표 배치에 대한 자세한 내용

이 문서의 앞 부분에서 "매개 변수 이름의 왼쪽은 매개 변수 팩을 나타내고 매개 변수 이름 오른쪽은 매개 변수 팩을 별도의 이름으로 확장"한다고 매개 변수 팩과 확장을 정의하는 줄임표 배치에 대해 설명했습니다. 이는 기술적으로는 맞지만 코드로 변환할 때 혼동될 수 있습니다. 고려 사항:

- 템플릿 매개 변수 목록에서 (`template <parameter-list>`), `typename...` 템플릿 매개 변수 팩을 소개 합니다.

- 매개 변수 선언 절에서 (`func(parameter-list)`), "최상위" 줄임표는 함수 매개 변수 팩을 소개 하 고 하므로 줄임표 배치 하는 것이 중요 합니다.

    ```cpp
    // v1 is NOT a function parameter pack:
    template <typename... Types> void func1(std::vector<Types...> v1);

    // v2 IS a function parameter pack:
    template <typename... Types> void func2(std::vector<Types>... v2);
    ```

- 매개 변수 이름 바로 뒤에 줄임표가 표시된 경우 매개 변수 팩 확장이 있는 것입니다.

## <a name="example"></a>예제

Variadic 템플릿 함수 메커니즘을 설명 하는 좋은 방법에서의 기능 중 일부의 다시 쓰기를 사용 하는 `printf`:

```cpp
#include <iostream>

using namespace std;

void print() {
    cout << endl;
}

template <typename T> void print(const T& t) {
    cout << t << endl;
}

template <typename First, typename... Rest> void print(const First& first, const Rest&... rest) {
    cout << first << ", ";
    print(rest...); // recursive call using pack expansion syntax
}

int main()
{
    print(); // calls first overload, outputting only a newline
    print(1); // calls second overload

    // these call the third overload, the variadic template,
    // which uses recursion as needed.
    print(10, 20);
    print(100, 200, 300);
    print("first", 2, "third", 3.14159);
}
```

## <a name="output"></a>출력

```Output
1
10, 20
100, 200, 300
first, 2, third, 3.14159
```

> [!NOTE]
>  Variadic 템플릿 함수를 통합 하는 대부분의 구현은 일부 양식의 재귀를 사용 하지만 전통적인 재귀와에서 약간 다릅니다.  전통적인 재귀는 같은 서명을 사용 하 여 자신을 호출 하는 함수에 포함 됩니다. (템플릿 또는 오버 로드 된 이름일 수 있습니다 하지만 동일한 서명 될 때마다 선택 되었습니다.) Variadic 재귀 (거의 항상 감소) 다른 개수의 인수를 사용 하 여 여 줄어듦 다른 서명을 때마다 variadic 함수 템플릿을 호출 해야 합니다. "기본 사례"는 여전히 필요 하지만 재귀적 특성 다릅니다.