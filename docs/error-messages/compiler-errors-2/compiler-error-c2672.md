---
title: 컴파일러 오류 C2672
ms.date: 10/24/2017
f1_keywords:
- C2672
helpviewer_keywords:
- C2672
ms.assetid: 7e86338a-2d4b-40fe-9dd2-ac6886f3f31a
ms.openlocfilehash: df0f656c9db23739ec62629088b9cc5f7950a92d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386865"
---
# <a name="compiler-error-c2672"></a>컴파일러 오류 C2672

> '*함수*': 오버 로드 된 함수를 찾을 수 없는 일치

컴파일러는 지정된 된 함수를 일치 하는 오버 로드 된 함수를 찾을 수 없습니다. 매개 변수 또는 일치 하는 함수가 일치 하는 상황에 맞는 필수 내게 필요한 옵션에는 아무런 기능을 찾았습니다.

특정 표준 라이브러리 컨테이너 또는 알고리즘을 사용 하는 경우 형식에 액세스할 수 있는 멤버 또는 컨테이너 또는 알고리즘의 요구 사항을 충족 하는 friend 함수를 제공 해야 합니다. 반복기 형식에서 파생 되어야 예를 들어 `std::iterator<>`합니다. 비교 연산 또는 컨테이너 요소 형식에 다른 연산자의 사용을 왼쪽 및 오른쪽 피연산자를 형식으로 간주 필요할 수 있습니다. 사용 유형 오른쪽 피연산자 형식의 비멤버 함수로 구현 된 연산자를 요구할 수 있습니다.

## <a name="example"></a>예제

버전의 Visual Studio 2017 이전 컴파일러는 일부 템플릿 컨텍스트에서 정규화 된 이름에 대 한 액세스 검사를 수행 하지 않았습니다. 이는 이름에 액세스할 수 없기 때문에 대체에 실패할 것으로 예상되는 경우 예상되는 SFINAE 동작을 방해할 수 있습니다. 따라서 컴파일러가 연산자의 잘못된 오버로드를 잘못 호출하기 때문에 잠재적으로 런타임에 크래시나 예기치 않은 동작이 발생했을 수 있습니다. Visual Studio 2017에서는 컴파일러 오류가 발생합니다.

이 예제에서는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017에서 오류를 발생 시킵니다. 이 문제를 해결 하려면 계산 되는 액세스할 수 있는 템플릿 매개 변수 멤버를 확인 합니다.

```cpp
#include <type_traits>

template <class T> class S {
// public:    // Uncomment this line to fix
    typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x)
{
    return (x == 0);
}

int main()
{
    f(10); // C2672: No matching overloaded function found.
}
```