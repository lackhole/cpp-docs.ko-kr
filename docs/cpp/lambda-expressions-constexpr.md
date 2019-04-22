---
title: C++의 constexpr 람다식
ms.date: 04/08/2019
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
ms.openlocfilehash: d1bc60a6da813e54c857da38b0164f544216be00
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59424185"
---
# <a name="constexpr-lambda-expressions-in-c"></a>C++의 constexpr 람다식

**Visual Studio 2017 버전 15.3 이상** (사용할 수 있습니다 [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)): 람다 식으로 선언할 수 있습니다 **constexpr** 캡처하거나 소개 하는 각 데이터 멤버를 초기화 하는 상수 식 내에서 허용 되는 경우 상수 식에 사용 합니다.

```cpp
    int y = 32;
    auto answer = [y]() constexpr
    {
        int x = 10;
        return y + x;
    };

    constexpr int Increment(int n)
    {
        return [n] { return n + 1; }();
    }
```

람다는 결과가 **constexpr**함수의 요구사항을 만족하면 암시적으로 **constexpr**가 됩니다.

```cpp
    auto answer = [](int n)
    {
        return 32 + n;
    };

    constexpr int response = answer(10);
```

람다는 암시적 혹은 명시적으로도 **constexpr**이고, 함수 포인터로 변환하면 결과 함수도 **constexpr**입니다.

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```

## <a name="see-also"></a>참고자료

[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리의 함수 개체](../standard-library/function-objects-in-the-stl.md)<br/>
[함수 호출](../cpp/function-call-cpp.md)<br/>
[for_each](../standard-library/algorithm-functions.md#for_each)