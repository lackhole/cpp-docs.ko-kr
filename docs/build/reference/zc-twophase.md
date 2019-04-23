---
title: '/Zc: twophase-(2 단계 이름 조회 사용 안 함)'
ms.date: 03/06/2018
f1_keywords:
- twoPhase
- /Zc:twoPhase
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
helpviewer_keywords:
- twoPhase
- disable two-phase name lookup
- /Zc:twoPhase
ms.openlocfilehash: 5f990181fd1e606cf9d7dd33242752bed33aa456
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58898754"
---
# <a name="zctwophase--disable-two-phase-name-lookup"></a>/Zc: twophase-(2 단계 이름 조회 사용 안 함)

경우는 **/zc: twophase-** 옵션을 지정 하면 컴파일러 구문 분석 하 고 동일한 맞지 않는 방식으로 버전의 Visual Studio 2017 버전 15.3 하기 전에 Visual Studio에서 클래스 템플릿과 함수 템플릿을 인스턴스화합니다.

## <a name="syntax"></a>구문

> **/Zc:twoPhase-**

## <a name="remarks"></a>설명

Visual Studio 2017 버전 15.3 이상 버전에서는 기본적으로 컴파일러는 템플릿 이름 확인에 대 한 2 단계 이름 조회를 사용합니다. 하는 경우 **/zc: twophase-** 를 지정 하면 컴파일러는 이전 비준수 클래스 템플릿과 함수 템플릿 이름 확인 및 대체 동작으로 돌아갑니다.

합니다 **/zc: twophase-** 기본적으로 비준수 동작을 사용 하도록 설정 하는 옵션을 설정 하지 않으면. [/ permissive-](permissive-standards-conformance.md) 옵션에는 암시적으로 표준에 맞는 2 단계 조회 컴파일러 동작을 설정 하지만 사용 하 여 재정의할 수 있습니다 **/zc: twophase-** 합니다.

(크리에이터 스 업데이트 또는 Redstone 2) 하는 10.0.15063.0 버전 및 이전 버전의 Windows SDK 헤더 파일 규칙 모드에서 제대로 작동 하지 않습니다. 사용 해야 합니다 **/zc: twophase-** Visual Studio 2017 버전 15.3 이상 사용 하는 경우 해당 SDK 버전에 대 한 코드를 컴파일할 수 있습니다. 10.0.15254.0 (레드 스톤 3 또는 Fall Creators Update) 버전부터 Windows SDK의 버전 준수 모드에서 제대로 작동 하 고 필요 하지는 **/zc: twophase-** 옵션입니다.

사용 하 여 **/zc: twophase-** 코드에 올바르게 컴파일되도록 하려면 이전 동작이 필요한 경우. 강력한 표준에 맞게 코드를 업데이트 하는 것이 좋습니다.

### <a name="compiler-behavior-under-zctwophase-"></a>/Zc: twophase-컴파일러 동작

전에 Visual Studio 2017 버전 15.3에서 컴파일러의 버전에서 및 시기 **/zc: twophase-** 를 지정 하면 컴파일러에서이 동작을 사용 합니다.

- 템플릿 선언의, 클래스 헤드와 기본 클래스 목록 구문 분석 합니다. 템플릿 본문 토큰 스트림으로 캡처됩니다. 함수 본문, 이니셜라이저, 기본 인수가 없거나 noexcept 인수 구문 분석 됩니다. 클래스 템플릿은 클래스 템플릿의 선언이 올바른지 유효성을 검사 하는 미정 형식에서 의사 인스턴스화된입니다. 이 클래스 템플릿 고려해 야 합니다.

   ```cpp
   template <typename T> class Derived : public Base<T> { ... }
   ```

   템플릿 선언의 `template <typename T`>를 클래스 헤드 `class Derived`, 및 기본 클래스 목록 `public Base<T>` 구문 분석 되 고 템플릿 본문 토큰 스트림을으로 캡처된다 면 있지만.

