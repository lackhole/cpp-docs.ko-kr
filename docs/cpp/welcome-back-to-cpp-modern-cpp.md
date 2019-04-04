---
title: C++의 진화(모던 C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
ms.openlocfilehash: 5b2868d20c047eef7762256ff8c9bf43de7a0de0
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58771788"
---
# <a name="welcome-back-to-c-modern-c"></a>C++의 진화(모던 C++)

C++는 전세계적으로 가장 널리 사용되는 프로그래밍 언어 중 하나입니다. 잘 작성된 C++ 프로그램은 빠르고 효율적입니다. 재미있고 흥미로운 게임에서부터 과학 분야의 고성능 소프트웨어, 장치 드라이버, 임베디드 장치용 프로그램 및 Windows 클라이언트 응용 프로그램에 이르기까지 다양한 응용 프로그램을 만드는 데 이 언어를 사용할 수 있어 다른 언어보다 뛰어난 유연성을 가지고 있습니다. C++는 20년 이상 이러한 문제와 기타 문제를 해결하는 데 사용되었습니다. 전반적으로 오래된 C 스타일 프로그래밍 대신 모던 C++를 사용하는 C++ 프로그래머의 수가 점점 증가하고 있습니다.

C++의 초기 철학 중 하나는 C 언어와의 하위 호환성입니다. C++는 클래스가 있는 C 언어, 초기의 C++ 언어 사양, 많은 후속 기능 개선의 순서로 반복적인 과정을 거쳐 발전되었습니다. 이러한 특성으로 인해 C++는 다중 패러다임 프로그래밍 언어라고 합니다. C++에서는 순수한 절차적 C 프로그래밍 스타일인 메모리를 직접 가리키는 포인터, 배열, null 종료 문자열, 사용자 지정 데이터 구조를 사용해 성능 향상을 얻을 수 있지만 버그나 복잡한 코드를 만들어낼 수도 있습니다.  C 스타일 프로그래밍의 이러한 위험과 어려움으로 인해, C++의 초기 목표 중 하나는 프로그램을 형식에 관계없이 안전하게 작성하고 확장하며 쉽게 유지관리하는 것이었습니다. 초기에는 C++에서 개체 지행 프로그래밍과 같은 프로그래밍 패러다임을 채택하였습니다. 수년간에 걸쳐 견고하게 검증된 표준 라이브러리의 데이터 구조 및 알고리즘과 함께 언어는 다양한 기능들을 흡수하였습니다. 이러한 변화들이 더해져 현대적인 모던 C++ 스타일이 정립되었습니다.

모던 C++는 다음을 강조합니다.

- 힙 또는 정적 전역 범위가 아닌 스택 기반 범위

- 명시적 형식 이름이 아닌 자동 형식 유추

- 원시 포인터가 아닌 스마트 포인터

- 원시 `char[]` 배열 대신 `std::string`, `std::wstring` 형식 [\<string> 참조](../standard-library/string.md)) 사용

- 원시 배열이나 사용자 정의 컨테이너 대신 `vector`, `list`, `map`과 같은 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-header-files.md)의 컨테이너를 사용하세요. [\<vector >](../standard-library/vector.md), [\<list >](../standard-library/list.md)[\<map >](../standard-library/map.md)을 참조합니다.

- 직접 만든 알고리즘 대신 C++ 표준 라이브러리의 [알고리즘](../standard-library/algorithm.md)을 사용합니다.

- 오류 조건 보고를 위한 예외 사용

- 스레드간 통신 매커니즘을 C++ 표준 라이브러리의 `std::atomic<>` (참조 [\<atomic>](../standard-library/atomic.md))으로 사용

- 작은 기능을 개별적으로 함수로 구현하는 대신 인라인 [람다 함수](../cpp/lambda-expressions-in-cpp.md)를 사용

- 배열, C++ 표준 라이브러리의 컨테이너 및 Windows 런타임 컬렉션과 함께, `for ( for-range-declaration : expression )`과 같은 형식의 강력한 루프를 작성할 수 있게 해주는 범위 기반 for 루프 사용. 핵심 언어 지원에 포함됩니다. 자세한 내용은 [범위 기반 for 문(C++)](../cpp/range-based-for-statement-cpp.md)를 참조합니다.

C++ 언어 자체도 발전하고 있습니다. 다음 코드 조각을 비교해 보십시오. 이 코드는 기존 C++의 방식을 보여 줍니다.

```cpp
#include <vector>

void f()
{
    // Assume circle and shape are user-defined types
    circle* p = new circle( 42 );
    vector<shape*> v = load_shapes();

    for( vector<circle*>::iterator i = v.begin(); i != v.end(); ++i ) {
        if( *i && **i == *p )
            cout << **i << " is a match\n";
    }

    // CAUTION: If v's pointers own the objects, then you
    // must delete them all before v goes out of scope.
    // If v's pointers do not own the objects, and you delete
    // them here, any code that tries to dereference copies
    // of the pointers will cause null pointer exceptions.
    for( vector<circle*>::iterator i = v.begin();
            i != v.end(); ++i ) {
        delete *i; // not exception safe
    }

    // Don't forget to delete this, too.
    delete p;
} // end f()
```

다음은 모던 C++에서 동일한 작업이 수행되는 방식입니다.

