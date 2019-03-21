---
title: Visual Studio의 Visual C++에 대한 새로운 기능
ms.date: 11/15/2017
ms.technology: cpp-ide
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.openlocfilehash: b75a1903b3e0767f8aa009134a2b37a7d1a8e0d0
ms.sourcegitcommit: 9e85c2e029d06b4c1c69837437468718b4d54908
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2019
ms.locfileid: "57810473"
---
# <a name="whats-new-for-visual-c-in-visual-studio-2017"></a>Visual Studio 2017의 Visual C++에 대한 새로운 기능

Visual Studio 2017에는 Visual C++ 환경에 대한 많은 업데이트와 수정이 포함되었습니다. 대부분 **사용자 의견 보내기** 아래의 [문제 보고](/visualstudio/how-to-report-a-problem-with-visual-studio-2017) 및 [제안하기](https://visualstudio.uservoice.com/) 옵션을 통해 고객이 제출한 250개 이상의 버그와 보고된 문제를 해결했습니다. 버그를 알려 주셔서 감사합니다. 모든 Visual Studio의 새로운 기능에 대한 자세한 내용은 [Visual Studio 2017의 새로운 기능](/visualstudio/ide/whats-new-in-visual-studio)을 참조하세요.

<!--The compiler and tools version number in Visual Studio 2017 is 14.10.24629. -->

## <a name="c-compiler"></a>C++ 컴파일러

### <a name="c-conformance-improvements"></a>C++ 규칙 향상

이 릴리스에서는 C++ 컴파일러 및 표준 라이브러리를 C++11 및 C++14 기능에 대한 강화된 지원 기능과, C++17 표준에서 선보일 것으로 예상되는 특정 기능에 대한 임시 지원 기능으로 업데이트했습니다. 자세한 내용은 [Visual Studio 2017의 C++ 규칙 향상](cpp-conformance-improvements-2017.md)을 참조하세요.

**Visual Studio 2017 버전 15.5**: 컴파일러는 구조적 바인딩, `constexpr` 람다, `if constexpr`, 인라인 변수, fold 식 및 형식 시스템에 `noexcept` 추가 등 C++17에 새롭게 추가된 기능의 약 75%를 지원합니다. 이는 **/std:c++17** 옵션하에서 사용할 수 있습니다. 자세한 내용은 [Visual Studio 2017의 C++ 규칙 향상](cpp-conformance-improvements-2017.md)을 참조하세요.

**Visual Studio 2017 버전 15.7**: Visual Studio 버전 15.7의 MSVC 컴파일러 도구 집합은 이제 C++ 표준을 준수합니다. 자세한 내용은 [알림: MSVC의 C++ 표준 준수](https://blogs.msdn.microsoft.com/vcblog/2018/05/07/announcing-msvc-conforms-to-the-c-standard/) 및 [Visual C++ 언어 규칙](visual-cpp-language-conformance.md)을 참조하세요.

### <a name="new-compiler-options"></a>새로운 컴파일러 옵션

- [/permissive-](build/reference/permissive-standards-conformance.md): 모든 엄격한 표준 준수 컴파일러 옵션을 사용하고 대부분의 Microsoft 전용 컴파일러 확장(예: `__declspec(dllimport)` 제외)을 사용하지 않도록 설정합니다. 이 옵션은 Visual Studio 2017 버전 15.5에서 기본적으로 켜져 있습니다.  **/permissive-** conformance 모드에는 2단계 이름 조회에 대한 지원이 포함됩니다. 자세한 내용은 [Visual Studio 2017의 C++ 규칙 향상](cpp-conformance-improvements-2017.md)을 참조하세요.

- [/diagnostics](build/reference/diagnostics-compiler-diagnostic-options.md): 줄 번호, 줄 번호 및 열 또는 줄 번호 및 열과 진단 오류 또는 경고가 발견된 코드 줄 아래의 캐럿을 표시할 수 있습니다.

- [/debug:fastlink](build/reference/debug-generate-debug-info.md): 일부 디버그 정보를 PDB 파일에 복사하지 않음으로써 최대 30%까지 빠른 증분 연결 시간(Visual Studio 2015 대비)을 사용합니다. 대신, PDB 파일은 실행 파일을 만드는 데 사용된 개체 및 라이브러리 파일에 대한 디버그 정보를 가리킵니다. [Faster C++ build cycle in VS "15" with /Debug:fastlink](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/faster-c-build-cycle-in-vs-15-with-debugfastlink/)(/Debug:fastlink를 사용하는 VS "15"의 더 빠른 C++ 빌드 주기) 및 [Recommendations to speed C++ builds in Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2016/10/26/recommendations-to-speed-c-builds-in-visual-studio/)(Visual Studio에서 C++ 빌드 속도를 향상하기 위한 권장 사항)를 참조하세요.

- Visual Studio 2017에서는 [/sdl](build/reference/sdl-enable-additional-security-checks.md)과 함께 [/await](build/reference/await-enable-coroutine-support.md)를 사용할 수 있습니다. 코루틴에서 [/RTC](build/reference/rtc-run-time-error-checks.md) 제한이 제거되었습니다.

   **Visual Studio 2017 버전 15.3**:

- [/std:c++14 및 /std:c++latest](build/reference/std-specify-language-standard-version.md): 이러한 컴파일러 옵션을 사용하면 프로젝트에서 특정 버전의 ISO C++ 프로그래밍 언어를 옵트인할 수 있습니다. **/std:c++latest** 옵션은 대부분의 새 초안 표준 기능을 보호합니다.

- [/std:c++17](build/reference/std-specify-language-standard-version.md)을 사용하면 컴파일러에서 구현된 일련의 C++17 기능을 사용할 수 있습니다. 이 옵션에서는 C++17 이후의 C++표준 규격 초안(Working Draft) 및 결함 업데이트의 전에서 변경되거나 새로운 기능에 대한 컴파일러 및 표준 라이브러리 지원을 사용하지 않습니다. 이러한 기능을 사용하려면 **/std:c++latest**를 사용하세요.

### <a name="codegen-security-diagnostics-and-versioning"></a>Codegen, 보안, 진단 및 버전 관리

이 릴리스에서는 최적화, 코드 생성, 도구 집합 버전 관리 및 진단의 몇 가지 기능이 향상되었습니다. 특히 주목할 만한 기능 향상은 다음과 같습니다.

- 루프의 향상된 코드 생성: 상수 정수 나누기의 자동 벡터화를 지원하며, memset 패턴 식별 기능이 향상되었습니다.
- 코드 보안 개선: 버퍼 오버런 컴파일러 진단의 내보내기가 개선되었으며, 이제는 [/guard:cf](build/reference/guard-enable-control-flow-guard.md)가 점프 테이블을 생성하는 스위치 문을 보호합니다.
- 버전 관리: 기본 제공 전처리기 매크로 **\_MSC\_VER**의 값이 이제 Visual C++ 도구 세트 업데이트 시마다 일정하게 업데이트됩니다. 자세한 내용은 [Visual C++ Compiler Version](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/visual-c-compiler-version/)(Visual C++ 컴파일러 버전)을 참조하세요.
- 새 도구 세트 레이아웃: 개발 머신에서 컴파일러 및 관련된 빌드 도구의 위치 및 디렉터리 구조가 변경되었습니다. 새 레이아웃을 사용하면 여러 버전의 컴파일러를 병렬 설치할 수 있습니다. 자세한 내용은 [Compiler Tools Layout in Visual Studio "15"](https://blogs.msdn.microsoft.com/vcblog/2016/10/07/compiler-tools-layout-in-visual-studio-15/)(Visual Studio "15"의 컴파일러 도구 레이아웃)를 참조하세요.
- 향상된 진단: 이제 출력 창에 오류가 발생하는 열이 표시됩니다. 자세한 내용은 [C++ compiler diagnostics improvements in VS "15" Preview 5](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-compiler-diagnostics-improvements-in-vs-15-rc/)(VS "15" Preview 5의 C++ 컴파일러 진단 향상)를 참조하세요.
- 코루틴을 사용하는 경우 실험적인 **yield**(**/await** 옵션 아래에서 사용 가능) 키워드가 제거되었습니다. 대신 `co_yield`를 사용하도록 코드를 업데이트해야 합니다. 자세한 내용은 [Visual C++ 팀 블로그](https://blogs.msdn.microsoft.com/vcblog/)를 참조하세요.

**Visual Studio 2017 버전 15.3**:

컴파일러에서 향상된 진단 추가 기능이 있습니다. 자세한 내용은 [Visual Studio 2017 15.3.0에서 향상된 진단 기능(영문)](https://blogs.msdn.microsoft.com/vcblog/2017/07/21/diagnostic-improvements-in-vs2017-15-3-0/)을 참조하세요.

**Visual Studio 2017 버전 15.5**:

생성된 코드의 품질 향상으로 인해 Visual C++ 런타임 성능은 계속 개선되고 있습니다. 즉, 사용자 코드를 단순히 다시 컴파일하기만 하면 앱이 보다 빠르게 실행됩니다. 컴파일러 최적화 기능 중에는 조건부 스칼라 저장소의 벡터화, 호출 `sin(x)` 및 `cos(x)`를 새로운 `sincos(x)`로 결합, SSA 최적화 프로그램을 통한 중복 명령 제거와 같이 완전히 새로운 기능이 있습니다. 다른 컴파일러 최적화 기능으로는 조건식의 벡터화 도우미 추론, 더 나은 루프 최적화 및 부동 최소/최대 codegen과 같은 기존 기능에 대한 개선 사항이 있습니다. 링커에는 링크 시간 속도를 최대 9% 개선할 수 있는 새롭고 더욱 빠른 **/OPT:ICF** 구현이 있고, 증분 링크에는 다른 성능 개선 사항이 있습니다. 자세한 내용은 [/OPT(최적화)](build/reference/opt-optimizations.md) 및 [/INCREMENTAL(증분 링크)](build/reference/incremental-link-incrementally.md)을 참조하세요.

Visual C++는 AVX-512의 새로운 기능을 128비트 및 256비트 차원의 레지스터에 가져오는 벡터 길이 명령을 포함하는 Intel의 AVX-512를 지원합니다.

전체적으로 C++17 모드를 사용 중일 때 [/Zc:noexceptTypes-](build/reference/zc-noexcepttypes.md) 옵션을 사용하여 `noexcept`의 C++14 버전으로 되돌릴 수 있습니다. 이렇게 하면 모든 `throw()` 코드를 동시에 다시 작성할 필요 없이 C++17에 부합하도록 소스 코드를 업데이트할 수 있습니다. 자세한 내용은 [동적 예외 사양 제거 및 noexcept](cpp-conformance-improvements-2017.md#noexcept_removal)를 참조하세요.

**Visual Studio 2017 버전 15.7**:

- 새로운 컴파일러 스위치 [/Qspectre](build/reference/qspectre.md)는 위험한 실행 부채널 공격을 완화하는 데 도움이 됩니다. 자세한 내용은 [MSVC의 스펙터 완화](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc/)를 참조하세요.
- 스펙터 완화를 위해 새로운 진단 경고입니다. 자세한 내용은 [Visual Studio 2017 버전 15.7 Preview 4의 스펙터 진단](https://blogs.msdn.microsoft.com/vcblog/2018/04/20/spectre-diagnostic-in-visual-studio-2017-version-15-7-preview-4/)을 참조하세요.
- /Zc, **/Zc:__cplusplus**의 새 값을 사용하면 C++ 표준 지원에 대한 올바른 보고가 가능합니다. 예를 들어, 스위치가 설정되고 컴파일러가 /std:c++17 모드인 경우 값은 **201703L**로 확장됩니다. 자세한 내용은 [MSVC가 이제 __cplusplus를 올바르게 보고](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/msvc-now-correctly-reports-__cplusplus/)를 참조하세요.

## <a name="c-standard-library-improvements"></a>C++ 표준 라이브러리 향상

- 사소한 `basic_string` `_ITERATOR_DEBUG_LEVEL != 0` 진단 기능 개선. 문자열 조직에서 IDL 검사를 트립할 경우 그 트립이 일어나게 된 특정 동작이 보고됩니다. 예를 들어 "문자열 반복기를 역참조할 수 없음" 대신에 "범위(예: 끝 반복기) 밖에 있기 때문에 문자열 반복기를 역참조할 수 없음”이라는 메시지가 나타납니다.
- 성능 향상: `basic_string::find(char)` 오버로드가 `traits::find`를 한 번만 호출하도록 만들었습니다. 이전에 이 오버로드는 길이가 1인 문자열을 대상으로 한 일반 문자열 검색으로 구현되었습니다.
- 성능 향상: `basic_string::operator==`가 이제 문자열 내용을 비교하기 전에 문자열 크기를 확인합니다.
- 성능 향상: `basic_string`에서 컴파일러 최적화 프로그램의 분석 작업을 어렵게 한 컨트롤 결합을 제거했습니다. 그래도 짧은 문자열을 대상으로 `reserve`를 호출할 때 아무 작업도 하지 않도록 하는 데 비용이 듭니다.
- \<any\>, \<string_view\>, `apply()`, `make_from_tuple()`을 추가했습니다.
- `std::vector`가 정확성과 성능에서 철저히 점검되었습니다. 이제 삽입 및 대입 작업에서 앨리어싱이 표준에서 요구하는 대로 올바르게 처리되고, 강한 예외 보장이 표준에 따라 요구되면 `move_if_noexcept()` 및 기타 논리를 통해 제공되며, 삽입/대입의 항목 작업 개수가 줄어들었습니다.
- 이제 C++ 표준 라이브러리가 가상의 null 포인터를 역참조하지 못하도록 방지합니다.
- \<optional\>, \<variant\>, `shared_ptr::weak_type` 및 \<cstdalign\>을 추가했습니다.
- `min(initializer_list)`, `max(initializer_list)`, `minmax(initializer_list)`, `min_element()`, `max_element()`, `minmax_element()`에서 C++14 `constexpr`을 사용하도록 설정했습니다.
- `weak_ptr::lock()` 성능이 향상되었습니다.
- 이전에 코드가 영원히 잠기는 문제가 발생하던 `std::promise` 이동 할당 연산자가 해결되었습니다.
- `atomic<T*>`를 `T*`로 암시적으로 변환할 때 발생하는 컴파일러 오류를 해결했습니다.
- `pointer_traits<Ptr>`가 이제 `Ptr::rebind<U>`를 올바르게 검색합니다.
- `move_iterator` 빼기 연산자에서 누락된 `const` 한정자를 수정했습니다.
- `propagate_on_container_copy_assignment` 및 `propagate_on_container_move_assignment`를 요청하는 상태 저장 사용자 정의 할당자의 silent bad codegen을 수정했습니다.
- `atomic<T>`가 이제 오버로드된 `operator&()`를 허용합니다.
- 컴파일러 처리량을 늘리기 위해 이제 C++ 표준 라이브러리 헤더는 불필요한 컴파일러 내장 함수에 대한 선언을 포함하지 않습니다.
- 잘못된 `bind()` 호출에 대한 컴파일러 진단이 약간 개선되었습니다.
- `std::string` 및 `std::wstring` 이동 생성자 성능이 3배 넘게 향상되었습니다.

향상된 표준 라이브러리 기능에 대한 전체 목록은 [VS 2017 RTM의 표준 라이브러리 수정(영문)](https://blogs.msdn.microsoft.com/vcblog/2017/02/06/stl-fixes-in-vs-2017-rtm/)을 참조하세요.

### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 15.3 버전

#### <a name="c17-features"></a>C++17 기능

몇 가지 C++17 추가 기능이 구현되었습니다. 자세한 내용은 [Visual C++ 언어 규칙](cpp-conformance-improvements-2017.md#improvements_153)을 참조하세요.

#### <a name="other-new-features"></a>기타 새로운 기능

- 구현된 P0602R0 "variant 및 optional에서 복사/이동 사소성(triviality)을 전파해야 합니다".
- 표준 라이브러리에서는 이제 비활성화되는 동적 RTTI를 [/GR-](build/reference/gr-enable-run-time-type-information.md) 옵션을 통해 공식적으로 허용합니다. `dynamic_pointer_cast()` 및 `rethrow_if_nested()`는 둘 다 기본적으로 `dynamic_cast`가 필요하므로 표준 라이브러리에서 이제 **/GR-** 아래에 `=delete`로 표시됩니다.
- 동적 RTTI가 **/GR-** 를 통해 비활성화된 경우에도 "정적 RTTI"(`typeid(SomeType)` 형식)를 계속 사용할 수 있으며, 몇 가지 표준 라이브러리 구성 요소를 제공합니다. 이제 표준 라이브러리에서는 **/D\_HAS\_STATIC\_RTTI=0**을 통해 정적 RTTI를 비활성화할 수 있습니다. 따라서 `std::function`의 `std::any`, `target()` 및 `target_type()` 멤버 함수와 `std::shared_ptr` 및 `std::weak_ptr`의 `get_deleter()` friend 멤버 함수가 비활성화됩니다.

#### <a name="correctness-fixes-in-visual-studio-2017-version-153"></a>Visual Studio 2017 버전 15.3의 정확성 수정

- 표준 라이브러리 컨테이너는 이제 `max_size()`를 `size_type`의 `max()`가 아닌 `numeric_limits<difference_type>::max()`로 제한합니다. 이렇게 하면 결과 해당 컨테이너의 반복기에 대한 `distance()` 결과를 `distance()`의 반환 형식으로 나타낼 수 있습니다.
- 누락된 `auto_ptr<void>` 전문화가 수정되었습니다.
- 이전에는 length 인수가 정수 형식이 아닌 경우 `for_each_n()`, `generate_n()` 및 `search_n()` 알고리즘을 컴파일하지 못했습니다. 이제는 정수 형식이 아닌 길이를 반복기의 `difference_type`으로 변환하려고 시도합니다.
- `normal_distribution<float>`는 더 이상 double에서 float로 좁히는 것에 대한 표준 라이브러리 내부 경고를 내보내지 않습니다.
- 최대 크기 오버플로를 확인할 때 `basic_string` 대신 `npos`와 비교되는 일부 `max_size()` 연산이 수정되었습니다.
- `condition_variable::wait_for(lock, relative_time, predicate)`는 잘못된 절전 모드 해제 시 전체 상대 시간 동안 대기합니다. 이제는 상대 시간의 단일 간격 동안만 대기합니다.
- `future::get()`은 표준에 필요한 만큼 `future`를 무효화합니다.
- `iterator_traits<void *>`는 `void&`를 형성하려고 시도했기 때문에 하드 오류였습니다. 이제는 "is iterator" SFINAE 조건에서 `iterator_traits`를 사용할 수 있도록 완전하게 빈 구조체가 됩니다.
- Clang **-Wsystem-headers**에서 보고된 일부 경고가 수정되었습니다.
- Clang **-Wmicrosoft-exception-spec**에서 보고된 "선언의 예외 사양이 이전 선언과 일치하지 않습니다."도 수정되었습니다.
- Clang과 C1XX에서 보고된 mem-initializer-list 순서 지정 경고도 수정되었습니다.
- 순서가 지정되지 않은 컨테이너는 컨테이너 자체가 교체될 때 해셔 또는 조건자를 교환하지 않았습니다. 이제는 교환합니다.
- 표준 라이브러리에서 non-`propagate_on_container_swap`(정의되지 않은 non-equal-allocator 동작 조건)을 검색하면 예외를 throw하지 않으므로 이제는 많은 컨테이너 교환 작업이 `noexcept`로 표시됩니다.
- 많은 `vector<bool>` 연산이 이제 `noexcept`로 표시됩니다.
- 표준 라이브러리에서는 이제 옵트아웃 이스케이프 해치와 일치하는 `value_type` 할당자(C++17 모드에서)를 적용합니다.
- `basic_string`에 대한 self-range-insert에서 문자열의 내용이 뒤섞이는 일부 조건이 수정되었습니다. (참고: 벡터에 대한 self-range-insert는 여전히 표준 라이브러리에서 금지됩니다.)
- `basic_string::shrink_to_fit()`는 더 이상 할당자 `propagate_on_container_swap`의 영향을 받지 않습니다.
- `std::decay`는 이제 끔찍한 함수 형식, 즉 cv-qualified 및/또는 ref-qualified인 함수 형식을 처리합니다.
- include 지시문에서 적절한 대/소문자 구분과 슬래시를 사용하도록 변경하여 이식성이 향상되었습니다.
- 경고 C4061 "열거형 '*enumeration*'의 switch에 있는 '*enumerator*' 열거자는 case 레이블에 의해 명시적으로 처리되지 않습니다."가 수정되었습니다. 경고는 기본적으로 사용하지 않도록 설정되어 있으며, 표준 라이브러리의 일반 경고 정책의 예외로 수정되었습니다. (표준 라이브러리는 **/W4** 정리이지만 **/Wall** 정리가 되려고 시도하지는 않습니다. 기본적으로 사용되지 않는 대부분의 경고는 매우 시끄럽고, 정기적으로 사용하기 위한 것이 아닙니다.)
- `std::list` 디버그 검사가 향상되었습니다. 이제는 목록 반복기에서 `operator->()`를 검사하고, `list::unique()`에서는 반복기를 무효화된(invalidated) 것으로 표시합니다.
- `tuple`의 use-allocator 메타 프로그래밍이 수정되었습니다.

#### <a name="performancethroughput-fixes"></a>성능/처리량 수정

- SEH(구조적 예외 처리)를 사용하는 함수로 `std::atomic`의 구현을 인라인하지 못하게 했던 `noexcept`와의 상호 작용이 해결되었습니다.
- 표준 라이브러리의 내부 `_Deallocate()` 함수가 더 작은 코드로 최적화하여 더 많은 위치로 인라인될 수 있도록 변경되었습니다.
- 재귀 대신 팩 확장을 사용하도록 `std::try_lock()`이 변경되었습니다.
- 모든 잠금의 `std::lock()`에서 회전하는 대신 `lock()` 연산을 사용하도록 `try_lock()` 교착 상태 방지 알고리즘이 향상되었습니다.
- `system_category::message()`에서 명명된 반환 값 최적화가 활성화되었습니다.
- `conjunction` 및 `disjunction`은 이제 2N + 2 형식 대신 N + 1 형식을 인스턴스화합니다.
- `std::function`에서는 `std::function`으로 많은 고유 람다를 전달하는 프로그램에서 처리량을 향상시키고 obj 크기를 줄임으로써 더 이상 각 type-erased 호출 가능 코드에 대한 할당자 지원 기계를 인스턴스화하지 않습니다.
- `allocator_traits<std::allocator>`에는 `std::allocator`부터 `allocator_traits`까지만 상호 작용하는 코드에서(즉, 대부분의 코드에서) 코드 크기를 줄이는, 수동으로 인라인된 `std::allocator` 연산이 포함됩니다.
- C++11 최소 할당자 인터페이스는 이제 `_Wrap_alloc` 내부 클래스에 할당자를 래핑하는 대신 `allocator_traits`를 직접 호출하는 표준 라이브러리에서 처리됩니다. 이렇게 하면 할당자 지원을 위해 생성되는 코드의 크기를 줄이고, 경우에 따라 표준 라이브러리 컨테이너에 대해 추론할 수 있는 최적화 프로그램의 기능이 향상되고, 더 효율적인 디버깅 환경을 제공합니다(이제는 디버거에서 `_Wrap_alloc<your_allocator_type>` 대신 할당자 유형이 표시되기 때문임).
- 할당자를 실제로 사용자 지정할 수 없는 사용자 지정 `allocator::reference`에 대한 메타 프로그래밍이 제거되었습니다. (할당자는 컨테이너에서 고급 참조가 아니라 고급 포인터를 사용하도록 만들 수 있습니다.)
- 컴파일러 프런트 엔드에서 범위 기반 for 루프의 디버그 반복기를 래핑하지 않도록 지시하여 디버그 빌드의 성능이 향상되었습니다.
- `shrink_to_fit()` 및 `reserve()`에 대한 `basic_string`의 내부 축소 경로는 더 이상 재할당 작업의 경로에 있지 않으므로 모든 변경 멤버에 대한 코드 크기가 줄어듭니다.
- `basic_string` 내부 증가 경로가 더 이상 `shrink_to_fit()` 경로에 없습니다.
- `basic_string`의 변경 작업은 이제 할당되지 않은 빠른 경로와 할당된 느린 경로 함수에 팩터링되어 기능이 할당되므로 일반적인 재할당되지 않은 case가 호출자에 인라인될 가능성이 높아집니다.
- `basic_string`의 변형 작업은 이제 크기를 조정하는 대신 원하는 상태로 재할당된 버퍼를 구성합니다. 예를 들어 문자열의 시작에 삽입하면 이제는 재할당될 case에 두 번(새로 할당된 버퍼로, 그 다음에 아래로) 삽입하는 것이 아니라 정확히 한 번만(아래로 또는 새로 할당된 버퍼로) 삽입한 후의 내용을 이동합니다.
- \<string\>에서 C 표준 라이브러리를 호출하는 작업은 이제 `errno`의 주소를 캐시하여 TLS와의 반복된 상호 작용을 제거합니다.
- `is_pointer` 구현이 간소화되었습니다.
- 함수 기반 식 SFINAE가 `struct` 및 `void_t` 기반으로 변경되었습니다.
- 표준 라이브러리 알고리즘은 이제 반복기의 후위 증가 연산(postincrement)을 방지합니다.
- 64비트 시스템에서 32비트 할당자를 사용할 때의 잘림 경고가 수정되었습니다.
- 이제는 가능한 경우 버퍼를 다시 사용하여 비POCMA non-equal-allocator case에서 `std::vector` 이동 할당이 더 효율적입니다.

#### <a name="readability-and-other-improvements"></a>가독성 및 기타 향상된 기능

- 표준 라이브러리에서는 이제 조건부로 정의된 매크로 대신 C++14 `constexpr`을 무조건부로 사용합니다.
- 표준 라이브러리에서는 이제 별칭 템플릿을 내부적으로 사용합니다.
- 표준 라이브러리에서는 이제 `nullptr_t{}` 대신에 `nullptr`을 내부적으로 사용합니다. (NULL의 내부 사용은 완전히 금지되었습니다. 0-as-null의 내부 사용은 점차적으로 정리되고 있습니다.)
- 표준 라이브러리에서는 이제 문체론적으로 `std::forward()`를 오용하는 대신 `std::move()`를 내부적으로 사용합니다.
- `static_assert(false, "message")`을(를) `#error message`(으)로 변경했습니다. 이렇게 하면 `#error`에서 컴파일을 즉시 중단하기 때문에 컴파일러 진단이 향상됩니다.
- 표준 라이브러리에서는 더 이상 함수를 `__declspec(dllimport)`로 표시하지 않습니다. 최신 링커 기술에는 이 선언자가 더 이상 필요하지 않습니다.
- SFINAE가 기본 템플릿 인수로 추출되어 반환 형식 및 함수 인수 형식에 비해 간단하게 표시됩니다.
- \<random\>의 디버그 검사에서는 이제 `fputs()`를 **stderr**로 호출한 _Rng_abort() 내부 함수 `_Rng_abort()` 대신 표준 라이브러리의 일반적인 기계를 사용합니다. 이 함수의 구현은 이진 방식 호환성을 위해 유지되지만, 표준 라이브러리의 이진 방식으로 호환되지 않는 다음 버전에서 제거되었습니다.

### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 15.5 버전

C++17 표준에 따라 몇 가지 표준 라이브러리 기능이 추가 또는 제거되거나 더 이상 사용되지 않게 되었습니다. 자세한 내용은 [Visual Studio의 C++ 규칙 향상](cpp-conformance-improvements-2017.md#improvements_155)을 참조하세요.

#### <a name="new-experimental-features"></a>새로운 실험적 기능

- 다음과 같은 병렬 알고리즘에 대 한 실험적 지원:
  - `all_of`
  - `any_of`
  - `for_each`
  - `for_each_n`
  - `none_of`
  - `reduce`
  - `replace`
  - `replace_if`
  - `sort`
- 다음과 같은 병렬 알고리즘에 대한 서명이 추가되었지만 현재는 병렬화되어 있지 않으므로 요소를 이동하거나 변경하기만 하는 병렬화 알고리즘에서는 아무 유익이 없는 것으로 나타났습니다.
  - `copy`
  - `copy_n`
  - `fill`
  - `fill_n`
  - `move`
  - `reverse`
  - `reverse_copy`
  - `rotate`
  - `rotate_copy`
  - `swap_ranges`

#### <a name="performance-fixes-and-improvements"></a>성능 수정 및 개선 사항

- `basic_string<char16_t>`에서는 이제 `basic_string<wchar_t>`이 참여하는 유사한 최적화 및 동일한 `memcmp`, `memcpy`에 참여합니다.
- 함수 포인터가 Visual Studio 2015 업데이트 3의 "함수 복사 방지" 작업으로 인해 인라인되고 노출되지 않도록 방지하는 최적화 제한 문제가 해결되어 `lower_bound(iter, iter, function pointer)`의 성능이 복원되었습니다.
- 순서 확인 전 반복기의 래핑을 해제하여 반복기 디버깅의 `includes`, `set_difference`, `set_symmetric_difference` 및 `set_union` 입력 순서 확인 오버헤드를 줄였습니다.
- 이제 `std::inplace_merge`는 이미 제자리에 있는 요소를 건너뜁니다.
- `std::random_device`를 생성해도 더 이상 `std::string`이 생성된 후 파괴되지 않습니다.
- `std::equal`과 `std::partition`에는 점프 스레딩 최적화 전달이 있어 반복기 비교가 필요 없습니다.
- `std::reverse`가 일반적으로 복사 가능한 `T`에 포인터를 전달받으면 이제 직접 작성한 벡터화된 구현으로 디스패치합니다.
- `std::fill`, `std::equal` 및 `std::lexicographical_compare`은(는) `std::byte` 및 `gsl::byte`(및 기타 char과 유사한 열거형 및 열거형 클래스)의 `memset` 및 `memcmp`(으)로 디스패치하는 방법을 지시받았습니다. `std::copy`은(는) `is_trivially_copyable`을(를) 사용하여 디스패치하므로 변경이 필요하지 않았습니다.
- 표준 라이브러리는 더 이상 형식을 non-trivially-destructible로 만드는 동작만 수행하는 empty-braces 소멸자를 포함하지 않습니다.

#### <a name="correctness-fixes-in-visual-studio-2017-version-155"></a>Visual Studio 2017 버전 15.5의 정확성 수정

- `std::partition`은 이제 표준의 요구 사항에 따라 조건자를 N + 1회 대신 N회 호출합니다.
- 버전 15.3에서 매직 정적 이름을 방지하려는 시도가 버전 15.5에서 복구되었습니다.
- `std::atomic<T>`는 더 이상 `T`를 구성 가능한 기본값으로 요구하지 않습니다.
- 로그 시간을 사용하는 힙 알고리즘은 반복기 디버깅이 활성화되었을 때 사실상 입력이 힙인 선형 시간 어설션을 더 이상 수행하지 않습니다.
- `__declspec(allocator)`는 이제 이러한 declspec를 인식하지 않는 Clang의 경고를 차단하기 위해 C1XX에서만 보호됩니다.
- `basic_string::npos`는 이제 컴파일 시간 상수로 사용할 수 있습니다.
- C++17 모드에서 `std::allocator`는 이제 alignment가 `max_align_t`보다 큰 over-aligned types - types 할당을 올바르게 처리합니다(**/Zc:alignedNew-** 로 비활성화되지 않은 경우에 한함).  예를 들어 16 또는 32바이트 맞춤이 있는 개체의 벡터는 이제 SSE 및 AVX 명령에 맞게 올바르게 맞춰집니다.

### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 버전 15.6

- \<memory_resource>
- 라이브러리 기본 사항 V1
- polymorphic_allocator 할당 삭제
- 클래스 템플릿 인수 추론 향상

### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 버전 15.7

- 병렬 알고리즘 지원은 더 이상 실험이 아님
- \<filesystem>의 새로운 구현
- 기본 문자열 변환(부분)
- std::launder()
- std::byte
- hypot(x,y,z)
- 불필요한 decay 방지
- 수학 특수 함수
- constexpr char_traits
- STL에 대한 추론 가이드

자세한 내용은 [Visual C++ 언어 규칙](visual-cpp-language-conformance.md)을 참조하세요.

## <a name="other-libraries"></a>기타 라이브러리

### <a name="open-source-library-support"></a>오픈 소스 라이브러리 지원

**vcpkg**는 오픈 소스 명령줄 도구로, Visual Studio에서 오픈 소스 C++ 정적 라이브러리와 DLL을 얻고 빌드하는 프로세스를 훨씬 간소화합니다. 자세한 내용은 [vcpkg: C++용 패키지 관리자](vcpkg.md)를 참조하세요.

**Visual Studio 2017 버전 15.5**:

### <a name="cpprest-sdk-290"></a>CPPRest SDK 2.9.0

C++용 플랫폼 간 웹 API인 CPPRestSDK가 버전 2.9.0으로 업데이트되었습니다. 자세한 내용은 [CppRestSDK 2.9.0 is available on GitHub](https://blogs.msdn.microsoft.com/vcblog/2016/10/21/cpprestsdk-2-9-0-is-available-on-github/)(GitHub에서 CppRestSDK 2.9.0을 사용할 수 있음)를 참조하세요.

### <a name="atl"></a>ATL

- 이름 조회 규칙의 다른 설정 수정
- 기존 이동 생성자 및 이동 할당 연산자가 이제 throw되지 않음으로 제대로 표시됨
- atlstr.h에서 지역 정적 변수의 스레드 안전 초기화에 대한 올바른 경고 C4640 표시
- [ATL 사용 및 DLL 빌드] 시 XP 도구 집합에서 지역 정적의 스레드 안전 초기화가 자동으로 꺼집니다. 물론 이에 해당하는 경우는 더 이상 없습니다. 스레드 안전 초기화 해제를 원하는 경우 프로젝트 설정에 **/Zc:threadSafeInit-** 을 추가할 수 있습니다.

### <a name="visual-c-runtime"></a>Visual C++ 런타임

- 제어 흐름 보호 기호에 대한 새 헤더 "cfguard.h".

## <a name="c-ide"></a>C++ IDE

- 이제 구성 변경 성능이 C++ 네이티브 프로젝트의 경우 향상되었고, C++/CLI 프로젝트의 경우 훨씬 더 향상되었습니다. 이제 처음으로 활성화될 때 솔루션 구성이 더 빠르고, 이 솔루션 구성의 모든 후속 활성화는 거의 즉시 이루어집니다.

**Visual Studio 2017 버전 15.3**:

- 여러 가지 프로젝트 및 코드 마법사가 시그니처 대화 상자 스타일로 다시 작성되었습니다.
- 이제 **클래스 추가**를 선택하면 [클래스 추가] 마법사가 직접 시작됩니다. 이전에 여기에 있던 다른 모든 항목은 이제 **추가 > 새 항목**에서 사용할 수 있습니다.
- Win32 프로젝트는 이제 **새 프로젝트** 대화 상자의 **Windows 데스크톱** 범주 아래에 있습니다.
- 이제 **Windows 콘솔** 및 **데스크톱 애플리케이션** 템플릿은 마법사를 표시하지 않고 프로젝트를 만듭니다. 이전의 **Win32 콘솔 애플리케이션** 마법사와 같은 옵션을 표시하는 동일한 범주 아래에는 새로운 **Windows 데스크톱 마법사**가 있습니다.

**Visual Studio 2017 버전 15.5**:

리팩터링 및 코드 탐색에 IntelliSense 엔진을 사용하는 일부 C++ 작업은 훨씬 더 빨리 실행됩니다. 다음 값은 3500개 프로젝트가 있는 Visual Studio Chromium 솔루션을 기준으로 합니다.

|||
|-|-|
|기능|성능 향상|
|이름 바꾸기|5.3배|
|시그니처 변경 |4.5배|
|모든 참조 찾기|4.7배|

C++는 이제 Ctrl+Click **Go To Definition**을 지원하여 정의에 대한 마우스 탐색을 쉽게 해줍니다. Productivity Power Tools 팩의 구조 시각화 도우미도 이제 제품에 기본적으로 포함됩니다.

## <a name="intellisense"></a>IntelliSense

- 이제 새 SQLite 기반 데이터베이스 엔진이 기본적으로 사용됩니다. 이 엔진은 **정의로 이동(Go To Definitions)**, **모든 참조 찾기(Find All References)** 같은 데이터베이스 작업의 속도를 높이고 초기 솔루션 구문 분석 시간을 크게 개선합니다. 해당 설정이 **도구 > 옵션 > 텍스트 편집기 > C/C++ > 고급**(이전에는 ...C/C++ | 실험적에 있었음)으로 이동되었습니다.

- 미리 컴파일된 헤더를 사용하지 않는 프로젝트 및 파일에 대한 IntelliSense 성능이 향상되었습니다. 현재 파일의 헤더에 대해 자동 미리 컴파일된 헤더가 생성됩니다.

- IntelliSense 오류에 대한 오류 필터링 및 도움말이 오류 목록에 추가되었습니다. 이제 오류 열을 클릭하여 필터링할 수 있습니다. 또한 특정 오류를 클릭하거나 F1 키를 누르면 오류 메시지에 대한 온라인 검색이 시작됩니다.

  ![오류 목록](media/ErrorList1.png "오류 목록")

  ![오류 목록 필터링](media/ErrorList2.png "오류 목록 필터링")

- 멤버 목록 항목을 종류별로 필터링하는 기능이 추가되었습니다.

  ![멤버 목록 필터링](media/mlfiltering.png "멤버 목록 필터링")

- 멤버 목록에 나타나는 항목의 컨텍스트 인식 필터링을 제공하는 새로운 실험 예측 IntelliSense 기능이 추가되었습니다. [C++ IntelliSense Improvements – Predictive IntelliSense & Filtering](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-intellisense-improvements-predictive-intellisense-filtering/)(C++ IntelliSense 향상 – 예측 IntelliSense 및 필터링)을 참조하세요.
- 이제 **모든 참조 찾기**(Shift+F12)를 사용하여 복잡한 코드베이스에서도 쉽게 탐색할 수 있습니다. 고급 그룹화, 필터링, 정렬, 결과 내 검색 및 (일부 언어의 경우) 색 지정이 제공되므로 참조를 명확하게 이해할 수 있습니다. C++의 경우 새로운 UI에 변수에서 읽고 있는지 아니면 변수에 쓰고 있는지에 대한 정보가 포함되어 있습니다.
- IntelliSense 점-화살표 기능이 실험적에서 고급으로 옮겨졌고 이제 기본적으로 사용됩니다. 편집기 기능인 **범위 확장**과 **우선 순위 확장**도 실험적에서 고급으로 옮겨졌습니다.
- 실험적 리팩터링 기능인 **시그니처 변경**과 **함수 추출**을 기본적으로 사용할 수 있습니다.
- C++ 프로젝트를 위한 '빠른 프로젝트 로드'라는 실험적 기능이 있습니다. 다음에 C++ 프로젝트를 열 때 프로젝트가 더 빠르게 로드되고, 그 다음에 프로젝트를 열 때는 더 빠르게 로드됩니다.
- 이러한 기능 중 일부는 다른 언어에 공통적으로 적용되고, 일부는 C++에만 해당합니다. 이러한 새로운 기능에 대한 자세한 내용은 [Announcing Visual Studio "15"](https://blogs.msdn.microsoft.com/visualstudio/2016/10/05/announcing-visual-studio-15-preview-5/)(Visual Studio "15" 발표)를 참조하세요.

**Visual Studio 1027 버전 15.7**: ClangFormat에 대한 지원이 추가되었습니다. 자세한 내용은 [Visual Studio 2017에서 ClangFormat 지원](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/clangformat-support-in-visual-studio-2017-15-7-preview-1/)을 참조하세요.

## <a name="non-msbuild-projects-with-open-folder"></a>폴더 열기를 사용한 비 MSBuild 프로젝트에

Visual Studio 2017에서는 솔루션 또는 프로젝트를 만들 필요 없이 소스 코드가 포함된 폴더에서 코딩, 빌드 및 디버그할 수 있는 **폴더 열기** 기능이 도입되었습니다. 이렇게 하면 프로젝트가 MSBuild 기반 프로젝트가 아닌 경우에도 Visual Studio를 훨씬 간단하게 시작할 수 있습니다. **폴더 열기**를 사용하면 Visual Studio에서 MSBuild 프로젝트에 이미 제공하는 강력한 코드 이해, 편집, 빌드 및 디버깅 기능에 액세스할 수 있습니다. 자세한 내용은 [C++용 폴더 열기 프로젝트](build/open-folder-projects-cpp.md)를 참조하세요.

- 폴더 열기 환경이 개선되었습니다. 다음 json 파일을 통해 환경을 사용자 지정할 수 있습니다.
  - IntelliSense 및 검색 환경을 사용자 지정할 수 있는 CppProperties.json.
  - 빌드 단계를 사용자 지정할 수 있는 Tasks.json.
  - 디버깅 환경을 사용자 지정할 수 있는 Launch.json.

**Visual Studio 2017 버전 15.3**:

- MinGW 및 Cygwin과 같은 대체 컴파일러 및 빌드 환경에 대한 지원이 향상되었습니다. 자세한 내용은 [Visual C++ 및 폴더 열기에서 MinGW 및 Cygwin 사용(영문)](https://blogs.msdn.microsoft.com/vcblog/2017/07/19/using-mingw-and-cygwin-with-visual-cpp-and-open-folder/)을 참조하세요.
- CppProperties.json 및 CMakeSettings.json에서 전역 및 구성별 환경 변수를 정의하기 위한 지원이 추가되었습니다. 이러한 환경 변수는 launch.vs.json에 정의된 디버그 구성 및 tasks.vs.json의 작업에 사용될 수 있습니다. 자세한 내용은 [Visual C++ 및 폴더 열기에서 환경 사용자 지정(영문)](https://blogs.msdn.microsoft.com/vcblog/2017/11/02/customizing-your-environment-with-visual-c-and-open-folder/)을 참조하세요.
- 64비트 플랫폼을 쉽게 대상으로 지정할 수 있는 기능을 포함하여 CMake의 닌자 생성기에 대한 지원이 향상되었습니다.

## <a name="cmake-support-via-open-folder"></a>폴더 열기를 사용한 CMake 지원

Visual Studio 2017에서는 MSBuild 프로젝트 파일(.vcxproj)로 변환하지 않고 CMake 프로젝트를 사용할 수 있는 지원이 도입되었습니다. 자세한 내용은 [Visual C++의 CMake 프로젝트](build/cmake-projects-in-visual-studio.md)를 참조하세요. **폴더 열기**로 CMake 프로젝트를 여는 경우 C++ 편집, 빌드, 디버깅 환경이 자동으로 구성됩니다.

- C++ IntelliSense가 루트 폴더에 CppProperties.json 파일을 만들지 않아도 작동합니다. 이와 함께 CMake 파일과 CppProperties.json 파일에서 제공하는 구성을 서로 쉽게 전환할 수 있도록 새 드롭다운을 추가했습니다.

- CMakeLists.txt 파일과 같은 폴더에 있는 CMakeSettings.json 파일을 통해 추가 구성이 지원됩니다.

  ![Cmake 폴더 열기](media/cmake_cpp.png "Cmake 폴더 열기")

**Visual Studio 2017 버전 15.3**: CMake Ninja 생성기에 대한 지원이 추가되었습니다.

**Visual Studio 2017 버전 15.5**: 기존 CMake 캐시 가져오기에 대한 지원이 추가되었습니다.

**Visual Studio 2017 버전 15.7**: CMake 3.11, CMake 프로젝트의 코드 분석, 솔루션 탐색기의 대상 보기, 캐시 생성 옵션 및 단일 파일 컴파일에 대한 지원이 추가되었습니다. 자세한 내용은 [Visual Studio의 CMake 지원](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/) 및 [Visual C++의 CMake 프로젝트](build/cmake-projects-in-visual-studio.md)를 참조하세요.

## <a name="windows-desktop-development-with-c"></a>C++를 사용한 Windows 데스크톱 개발

이제 원래 C++ 워크로드에 대한 보다 세분화된 설치 환경이 제공됩니다. 필요한 도구만 설치할 수 있도록 선택 가능한 구성 요소가 추가되었습니다.  설치 관리자 UI에 나열된 구성 요소에 대해 표시된 설치 크기는 정확하지 않으며 전체 크기는 이보다 클 수 있습니다.

C++ 데스크톱 작업에서 Win32 프로젝트를 성공적으로 만들려면 도구 집합과 Windows SDK를 둘 다 설치해야 합니다. 권장된(선택된) 구성 요소 **VC++ 2017 v141 도구 집합(x86, x64)** 및 **Windows 10 SDK(10.0.nnnnn)** 를 설치하면 제대로 작동합니다. 필요한 도구가 설치되어 있지 않으면 프로젝트가 생성되지 않고 마법사가 중단됩니다.

**Visual Studio 2017 버전 15.5**:

Visual C++ 빌드 도구(이전에 독립 실행형 제품으로 제공)가 이제 Visual Studio 설치 관리자에 작업으로 포함됩니다. 이 작업은 Visual Studio IDE를 설치하지 않고 C++ 프로젝트를 빌드하는 데 필요한 도구만 설치합니다. V140 및 v141 도구 집합이 모두 포함됩니다. v141 도구 집합에는 Visual Studio 2017 버전 15.5의 최신 향상 기능이 포함되어 있습니다. 자세한 내용은 [Visual Studio Build Tools에 이제 VS2017 및 VS2015 MSVC 도구 집합 포함(영문)](https://blogs.msdn.microsoft.com/vcblog/2017/11/02/visual-studio-build-tools-now-include-the-vs2017-and-vs2015-msvc-toolsets/)을 참조하세요.

## <a name="linux-development-with-c"></a>C++를 사용한 Linux 개발

일반적으로 사용되는 확장인 [Linux 개발용 Visual C++](https://visualstudiogallery.msdn.microsoft.com/725025cf-7067-45c2-8d01-1e0fd359ae6e)가 Visual Studio에 포함됩니다. 이 설치는 Linux 환경에서 실행되는 C++ 애플리케이션을 개발 및 디버깅하는 데 필요한 모든 사항을 제공합니다.

**Visual Studio 2017 버전 15.2**:

플랫폼 간 코드 공유 및 형식 시각화에 대한 기능이 향상되었습니다. 자세한 내용은 [플랫폼 간 코드 공유 및 형식 시각화에 대한 향상된 Linux C++ 기능](https://blogs.msdn.microsoft.com/vcblog/2017/05/10/linux-cross-platform-and-type-visualization/)을 참조하세요.

**Visual Studio 2017 버전 15.5**:

- Linux 작업은 원격 Linux 컴퓨터에 파일을 동기화하는 **sftp**에 대한 대안으로 **rsync** 지원을 추가했습니다.
- ARM 마이크로프로세서를 대상으로 하는 교차 컴파일을 위한 지원이 추가되었습니다. 설치 시 이를 활성화하려면 **C++를 사용한 Linux 개발** 워크로드를 선택하고 **포함 IoT 개발** 옵션을 선택합니다. 그러면 ARM GCC 크로스 컴파일 도구 및 CMake가 설치 대상에 추가됩니다. 자세한 내용은 [Visual Studio의 ARM GCC 크로스 컴파일(영문)](https://blogs.msdn.microsoft.com/vcblog/2017/10/23/arm-gcc-cross-compilation-in-visual-studio/)을 참조하세요.
- CMake에 대한 지원이 추가되었습니다. 이제 CMake를 Visual Studio 프로젝트로 변환할 필요 없이 기존의 CMake 코드 베이스에서 작업할 수 있습니다. 자세한 내용은 [Linux CMake 프로젝트 구성](linux/cmake-linux-project.md)을 참조하세요.
- 원격 작업 실행에 대한 지원이 추가되었습니다. 이 기능을 사용하면 Visual Studio의 연결 관리자에 정의된 원격 시스템에 명령을 실행할 수 있습니다. 또한 원격 작업은 원격 시스템에 파일을 복사하는 기능을 제공합니다.
자세한 내용은 [Linux CMake 프로젝트 구성](linux/cmake-linux-project.md)을 참조하세요.

**Visual Studio 2017 버전 15.7**:

- Linux 워크로드 시나리오에 대한 다양한 개선. 자세한 내용은 [프로젝트 시스템에 대한 Linux C++ 워크로드 개선 사항, Linux 콘솔 창, rsync 및 프로세스에 연결](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/)을 참조하세요.
- 원격 Linux 연결에서 헤더용 IntelliSense. 자세한 내용은 [원격 Linux 헤더용 IntelliSense](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/intellisense-for-remote-linux-headers/) 및 [Linux CMake 프로젝트 구성](linux/cmake-linux-project.md)을 참조하세요.

## <a name="game-development-with-c"></a>C++를 사용한 게임 개발

C++의 모든 기능을 사용하여 DirectX 또는 Cocos2d로 구동하는 전문 게임을 개발해 보세요.

## <a name="mobile-development-with-c-android-and-ios"></a>C++를 사용한 모바일 개발(Android 및 iOS)

이제 Visual Studio를 사용하여 Android 및 iOS를 대상으로 할 수 있는 모바일 앱을 만들고 디버깅할 수 있습니다.

## <a name="universal-windows-apps"></a>유니버설 Windows 앱

C++는 유니버설 Windows 앱 워크로드에 대한 선택적 구성 요소로 제공됩니다.  현재 C++ 프로젝트를 업그레이드하려면 수동으로 해야 합니다. Visual Studio 2017에서 v140을 대상으로 한 UWP 프로젝트를 열 때 Visual Studio 2015를 설치하지 않은 경우 프로젝트 속성 페이지에서 v141 플랫폼 도구 집합을 선택해야 합니다.

## <a name="new-options-for-c-on-universal-windows-platform-uwp"></a>유니버설 Windows 플랫폼(UWP)의 C++에 대한 새로운 옵션
이제 유니버설 Windows 플랫폼 및 Windows Store용 C++ 애플리케이션 작성 및 패키징에 대한 새 옵션이 제공됩니다. 사이드로드를 통한 기존 채널 또는 Windows 스토어를 통해 배포하기 위해 데스크톱 브리지 인프라를 사용하여 기존 데스크톱 애플리케이션 또는 COM 개체를 패키징할 수 있습니다. Windows 10의 새로운 기능을 사용하면 다양한 방법으로 데스크톱 애플리케이션에 UWP 기능을 추가할 수 있습니다. 자세한 내용은 [데스크톱 브리지](/windows/uwp/porting/desktop-to-uwp-root)를 참조하세요.

**Visual Studio 2017 버전 15.5**: 데스크톱 브리지를 사용하여 데스크톱 애플리케이션 패키징 작업을 많이 간소화하는 **Windows 애플리케이션 패키징 프로젝트** 프로젝트 템플릿이 추가되었습니다. **파일 | 새로 만들기 | 프로젝트 | 설치됨 | Visual C++ | 유니버설 Windows 플랫폼**에서 볼 수 있습니다. 자세한 내용은 [Visual Studio(데스크톱 브리지)를 사용하여 앱 패키지](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)를 참조하세요.

이제 새 코드를 작성할 때 헤더 파일에서만 구현되는 Windows 런타임용 표준 C++ 언어 프로젝션인 C++/WinRT를 사용할 수 있습니다. C++/WinRT를 사용하면 모든 표준 규격 C++ 컴파일러를 통해 Windows 런타임 API를 작성하고 사용할 수 있습니다. C++/WinRT는 C++ 개발자에게 최신 Windows API에 대한 최고 수준의 액세스를 제공하도록 설계되었습니다. 자세한 내용은 [C++/WinRT Available on GitHub](https://moderncpp.com/)(GitHub에서 C++/WinRT를 사용할 수 있음)를 참조하세요.

Windows SDK Insider Preview의 빌드 17025부터 C++/WinRT가 Windows SDK에 포함됩니다. 자세한 내용은 [Windows SDK에 이제 C++/WinRT가 포함됨(영문)](https://blogs.msdn.microsoft.com/vcblog/2017/11/01/cppwinrt-is-now-included-the-windows-sdk/)을 참조하세요.

## <a name="clangc2-platform-toolset"></a>Clang/C2 플랫폼 도구 집합

이제 Visual Studio 2017과 함께 제공되는 Clang/C2 도구 집합이 대규모 프로젝트를 빌드하는 데 중요한 **/bigobj** 스위치를 지원합니다. 또한 컴파일러의 프런트 엔드와 백 엔드에서 몇몇 중요한 버그 수정이 있었습니다.

## <a name="c-code-analysis"></a>C++ 코드 분석

[C++ Core 지침](https://github.com/isocpp/CppCoreGuidelines)을 적용하기 위한 C++ Core Checkers가 이제는 Visual Studio와 함께 배포됩니다. 프로젝트의 속성 페이지의 **코드 분석 확장** 페이지에서 체커를 활성화하기만 하면 코드 분석을 실행할 때 확장이 포함됩니다. 자세한 내용은 [C++ 핵심 지침 검사기 사용](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers)을 참조하세요.

![CppCoreCheck](media/CppCoreCheck.png "CppCoreCheck 속성 페이지")

**Visual Studio 2017 버전 15.3**: 리소스 관리와 관련된 규칙에 대한 지원이 추가되었습니다.

**Visual Studio 2017 버전 15.5**: 새로운 C++ Core Guidelines 검사 항목에는 스마트 포인터 정확성, 올바른 전역 이니셜라이저 사용, `goto` 및 잘못된 캐스트 같은 구문 사용 플래그 지정이 포함됩니다.

15.3에서 나타나는 일부 경고 번호가 15.5에서는 더 이상 나타나지 않습니다. 이러한 경고는 더 구체적인 검사로 대체되었습니다.

**Visual Studio 2017 버전 15.6**:

- 단일 파일 분석 및 분석 런타임 성능 향상을 위한 지원이 추가되었습니다. 자세한 내용은 [Visual Studio 2017 15.6 Preview 2에 대한 C++ 정적 분석 향상](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/c-static-analysis-improvements-for-visual-studio-2017-15-6-preview-2/)을 참조하세요.

**Visual Studio 2017 버전 15.7**:

- 실행할 코드 분석 규칙을 지정할 수 있는 [/analyze:ruleset](build/reference/analyze-code-analysis.md)에 대한 지원이 추가되었습니다.
- 추가 C++ Core Guidelines 규칙에 대한 지원이 추가되었습니다.  자세한 내용은 [C++ 핵심 지침 검사기 사용](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers)을 참조하세요.

## <a name="unit-testing"></a>단위 테스트

**Visual Studio 2017 버전 15.5**:

이제 Google Test Adapter와 Boost.Test Adapter가 **C++를 사용한 데스크톱 개발** 워크로드의 구성 요소로 제공되며, **테스트 탐색기**와 통합됩니다. Cmake 프로젝트에 대한 CTest 지원이 추가되었습니다(폴더 열기 사용). 하지만 **테스트 탐색기**와의 완전한 통합은 아직 제공되지 않습니다. 자세한 내용은 [C/C++에 대한 단위 테스트 작성](/visualstudio/test/writing-unit-tests-for-c-cpp)을 참조하세요.

**Visual Studio 2017 버전 15.6**:

- Boost.Test 동적 라이브러리 지원에 대한 지원이 추가되었습니다.
- 이제 Boost.Test 항목 템플릿을 IDE에서 사용할 수 있습니다.

자세한 내용은 [Boost.Test 단위 테스트: 동적 라이브러리 지원 및 새 항목 템플릿](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/boost-test-unit-testing-dynamic-library-support-and-new-item-template/)을 참조하세요.

**Visual Studio 2017 버전 15.7**:

[CodeLens](/visualstudio/ide/find-code-changes-and-other-history-with-codelens) C++ 단위 테스트 프로젝트에 대한 지원이 추가되었습니다. 자세한 내용은 [C++ 단위 테스트 프로젝트에 대한 CodeLens 알림](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/announcing-codelens-for-c-unit-testing/)을 참조하세요.

## <a name="visual-studio-graphics-diagnostics"></a>Visual Studio 그래픽 진단

Visual Studio 그래픽 진단은 Direct3D 앱의 렌더링 및 성능 문제를 기록한 후 분석하기 위한 도구 집합입니다. Windows PC에서 로컬로 실행 중이거나 Windows 디바이스 에뮬레이터 또는 원격 PC나 디바이스에서 실행 중인 앱에서 그래픽 진단 기능을 사용할 수 있습니다.

- **꼭짓점 및 기하 도형 셰이더의 입력 및 출력:** 꼭짓점 셰이더 및 기하 도형 셰이더의 입력과 출력을 볼 수 있는 기능은 가장 많이 요청된 기능 중 하나였으며 이제 도구에서 지원됩니다. 파이프라인 단계 보기에서 VS 또는 GS 단계를 선택하면 아래 표의 입력 및 출력 검사가 시작됩니다.

  ![셰이더의 입력/출력](media/io-shaders.png)

- **개체 테이블에서 검색 및 필터링:** 찾으려는 리소스를 빠르고 쉽게 찾는 방법을 제공합니다.

  ![검색](media/search.png)

- **리소스 기록:** 이 새로운 보기는 캡처된 프레임 렌더링하는 동안 사용된 리소스의 전체 수정 기록을 간단하게 볼 수 있는 방법을 제공합니다. 리소스에 대한 기록을 호출하려면 리소스 하이퍼링크 옆에 있는 시계 아이콘을 클릭하면 됩니다.

  ![리소스 기록](media/resource-history.png)

  리소스의 변경 기록으로 채워진 새 **리소스 기록** 도구 창이 표시됩니다.

  ![리소스 기록 변경](media/resource-history-change.png)

  전체 호출 스택 캡처링을 사용하여 프레임이 캡처된 경우(**Visual Studio > 도구 > 옵션(** 그래픽 진단 **아래)**), 각 변경 이벤트의 컨텍스트를 신속하게 추론하고 Visual Studio 프로젝트 내에서 검사할 수 있습니다.

- **API 통계:** 프레임의 API 사용에 대한 대략적인 요약을 표시합니다. 인지하지 못한 상태에서 수행 중인 호출이나 너무 많이 수행 중인 호출을 검색하는 데 유용할 수 있습니다. 이 창은 Visual Studio Graphics Analyzer의 **보기 > API 통계**를 통해 사용할 수 있습니다.

  ![API 통계](media/api-stats.png)

- **메모리 통계:** 드라이버가 프레임에 생성되는 리소스에 대해 할당하는 메모리 양을 표시합니다. 이 창은 **Visual Studio Graphics Analyzer**의 **보기 | 메모리 통계**를 통해 사용할 수 있습니다. 마우스 오른쪽 단추로 클릭하고 **모두 복사**를 선택하여 데이터를 CSV 파일에 복사한 후 스프레드시트에서 볼 수 있습니다.

  ![메모리 통계](media/memory-stats.png)

- **프레임 유효성 검사:** 새로운 오류 및 경고 목록을 통해 Direct3D 디버그 계층에서 검색된 잠재적인 문제에 따라 이벤트 목록을 쉽게 탐색할 수 있습니다. Visual Studio Graphics Analyzer에서 **보기 > 프레임 유효성 검사**를 클릭하여 창을 엽니다. 그런 다음 **유효성 검사 실행**을 클릭하여 분석을 시작합니다. 프레임의 복잡성에 따라 완료하는 데 몇 분 정도 걸릴 수 있습니다.

  ![프레임 유효성 검사](media/frame-validation.png)

- **D3D12에 대한 프레임 분석:** 프레임 분석을 사용하여 안내된 "가상 분석" 실험을 통해 그리기 호출 성능을 분석할 수 있습니다. 프레임 분석 탭으로 전환한 다음 분석을 실행하여 보고서를 표시합니다. 자세한 내용은 [GoingNative 25: Visual Studio 그래픽 프레임 분석](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool) 비디오를 시청하세요.

  ![프레임 분석](media/frame-analysis.png)

- **GPU 사용량 향상:** 보다 자세한 분석을 위해 GPU 보기 또는 WPA(Windows 성능 분석기) 도구를 사용하여 Visual Studio GPU 사용량 프로파일러를 통해 수행된 추적을 엽니다. Windows 성능 도구 키트가 설치되어 있는 경우 WPA 및 GPU 보기를 위한 두 개의 하이퍼링크가 세션 개요의 오른쪽 아래에 표시됩니다.

  ![GPU 사용량](media/gpu-usage.png)

  이 링크를 통해 GPU 보기에서 열린 추적은 VS와 GPU 보기 간에 동기화된 타임라인 확대/축소 및 이동을 지원합니다. VS의 확인란을 사용하여 동기화 사용 여부를 제어합니다.

  ![GPU 보기](media/gpu-view.png)