- 함수 템플릿을 구문 분석 하는 경우 컴파일러가 함수 서명에 구문 분석 합니다. 함수 본문은 구문 분석 하지 않습니다. 대신, 토큰 스트림으로 캡처됩니다.

결과적으로, 템플릿 본문에 구문 오류가 발생 했습니다. 템플릿을 초기화 되지 않는 경우에 오류 진단 되지 됩니다.

이 동작의 결과 다른 오버 로드 확인입니다. 토큰 스트림을 인스턴스화의 사이트에서 확장 방식으로 인해 템플릿 선언에 표시 되지 않은 기호는 인스턴스화 시점에서 표시 하 고 오버 로드 확인에 참여 수 있습니다. 이 표준 달리 템플릿에 정의 된 경우 표시 되는 코드를 기반으로 하는 동작을 변경 하는 템플릿을 발생할 수 있습니다.

예를 들어 다음 코드를 고려합니다.

```cpp
#include <cstdio>

void func(void*) { std::puts("The call resolves to void*") ;}

template<typename T> void g(T x)
{
    func(0);
}

void func(int) { std::puts("The call resolves to int"); }

int main()
{
    g(3.14);
}
```

컴파일하면 **/zc: twophase-**,이 프로그램이 "호출을 int로 해결"을 인쇄 합니다. 아래 규칙 모드로 **생성-**,이 프로그램이 "는 호출은 void *", 두 번째 오버 로드 때문에 인쇄 `func` 컴파일러는 템플릿이 발견 하면 표시 되지 않습니다.

*종속 이름*를 템플릿 매개 변수에 종속 된 이름에는 조회 동작에서 서로 다른 이기도 **/zc: twophase-** 합니다. 준수 모드에서 종속 이름 템플릿 정의 시점 바인딩되지 않습니다. 대신 이러한 이름은 조회할 템플릿이 인스턴스화될 때. 종속 함수 이름 사용 하 여 함수 호출에 대 한 이름은 위와 템플릿 정의에서 호출 시 표시 되는 함수 집합에 바인딩되어 있습니다. 인수 종속 조회의 추가 오버 로드는 템플릿 정의 시점와 템플릿이 인스턴스화될 있는 지점에 추가 됩니다. 2 단계 조회의 두 단계는 템플릿 인스턴스화 시 종속 이름에 대 한 템플릿 정 및 조회의 시간에 종속 되지 않은 이름에 대 한 조회 합니다. 아래 **/zc: twophase-**, 컴파일러에서 일반, 정규화 되지 않은 조회 인수 종속 조회를 별도로 수행 하지는 않습니다 (즉, 일은 2 단계 조회)에 있도록 오버 로드 확인의 결과 다를 수 있습니다.

또 다른 예는 다음과 같습니다.

```cpp
// zctwophase1.cpp
// Compile by using
// cl /EHsc /W4 /permissive- zctwophase1.cpp
// cl /EHsc /W4 /permissive- /Zc:twoPhase- zctwophase1.cpp

#include <cstdio>

void func(long) { std::puts("func(long)"); }

template <typename T> void tfunc(T t) {
    func(t);
}

void func(int) { std::puts("func(int)"); }

namespace NS {
    struct S {};
    void func(S) { std::puts("NS::func(NS::S)"); }
}

int main() {
    tfunc(1729);
    NS::S s;
    tfunc(s);
}
```

사용 하지 않고 컴파일하면 **/zc: twophase-** 를이 출력

```Output
func(long)
NS::func(NS::S)
```

사용 하 여 컴파일하면 **/zc: twophase-** 를이 출력

```Output
func(int)
NS::func(NS::S)
```