```cpp
#include <memory>
#include <vector>

void f()
{
    // ...
    auto p = make_shared<circle>( 42 );
    vector<shared_ptr<shape>> v = load_shapes();

    for( auto& s : v )
    {
        if( s && *s == *p )
        {
            cout << *s << " is a match\n";
        }
    }
}
```

모던 C++에서는 대신 스마트 포인터를 사용할 수 있기 때문에 new/delete나 명시적 예외 처리를 사용할 필요가 없습니다. **auto**를 이용한 형식 추론과 [람다 함수](../cpp/lambda-expressions-in-cpp.md)를 사용하면 더욱 빠르고 친화적이며 더 이해하기 쉬운 코드를 작성할 수 있습니다. 범위 기반 **for** 루프는 C 스타일 **for** 루프보다 깨끗하고 사용하기 쉽고 의도하지 않은 오류가 적습니다. 표준을 준수하는 최소한의 코드로 앱을 만드는 것이 가능합니다. 또한 코드가 예외나 메모리 관련 문제로부터 안전하며, 할당/할당해제나 에러 코드를 다루지 않아도 됩니다.

모던 C++는 템플릿을 이용한 컴파일 타임 다형성과 상속과 가상화를 이용한 런타임, 두 종류의 다형성을 사용할 수 있습니다. 두 가지의 다형성을 모두 사용하여 더 뛰어난 효과를 낼 수도 있습니다. C++ 표준 라이브러리 템플릿의 `shared_ptr`은 내부 가상 메소드를 사용하여 확실하고 편리하게 형식에 종속되는 문제를 해결해 줄 수 있습니다. 템플릿이 더 나은 선택인 경우 다형성을 위해 과도한 가상화를 사용하지 마십시오. 템플릿은 어떤 상황에도 좋은 선택입니다.

특히 대부분의 형식이 참조이고 값 형식이 거의 없는 매니지드 언어에서 C++를 사용하는 경우, C++ 클래스는 기본적으로 값 형식이라는 것에 주의해야 합니다. 하지만 참조 형식으로 지정하여 개체 지향 프로그래밍을 지원하는 다형성 동작을 사용할 수 있습니다. 유용 정보: 값 형식은 메모리 및 레이아웃 제어와 관련되고, 참조 형식은 기본 클래스 및 다형성을 지원하는 가상 함수와 관련되어 있습니다. 기본적으로 값 형식은 복사가 가능합니다. 각 형식에는 복사 생성자와 복사 할당 연산자가 있습니다. 참조 형식을 지정할 때는 클래스를 복사할 수 없도록 복사 생성자와 복사 할당 연산자를 사용하도록 설정하고 다형성을 올바르게 지원하도록 가상 소멸자를 사용하십시오. 값 형식은 또한 내용과 관련 있습니다. 즉 복사될 때 독립적인 값 두 개를 제공하여 따로 수정할 수 있습니다. 그러나 참조 형식은 개체의 종류를 나타내므로 다형 형식(Polymorphic Type)이라고도 합니다.

성능이 가장 중요해지면서 C++이 다시 주목받고 있습니다. 프로그래머의 생산성이 중요할 경우 Java와 C#과 같은 언어가 유용하지만, 강력함과 성능이 중요할 경우에는 한계를 보여줍니다. 특히 하드웨어가 제한적인 장치에서는 C++보다 뛰어난 것은 없습니다.

언어뿐만 아니라 개발 도구도 모던합니다. Visual Studio는 개발 주기의 모든 단계를 강력하고 효율적이게 만듭니다. ALM(Application Lifecycle Management) 도구, IntelliSense와 같은 향상된 IDE 기능, XAML과 같은 친숙한 도구 메커니즘, 빌드, 디버깅 및 기타 도구가 포함됩니다.

다음의 문서에서는 모던 C++ 프로그램을 작성하는 데 가장 중요한 기능 및 기술에 대한 고급 지침 및 모범 사례를 제공합니다.

- [C++ 형식 시스템](../cpp/cpp-type-system-modern-cpp.md)

- [균일 초기화 및 생성자 위임](../cpp/uniform-initialization-and-delegating-constructors.md)

- [개체 수명 및 리소스 관리](../cpp/object-lifetime-and-resource-management-modern-cpp.md)

- [리소스를 소유하는 오브젝트(RAII)](../cpp/objects-own-resources-raii.md)

- [스마트 포인터(모던 C++)](../cpp/smart-pointers-modern-cpp.md)

- [컴파일 시간 캡슐화 Pimpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md)

- [컨테이너](../cpp/containers-modern-cpp.md)

- [알고리즘](../cpp/algorithms-modern-cpp.md)

- [문자열 및 I/O 서식(모던 C++)](../cpp/string-and-i-o-formatting-modern-cpp.md)

- [오류 및 예외 처리(모던 C++)](../cpp/errors-and-exception-handling-modern-cpp.md)

- [ABI 경계의 이식성](../cpp/portability-at-abi-boundaries-modern-cpp.md)

자세한 내용은 Stack Overflow 문서를 참조 [c +는 + 관용구는 C + + 11에서 사용 되지 않는](https://stackoverflow.com/questions/9299101/which-c-idioms-are-deprecated-in-c11)합니다.

## <a name="see-also"></a>참고자료

[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[람다 식](../cpp/lambda-expressions-in-cpp.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)<br/>
[Visual C++ 언어 규칙](../overview/visual-cpp-language-conformance.md)