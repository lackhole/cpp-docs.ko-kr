---
title: 특성C++
ms.date: 05/06/2019
ms.assetid: 748340d9-8abf-4940-b0a0-91b6156a3ff8
ms.openlocfilehash: bc92e5f3e279edc6fbea7f99d52c469f9fdf04f8
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222298"
---
# <a name="attributes-in-c"></a>특성C++

C++ 컴파일러는 표준에 정의 된 특성만 인식 해야 하지만 표준 특성 집합을 정의 및 컴파일러 공급 업체별 네임 스페이스) (내 자체 특성을 정의할 수 있습니다.

경우에 따라 표준 특성 컴파일러 별 declspec 매개 변수를 사용 하 여 겹칩니다. 시각적 개체의 C++를 사용할 수 있습니다는 `[[deprecated]]` 사용 하는 대신 특성 `declspec(deprecated)` 고 특성 모든와 호환 되는 컴파일러에서 인식 됩니다. 모든 다른 declspec 같은 매개 변수에 대해 dllimport 및 dllexport, 아직 없는 특성 해당은 하면 계속 해 서 declspec 구문을 사용 해야 합니다. 특성 형식 시스템에 영향을 주지 않습니다 하 고 해당 프로그램의 의미를 변경 하지 마세요. 컴파일러는 인식할 수 없습니다. 특성 값을 무시 합니다.

**Visual Studio 2017 버전 15.3 이상** (사용할 수 있습니다 [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)): 특성 목록의 범위에서 단일을 사용 하 여 모든 이름에 대 한 네임 스페이스를 지정할 수 있습니다 **를 사용 하 여** 도입자:

```cpp
void g() {
    [[using rpr: kernel, target(cpu,gpu)]] // equivalent to [[ rpr::kernel, rpr::target(cpu,gpu) ]]
    do task();
}
```

## <a name="c-standard-attributes"></a>C++표준 특성

C++11에서는 특성에 주석을 추가 하는 표준화 된 방법을 제공 C++ 공급 업체별 아닐 수 있는 추가 정보 (클래스, 함수, 변수 및 블록에 국한 되지 않음 포함)를 생성 합니다. 정보 메시지를 생성 하거나 특성 사용된 코드를 컴파일할 때 특별 한 논리를 적용 하려면 컴파일러에서이 정보를 사용할 수 있습니다. 컴파일러 즉,이 구문을 사용 하 여 사용자 고유의 사용자 지정 특성을 정의할 수 없습니다는 인식 하지 않는 모든 특성을 무시 합니다. 특성은 대괄호로 double:

```cpp
[[deprecated]]
void Foo(int);
```

특성이 나타내는 대신 #pragma 지시문와 같은 공급 업체별 확장 하는 표준화 된 표현 앞 (Visual C++), 또는 &#95; &#95;특성&#95; &#95; (GNU). 그러나 대부분의 공급 업체별 구문을 사용 하 여 계속 해야 합니다. 현재 표준에는 컴파일러에서 인식 해야 하는 다음 특성을 지정 합니다.

- `[[noreturn]]` 함수를 반환 하지 않습니다; 지정 즉 예외가 항상 throw 됩니다. 컴파일러에 대 한 해당 컴파일 규칙을 조정할 수 `[[noreturn]]` 엔터티.

- `[[carries_dependency]]` 함수는 데이터 종속성 순서 스레드 동기화와 관련 하 여 전파를 지정 합니다. 하나 이상의 매개 변수에 전달 된 인수 전달 함수 본문에 대 한 종속성을 지정 하는 특성을 적용할 수 있습니다. 함수 반환 값 전달 함수의 종속성을 지정 하려면 자체에 특성을 적용할 수 있습니다. 컴파일러가이 정보를 사용 하 여 더 효율적인 코드를 생성할 수 있습니다.

- `[[deprecated]]` **Visual Studio 2015 이상:** 함수는 사용할 수 없습니다 지정 되 고 나중에 라이브러리 인터페이스의 버전 존재 하지 않을 수 있습니다. 컴파일러는 클라이언트 코드에서 함수를 호출 하려고 하면 정보 메시지를 생성 하는 데 사용할 수 있습니다. 클래스, typedef 이름, 변수, 비정적 데이터 멤버, 함수, 네임 스페이스, 열거형, 열거자, 또는 템플릿 특수화의 선언에 적용할 수 있습니다.

- `[[fallthrough]]` **Visual Studio 2017 이상:** (사용할 수 있습니다 [/std: c + + 17](../build/reference/std-specify-language-standard-version.md))는 `[[fallthrough]]` 컨텍스트의 특성을 사용할 수 있습니다 [전환](switch-statement-cpp.md) 컴파일러 (또는 읽는 독자 라면 누구나 힌트로 문 코드)는 fallthrough 동작 합니다. Microsoft C++ 컴파일러 현재 경고 하지 않습니다 fallthrough 동작에 있으므로이 특성에 적용 컴파일러 동작이 없습니다.

- `[[nodiscard]]` **Visual Studio 2017 버전 15.3 이상:** (사용할 수 있습니다 [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)) 지정 하는 함수의 반환 값이 아닙니다 삭제 됩니다. 이 예제에 표시 된 대로, C4834 경고를 발생 시킵니다.

    ```cpp
    [[nodiscard]]
    int foo(int i) { return i * i; }

    int main()
    {
        foo(42); //warning C4834: discarding return value of function with 'nodiscard' attribute
        return 0;
    }
    ```

- `[[maybe_unused]]` **Visual Studio 2017 버전 15.3 이상:** (사용할 수 있습니다 [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)) 변수, 함수, 클래스, typedef, 비정적 데이터 멤버, 열거형 또는 템플릿 특수화 될 수 있습니다 의도적으로 사용 하지 않도록 지정 합니다. 엔터티의 표시 하는 경우 컴파일러에서 경고 하지 않습니다 `[[maybe_unused]]` 사용 되지 않습니다. 특성 없이 선언 된 엔터티의 나중에 다시 선언할 수 특성과 그 반대로 가능 합니다. 엔터티의 표시 표시 된 첫 번째 선언을 분석 한 후 현재 변환 단위 변환의 나머지 부분에 대 한 것으로 간주 됩니다.

## <a name="microsoft-specific-attributes"></a>Microsoft 전용 특성

- `[[gsl::suppress(rules)]]` 이 Microsoft 전용 특성은 적용 되는 검사기에서 발생 한 경고를 표시 하지 않기 위해 사용 [지침 지원 라이브러리 (GSL)](https://github.com/Microsoft/GSL) 코드에는 규칙입니다. 예를 들어이 코드 조각:

    ```cpp
    void main()
    {
        int arr[10]; // GSL warning 26494 will be fired
        int* p = arr; // GSL warning 26485 will be fired
        [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
        {
            int* q = p + 1; // GSL warning 26481 suppressed
            p = q--; // GSL warning 26481 suppressed
        }
    }
    ```

  이 예제에서는 이러한 경고를 발생 시킵니다.

  - 26494 (규칙 5를 입력 합니다. 항상 개체를 초기화 합니다.)

  - 26485 (범위 규칙 3: 없는 배열에서 포인터로 감소 합니다.)

  - 26481 (범위 규칙 1: 포인터 산술 연산을 사용 하지 마세요. 범위 대신 사용 합니다.)

  처음 두 경고 CppCoreCheck 코드 분석 도구를 설치 하 고 활성화를 사용 하 여이 코드를 컴파일할 때 발생 합니다. 하지만 세 번째 경고를 특성으로 인해 발생 하지 않습니다. 특정 규칙 수를 포함 하지 않고 [[gsl::suppress(bounds)]]을 작성 하 여 전체 범위 프로필을 억제할 수 있습니다. C++ Core Guidelines 향상 하 고 안전한 코드를 작성할 수 있도록 설계 됩니다. 표시 안 함 특성 쉽게 필요 하지는 때에 경고를 해제 합니다.