아래 규칙 모드에서 **관대 한 /-**, 호출 `tfunc(1729)` 로 확인 되는 `void func(long)` 를 오버 로드 하지 `void func(int)` 아래으로 오버 로드 **/zc: twophase-** 이므로 정규화 되지 않은 `func(int)` 템플릿의 정의 뒤에 선언 되며 인수 종속 조회를 통해 찾을 수 없습니다. 하지만 `void func(S)` 는 호출에 대해 설정 하는 오버 로드를에 추가 됩니다 있도록 인수 종속 조회에 참여 `tfunc(s)` 템플릿 함수 뒤에 선언 된 경우에 합니다.

### <a name="update-your-code-for-two-phase-conformance"></a>2 단계 규칙에 대 한 코드 업데이트

이전 버전의 컴파일러 키워드가 필요 하지 않습니다 `template` 하 고 `typename` everywhere는 C++ 표준 해야 합니다. 이러한 키워드는 컴파일러 종속 이름이 구문 분석 해야 조회의 첫 번째 단계는 방법을 명확 하 게 일부 위치에 필요 합니다. 예를 들어:

`T::Foo<a || b>(c);`

컴파일러 구문 분석 `Foo` 범위의 변수 `T`, 즉이 코드는 논리적-또는 식을 `T::foo < a` 왼쪽 피연산자로 및 `b > (c)` 오른쪽 피연산자로. 사용 하 고 싶으면 `Foo` 함수 템플릿으로 나타내야 추가 하 여 템플릿을 이것이 `template` 키워드:

`T::template Foo<a || b>(c);`

Visual Studio 2017 버전 15.3에서 이전 버전에서는 시점과 **/zc: twophase-** 를 지정 하면 컴파일러가 허용 하지 않고이 코드는 `template` 키워드 의인수를사용하여함수템플릿호출으로해석`a || b`이므로 매우 제한 된 방식으로 템플릿 구문 분석 합니다. 위의 코드 첫 번째 단계에서 전혀 구문 분석 되지 않습니다. 두 번째 단계 컨텍스트가 충분 하 게 `T::Foo` 이므로 변수를 사용 하지 않고 템플릿을 컴파일러 키워드를 적용 하지 않습니다.

키워드를 제거 하 여이 동작을 확인할 수도 있습니다 `typename` 함수 템플릿 본문, 이니셜라이저, 기본 인수 및 noexcept 인수 이름 앞입니다. 예를 들어:

```cpp
template<typename T>
typename T::TYPE func(typename T::TYPE*)
{
    /* typename */ T::TYPE i;
}
```

키워드를 사용 하지 않는 경우 `typename` 함수 본문에서이 코드에서 컴파일합니다 **/zc: twophase-**, 아니라 **/ permissive-** 합니다. 합니다 `typename` 키워드는 나타내는 필요는 `TYPE` 다릅니다. 본문을 구문 분석할 **/zc: twophase-**, 컴파일러 않는 키워드가 필요 합니다. **관대 한 /-** 준수 모드, 없이 코드를 `typename` 키워드 오류를 생성 합니다. Visual Studio 2017 버전 15.3에 코드 마이그레이션 및 그 이후에 삽입 된 `typename` 누락 되는 키워드입니다.

마찬가지로,이 코드 예제를 고려해 야 합니다.

```cpp
template<typename T>
typename T::template X<T>::TYPE func(typename T::TYPE)
{
    typename T::/* template */ X<T>::TYPE i;
}
```

아래 **/zc: twophase-** 하며 이전 컴파일러에서 컴파일러만는 `template` 2 줄에는 키워드입니다. 기본적으로 규칙 모드에서 컴파일러가 이제도 필요 합니다 `template` 키워드를 나타내는 4 줄 `T::X<T>` 템플릿입니다. 이 키워드 없는 코드가 살펴보고 표준에 맞게 코드를 제공 합니다.

규칙과 관련 된 문제에 대 한 자세한 내용은 참조 하세요. [ C++ Visual Studio의 규칙 향상](../../overview/cpp-conformance-improvements.md) 하 고 [비표준 동작](../../cpp/nonstandard-behavior.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 수정 된 **추가 옵션** 포함할 속성을 **/zc: twophase-** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)<br/>
