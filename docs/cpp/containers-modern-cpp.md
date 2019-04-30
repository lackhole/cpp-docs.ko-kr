---
title: 컨테이너(모던 C++)
ms.date: 1/18/2018
ms.topic: conceptual
ms.openlocfilehash: 2da57bfca8b04f50a223dddfb886835c69f746a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392338"
---
# <a name="containers-modern-c"></a>컨테이너(모던 C++)

기본적으로 C++에서 기본 순차 컨테이너로서의 [vector](../standard-library/vector-class.md)를 사용합니다. 이것은 .NET 언어에서의 `List<T>`와 동일합니다.

```cpp
vector<string> apples;
apples.push_back("Granny Smith");
```

기본 연관 컨테이너로 [map](../standard-library/map-class.md)(`unordered_map`이 아님)을 사용합니다. 디제너레이트 및 다중 사례에 대해 [set](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md), [multiset](../standard-library/multiset-class.md)을 사용합니다.

```cpp
map<string, string> apple_color;
// ...
apple_color["Granny Smith"] = "Green";
```

성능 최적화가 필요하면 다음을 사용합니다.

- 클래스 맴버와 같이 어떤 것에 속하는 경우 [배열](../standard-library/array-class-stl.md) 형식을 사용합니다.

- 같은 순서가 상관 없는 경우 [unordered_map](../standard-library/unordered-map-class.md)과 같은 연관 컨테이너를 사용합니다. 이러한 요소는 컨테이너의 각 항목당 부하가 낮거나 상수 시간에 검색이 되지만, 정확하고 효율적으로 사용하는 것이 어려울 수 있습니다.

- 순서가 있는 `vector`. 자세한 내용은 [알고리즘](../cpp/algorithms-modern-cpp.md)을 참조하세요.

C 스타일의 배열을 사용하지 마세요. 데이터에 대하여 직접 액세스가 필요한 이전 API의 경우 `f(vec.data(), vec.size());`와 같은 접근자 메서드를 대신 사용하세요.

컨테이너에 대한 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

[C++의 진화(모던 C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)
