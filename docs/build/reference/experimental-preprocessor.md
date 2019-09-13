---
title: '/o실험적: 전처리기 (전처리기 규칙 모드 사용)'
description: '/O실험적: 전처리기 컴파일러 옵션을 사용 하 여 표준에 맞는 전처리기에 대해 실험적 컴파일러 지원을 사용 하도록 설정할 수 있습니다.'
ms.date: 09/03/2019
f1_keywords:
- preprocessor
- /experimental:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /experimental:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 3055cfa2a32d1d668dbe0c51b5542415b5bb0af4
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70294440"
---
# <a name="experimentalpreprocessor-enable-preprocessor-conformance-mode"></a>/o실험적: 전처리기 (전처리기 규칙 모드 사용)

이 옵션은 C99 전처리기 기능을 비롯 하 여 c + + 11 표준을 준수 하는 실험적 토큰 기반 전처리기를 사용 하도록 설정 합니다.

## <a name="syntax"></a>구문

> **/s실험적: 전처리기** [ **-** ]

## <a name="remarks"></a>설명

**/B실험적: 전처리기** 컴파일러 옵션을 사용 하 여 전처리기에 맞는 실험을 사용 하도록 설정 합니다. **/O실험적: 전처리기-** 옵션을 사용 하 여 기존 전처리기를 명시적으로 지정할 수 있습니다.

**/S실험적: 전처리기** 옵션은 Visual Studio 2017 버전 15.8부터 사용할 수 있습니다.

컴파일 시간에 사용 중인 전처리기를 검색할 수 있습니다. 미리 정의 된 매크로 [ \_MSVC\_](../../preprocessor/predefined-macros.md) 의 값을 확인 하 여 기존의 전처리기가 사용 중인지 여부를 확인 합니다. 이 매크로는 전처리기가 호출 되는 것과 관계 없이 해당 매크로를 지 원하는 컴파일러 버전에 의해 무조건 설정 됩니다. 기존 전처리기에 대 한 값은 1입니다. 준수 하는 실험적 전처리기의 경우 0입니다.

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

### <a name="behavior-changes-in-the-experimental-preprocessor"></a>실험적 전처리기의 동작 변경 내용

전처리기 규칙 모드를 사용 하는 경우 발견 되는 일반적인 주요 변경 사항 중 몇 가지는 다음과 같습니다.

#### <a name="macro-comments"></a>매크로 주석

일반적인 전처리기는 전처리기 토큰 대신 문자 버퍼를 사용 합니다. 이를 통해 이러한 전처리기 주석 트릭과 같이 규격 전처리기에서 작동 하지 않는 일부 비정상적인 동작을 수행할 수 있습니다.

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
// To make standards compliant, wrap the following line with the appropriate #if/#endif
DISAPPEARING_TYPE myVal;
```

#### <a name="string-prefixes-lval"></a>문자열 접두사 (L # val)

기존 전처리기는 문자열 접두사를 [문자열 화 연산자 (#)](../../preprocessor/stringizing-operator-hash.md)의 결과와 잘못 결합 합니다.

```cpp
#define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

이 `L` 접두사는 매크로 확장 후 인접 문자열 리터럴이 결합 되기 때문에 필요 하지 않습니다. 이전 버전과 호환 되는 수정은 정의를 다음과 같이 변경 하는 것입니다.

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

이 문제는 또한 와이드 문자열 리터럴에 대 한 인수를 ' stringize 하는 편리한 매크로 에서도 찾을 수 있습니다.

```cpp
// The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str

// Potential fixes:
// Use string concatenation of L"" and #str to add prefix
// This works because adjacent string literals are combined after macro expansion
#define STRING1(str) L""#str

// Add the prefix after #str is stringized with additional macro expansion
#define WIDE(str) L##str
#define STRING2(str) WIDE(#str)

// Use concatenation operator ## to combine the tokens.
// The order of operations for ## and # is unspecified, although all compilers
// checked perform the # operator before ## in this case.
#define STRING3(str) L## #str
```

