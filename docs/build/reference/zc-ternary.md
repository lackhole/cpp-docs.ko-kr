---
title: '/Zc: ternary (조건 연산자 규칙 적용)'
ms.date: 3/06/2018
f1_keywords:
- /Zc:ternary
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
ms.openlocfilehash: cb9a4f8468a9cb57af711cdca36ee343e5092493
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315438"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/Zc: ternary (조건 연산자 규칙 적용)

적용 사용 C++ 형식 및 조건부 연산자 식의 두 번째 및 세 번째 피연산자의 const 또는 volatile (cv) 한정자에 대 한 표준 규칙입니다.

## <a name="syntax"></a>구문

> **/Zc:ternary**[**-**]

## <a name="remarks"></a>설명

Visual Studio 버전 15.3에서는 컴파일러 지원에 대 한 C++ 표준 조건부 (삼항) 연산자 (**?:**) 동작 합니다. C++ 표준에서는 동일한 형식 및 cv 한정자를, 동일한 유형 및 다른 cv 한정자를 명확 하 게 변환할 수 있는 하나의 피연산자에 대 한 또는 throw 식인 하나 또는 두 피연산자에 대 한 피연산자가 필요 합니다. Visual Studio 버전 15.5 이전 버전에서는 컴파일러가 허용 하 여 표준에서 모호한 간주 되는 변환입니다. 경우는 **/zc: ternary** 옵션을 지정 하면 컴파일러는 표준을 준수 하 고 일치 하는 형식 및 두 번째 및 세 번째 피연산자의 cv 한정자에 대 한 규칙을 충족 하지 않는 코드를 거부 합니다.

합니다 **/zc: ternary** 옵션은 기본적으로 해제 되어 있습니다. 사용 하 여 **/zc: ternary** 준수 동작을 사용 하도록 설정 하려면 또는 **/Zc:ternary-** 를 명시적으로 이전 비준수 컴파일러 동작을 지정 합니다. 합니다 [/ permissive-](permissive-standards-conformance.md) 옵션은 암시적으로이 옵션을 사용 하지만 사용 하 여 재정의할 수 있습니다 **/Zc:ternary-** 합니다.

### <a name="examples"></a>예제

이 예제에서 형식 및 형식으로의 변환을 모두 비 명시적 초기화를 제공 하는 클래스 모호한 변환 시킬 수 있습니다 하는 방법을 보여 줍니다. 이 코드 기본적으로 컴파일러에 의해 수락 되었지만 경우 거부 **/zc: ternary** 또는 **관대 한 /-** 지정 됩니다.

```cpp
// zcternary1.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary zcternary1.cpp

struct A
{
   long l;
   A(int i) : l{i} {}    // explicit prevents conversion of int
   operator int() const { return static_cast<int>(l); }
};

int main()
{
   A a(42);
   // Accepted when /Zc:ternary (or /permissive-) is not used
   auto x = true ? 7 : a;  // old behavior prefers A(7) over (int)a
   auto y = true ? A(7) : a;   // always accepted
   auto z = true ? 7 : (int)a; // always accepted
   return x + y + z;
}
```

필요한 수정 프로그램 일반적인 기본 형식으로 명시적 캐스트를 확인 하거나 명시적 변환 하 여 단방향 변환에서 일치 하는 형식 항목에 대 한 컴파일러 검색 참여를 차단 하는 것입니다.

이 일반적인 패턴에 중요 한 예외는 피연산자의 형식 같은 null로 끝나는 문자열 형식 중 하나인 경우 `const char*`, `const char16_t*`등입니다. 배열 형식과를 decay는 포인터 형식으로도 표현할 수 있습니다. 동작을 때의 실제 두 번째 또는 세 번째 피연산자?:은 해당 형식의 문자열 리터럴을 사용 하는 언어 표준에 따라 달라 집니다. C + + 17 c++14에서이 사례에 대 한 의미 체계가 변경 되었습니다. 아래에서 다음 예제에서 코드는 허용 하는 결과적으로 **/std: c + + 14** (컴파일러 기본값)는 경우 거부 **/std: c + + 17** 지정 됩니다.

```cpp
// zcternary2.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary /std:c++17 zcternary2.cpp

struct MyString
{
   const char * p;
   MyString(const char* s = "") noexcept : p{s} {} // from char*
   operator const char*() const noexcept { return p; } // to char*
};

int main()
{
   MyString s;
   auto x = true ? "A" : s; // MyString: permissive prefers MyString("A") over (const char*)s
}
```

이 코드를 수정 하려면 캐스팅 피연산자 중 하나가 명시적으로 합니다.

아래 **/zc: ternary**, 컴파일러 거부 조건부 연산자의 인수 중 하나가 void 형식 및 다른 throw 식이 아닙니다. 이러한 일반적인 용도 같은 ASSERT 매크로에서 됩니다.

```cpp
// zcternary3.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary /c zcternary3.cpp

void myassert(const char* text, const char* file, int line);
#define ASSERT(ex) (void)((ex) ? 0 : myassert(#ex, __FILE__, __LINE__))
// To fix, define it this way instead:
// #define ASSERT(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))

int main()
{
   ASSERT(false);  // C3447
}
```

일반적인 솔루션 단순히 void()를 사용 하 여 void가 아닌 인수를 바꾸는 것입니다.

이 샘플에서는 둘 다에서 오류를 발생 하는 코드를 보여 줍니다 **/zc: ternary** 하 고 **/Zc:ternary-**:

```cpp
// zcternary4.cpp
// Compile by using:
//   cl /EHsc /W4 /nologo /Zc:ternary zcternary4.cpp
//   cl /EHsc /W4 /nologo /Zc:ternary zcternary4.cpp

int main() {
   auto p1 = [](int a, int b) { return a > b; };
   auto p2 = [](int a, int b) { return a > b; };
   auto p3 = true ? p1 : p2; // C2593 under /Zc:ternary, was C2446
}
```

이 코드는이 오류 이전에 지정한:

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

사용 하 여 **/zc: ternary** 실패의 원인을 더 분명해 집니다; 여러 구현에서 정의 된 호출 규칙을 사용할 수 있는 각 람다를 생성 하는 아키텍처, 컴파일러가 표현 그중에서 기본 설정 없음 람다 서명을 명확 하 게 수입니다. 새 출력이 같습니다.

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

채택와 관련 된 문제의 공통 원인을 **/zc: ternary** 이 스위치에서 변경 결과 형식의 일부 템플릿 메타 프로그래밍의 조건부 연산자를 사용 하 여 제공 됩니다. 다음 예제에서는 두 가지 경우를 보여 줍니다. 여기서 **/zc: ternary** 메타 프로그래밍 아닌 컨텍스트에서 조건식의 결과 형식을 변경 합니다.

```cpp
// zcternary5.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary zcternary5.cpp

int main(int argc, char**) {
   char a = 'A';
   const char b = 'B';
   decltype(auto) x = true ? a : b; // char without, const char& with /Zc:ternary
   const char(&z)[2] = argc > 3 ? "A" : "B"; // const char* without /Zc:ternary
   return x > *z;
}
```

이러한 경우에 일반적인 해결책은 적용을 `std::remove_reference` 이전 동작을 유지 하기 위해 필요한 경우 결과에 특성 (trait)을 입력 합니다.

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 수정 된 **추가 옵션** 포함할 속성을 **/zc: ternary** 또는 **/Zc:ternary-** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)
