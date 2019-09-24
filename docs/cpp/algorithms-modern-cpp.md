---
title: 알고리즘(모던 C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 6f758d3c-a7c7-4a50-92bb-97b2f6d4ab27
ms.openlocfilehash: b972e575c982ae2523ec560a6237eac76ceaf834
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345171"
---
# <a name="algorithms-modern-c"></a>알고리즘(모던 C++)

모던 C++ 프로그래밍 적용을 위해 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)의 알고리즘을 사용하는 것을 권장합니다. 다음은 몇가지 주요 예를 보여줍니다.

- 기본 탐색 알고리즘인 **for_each** (또한 **transform**도 고려할 수 있습니다.)

- 기본 검색 알고리즘인 **find_if**

- **sort**, **lower_bound**와 그 밖의 기본 정렬 및 검색 알고리즘

비교자를 만들기 위해 비교 연산자 **<** 를 사용하고 가능한 경우 *이름있는 람다(named lambdas)* 를 사용하세요.

```cpp
auto comp = [](const widget& w1, const widget& w2)
     { return w1.weight() < w2.weight(); }

sort( v.begin(), v.end(), comp );

auto i = lower_bound( v.begin(), v.end(), comp );
```

## <a name="loops"></a>루프

가능한 경우 수작업으로 만든 루프를 사용하는 대신 범위 기반 **for**나 알고리즘을 호출하거나 혹은 두 가지를 모두 사용하세요. **copy**, **transform**, **count_if**, **remove_if** 등의 유형은 의도가 분명하고 보다 버그 없는 코드를 작성하기가 쉽기 때문에 수작업으로 작성한 루프보다 훨씬 좋습니다. 또한 많은 C++ 라이브러리 알고리즘에는 보다 효율적으로 구현된 최적화된 기능이 있습니다.

다음과 같은 이전 C++ 대신:

```cpp
for ( auto i = strings.begin(); i != strings.end(); ++i ) {
    /* ... */
}

auto i = v.begin();

for ( ; i != v.end(); ++i ) {
    if (*i > x && *i < y) break;
}
```

최신 C++을 다음과 같이 사용합니다.

```cpp
for_each( begin(strings), end(strings), [](string& s) {
  // ...
} );

auto i = find_if( begin(v), end(v),  [=](int i) { return i > x && i < y; } );
```

### <a name="range-based-for-loops"></a>범위 기반 for 루프

범위 기반 **for** 루프는 C ++ 표준 라이브러리 알고리즘이 아닌 C ++ 11 언어 기능입니다. 최신 기능이긴 하지만 이 루프 방법은 고민해볼 필요가 있습니다. 범위 기반 **for** 루프는 **for** 루프에 대한 키워드 확장이며 다양한 범위의 값을 반복하는 루프를 작성할 때 편리하고 효율적인 방법을 제공합니다. C++ 표준 라이브러리 컨테이너, 문자열 및 배열은 범위 기반 **for** 루프와 잘 어울려 사용할 수 있습니다. 사용자 정의 형식이 이러한 새로운 반복 구문을 사용하려면 다음 지원을 추가합니다.

- 구조체의 시작 부분에 반복자를 반환하는 `begin` 메서드와 반복자의 끝을 반환하는 `end` 메서드를 준비합니다.

- **operator** <strong>\*</strong>, **operator !=** , **operator ++** (접두사 버전)과 같은 메서드를 반복기에서 지원합니다.

이러한 메서드는 멤버 또는 독립 실행형 함수일 수 있습니다.

## <a name="random-numbers"></a>난수

이전 CRT `rand()` 함수에 많은 결함이 있다고 C++ 커뮤니티에서 오랫동안 다루어지고 논의되어 왔습니다. 최신 C++에서는 이러한 단점을 다룰 필요가 없으며, 균일하게 분포된 난수생성기를 독창적으로 구현하지 않아도 됩니다. 난수를 빠르고 쉽게 생성할 수 있는 도구가 C++ 표준 라이브러리의 [\<random>](../standard-library/random.md)을 통해 제공됩니다.

## <a name="see-also"></a>참고자료

[C++의 진화(모던 C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)<br/>