#### <a name="warning-on-invalid"></a>잘못 됨에 대 한 경고 ##

[토큰 붙여넣기 연산자 (# #)](../../preprocessor/token-pasting-operator-hash-hash.md) 가 잘못 된 단일 전처리 토큰을 생성 하지 않으면 동작이 정의 되지 않습니다. 기존 전처리기는 토큰을 자동으로 결합 하지 못합니다. 새 전처리기는 대부분의 다른 컴파일러의 동작과 일치 하 고 진단을 내보냅니다.

```cpp
// The ## is unnecessary and doesn't result in a single preprocessing token.
#define ADD_STD(x) std::##x

// Declare a std::string
ADD_STD(string) s;
```

#### <a name="comma-elision-in-variadic-macros"></a>Variadic 매크로의 쉼표 생략

다음 예제를 참조하세요.

```cpp
void func(int, int = 2, int = 3);
// This macro replacement list has a comma followed by __VA_ARGS__
#define FUNC(a, ...) func(a, __VA_ARGS__)
int main()
{
    // The following macro is replaced with:
    // func(10,20,30)
    FUNC(10, 20, 30);

    // A conforming preprocessor replaces the following macro with:
    // func(1, );
    // which results in a syntax error.
    FUNC(1, );
}
```

모든 주요 컴파일러에는이 문제를 해결 하는 데 도움이 되는 전처리기 확장이 있습니다. 기존 MSVC 전처리기는 항상 빈 `__VA_ARGS__` 대체 항목 앞에 쉼표를 제거 합니다. 업데이트 된 전처리기는 널리 사용 되는 다른 플랫폼 간 컴파일러의 동작을 더욱 잘 따릅니다. 쉼표를 제거 하려면 variadic 인수가 비어 있는 것이 아니라 반드시 누락 되어야 하 고 `##` 연산자를 사용 하 여 표시 되어야 합니다.

```cpp
#define FUNC2(a, ...) func(a , ## __VA_ARGS__)
int main()
{
    // The variadic argument is missing in the macro being evoked
    // The comma is removed and replaced with:
    // func(1)
    FUNC2(1);

    // The variadic argument is empty, but not missing. (Notice the
    // comma in the argument list.) The comma isn't removed
    // when the macro is replaced:
    // func(1, )
    FUNC2(1, );
}
```

예정 된 C + + 2a 표준에서는 아직 구현 되지 않은를 추가 `__VA_OPT__`하 여이 문제를 해결 했습니다.

#### <a name="macro-arguments-are-unpacked"></a>매크로 인수는 ' 압축 풀기 '입니다.

일반적인 전처리기에서 매크로가 인수 중 하나를 다른 종속 매크로에 전달 하는 경우 인수는 대체 될 때 "압축 풀기" 되지 않습니다. 일반적으로 이러한 최적화는 알지 못할 수 있지만 비정상적인 동작이 발생할 수 있습니다.

```cpp
// Create a string out of the first argument, and the rest of the arguments.
#define TWO_STRINGS( first, ... ) #first, #__VA_ARGS__
#define A( ... ) TWO_STRINGS(__VA_ARGS__)

const char* c[2] = { A(1, 2) };
// Conformant preprocessor results:
// const char c[2] = { "1", "2" };
// Traditional preprocessor results, all arguments are in the first string:
// const char c[2] = { "1, 2", };
```

를 확장할 `A()`때 기존 전처리기는의 첫 번째 인수에 `__VA_ARGS__` 패키지 된 모든 인수 `TWO_STRINGS`를 전달 합니다. 의 `TWO_STRINGS` variadic 인수가 비어 있습니다 .이 경우의 `#first` 결과는 뿐 `"1"`아니라로 `"1, 2"` 설정 됩니다. 일반적인 전처리기 확장에서의 `#__VA_ARGS__` 결과에 어떤 일이 발생 했는지 궁금할 수 있습니다. variadic 매개 변수가 비어 있는 경우 빈 문자열 리터럴 ""이 발생 해야 합니다. 별도의 문제로 인해 빈 문자열 리터럴 토큰이 생성 되지 않았습니다.

#### <a name="rescanning-replacement-list-for-macros"></a>매크로에 대 한 대체 목록 다시 검사

매크로가 대체 된 후에는 대체 하는 추가 매크로 식별자에 대해 결과 토큰을 다시 검색 합니다. 기존 전처리기에서 사용 하는 다시 검사 알고리즘은 실제 코드를 기반으로 하는이 예제에 나와 있는 것 처럼 준수 하지 않습니다.

```cpp
#define CAT(a,b) a ## b
#define ECHO(...) __VA_ARGS__

// IMPL1 and IMPL2 are implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)
// MACRO chooses the expansion behavior based on the value passed to macro_switch
#define DO_THING(macro_switch, b) CAT(IMPL, macro_switch) ECHO(( "Hello", b))

DO_THING(1, "World");
// Traditional preprocessor:
// do_thing_one( "Hello", "World");
// Conformant preprocessor:
// IMPL1 ( "Hello","World");
```

이 예제에서 진행 되는 작업을 확인 하기 위해 `DO_THING`다음부터 확장을 분할 합니다.

`DO_THING(1, "World")` ->
`CAT(IMPL, 1) ECHO(("Hello", "World"))`

둘째, CAT이 확장 됩니다.

`CAT(IMPL, 1)` -> `IMPL ## 1` -> `IMPL1`

토큰을이 상태로 전환 합니다.

`IMPL1 ECHO(("Hello", "World"))`

전처리기는 함수 형식 매크로 식별자 `IMPL1`를 찾았지만 "("가 오지 않으므로 함수 형태의 매크로 호출로 간주 되지 않습니다. 다음 토큰으로 이동 하 여 호출 되는 함수 같은 매크로 `ECHO` 를 찾습니다.

`ECHO(("Hello", "World"))` -> `("Hello", "World")`

`IMPL1`는 확장에 대해 다시 고려 되지 않으므로 확장의 전체 결과는 다음과 같습니다.

`IMPL1("Hello", "World");`

이 매크로는 실험적 전처리기와 일반적인 전처리기에서 동일한 방식으로 동작 하도록 수정할 수 있습니다. 해결 방법은 다른 간접 계층을 추가 하는 것입니다.

```cpp
#define CAT(a,b) a##b
#define ECHO(...) __VA_ARGS__

// IMPL1 and IMPL2 are macros implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)

#define CALL(macroName, args) macroName args
#define DO_THING_FIXED(a,b) CALL( CAT(IMPL, a), ECHO(( "Hello",b)))

DO_THING_FIXED(1, "World");
// macro expanded to:
// do_thing_one( "Hello", "World");
```

### <a name="conformance-mode-conformance"></a>규칙 모드 규칙

실험적 전처리기는 아직 완료 되지 않았으며 일부 전처리기 지시문 논리는 여전히 기존의 동작으로 대체 됩니다. 다음은 불완전 한 기능의 일부 목록입니다.

- 지원`_Pragma`
- C + + 20 기능
- 추가 진단 기능 향상
- /E 및/P 아래의 출력을 제어 하는 스위치입니다.
- 차단 버그 상승: 전처리기 상수 식의 논리 연산자는 새 전처리기에서 완전히 구현 되지 않습니다. 일부 `#if` 지시문에서 새 전처리기는 기존 전처리기로 대체 될 수 있습니다. 일반적인 전처리기와 호환 되지 않는 매크로가 확장 되는 경우에만 결과가 뚜렷하게 전처리기 슬롯을 빌드할 때 발생할 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++**  > **명령줄** 속성 페이지를 선택합니다.

1. **/S실험적: 전처리기** 를 포함 하도록 **추가 옵션** 속성을 수정한 다음 **확인**을 선택 합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)
