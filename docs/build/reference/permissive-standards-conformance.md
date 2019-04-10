---
title: / permissive-(표준 준수)
ms.date: 03/08/2019
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 05089ef4f0a516f932d82f13be979da572701ae2
ms.sourcegitcommit: 39debf8c525c3951af6913ee5e514617658f8859
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424133"
---
# <a name="permissive--standards-conformance"></a>/ permissive-(표준 준수)

컴파일러에 표준 규격 모드를 지정 합니다. 이 옵션을 확인 하 고 더 정확 하 고 이식 가능 하도록 코드에서 규칙과 관련 된 문제를 해결 하는 데 사용 합니다.

## <a name="syntax"></a>구문

> **/permissive-**

## <a name="remarks"></a>설명

이 옵션은 Visual Studio 2017 이상에 지원 됩니다.

사용할 수는 **/ permissive-** 표준 준수 컴파일러 동작을 지정 하는 컴파일러 옵션입니다. 이 옵션 관대 한 동작을 사용 하지 않도록 설정 하 고 설정 합니다 [/Zc](zc-conformance.md) 엄격한 규칙에 대 한 컴파일러 옵션입니다. 이 옵션에는 IDE에서 IntelliSense 엔진 밑줄 비준수 코드를 또한 수 있습니다.

기본적으로 **/ permissive-** 옵션은 Visual Studio 2017 버전 15.5 이상 버전에서 만든 새로운 프로젝트에서 설정 합니다. 이전 버전에서 기본적으로 설정 되지 않았습니다. 이 옵션이 설정 되어, 컴파일러 진단 오류를 생성 합니다. 또는 경고를 생성 하는 비표준 언어 경우 코드에서 발견 되 면, 몇 가지 일반적인 버그를 포함 하 여 사전에서-C + + 11 코드입니다.

합니다 **/ permissive-** 옵션은 소프트웨어 개발 키트 (SDK) 또는 Windows Driver Kit (WDK), Windows Fall Creators SDK (10.0.16299.0)부터 같은 최신 Windows 키트, 헤더 파일의 거의 모든 호환입니다. 이전 버전의 SDK에서 컴파일하는 데 실패할 수 있습니다 **/ permissive-** 다양 한 소스 코드 표준을 따르도록 합니다. 컴파일러 및 다른 릴리스 타임 라인의 Sdk 출시 하므로 몇 가지 나머지 문제가 있습니다. 특정 헤더 파일 문제를 참조 하세요 [Windows 헤더 문제](#windows-header-issues) 아래.

**관대 한 /-** 옵션 집합을 [/zc: referencebinding](zc-referencebinding-enforce-reference-binding-rules.md), [/zc: strictstrings](zc-strictstrings-disable-string-literal-type-conversion.md), 및 [/zc: rvaluecast](zc-rvaluecast-enforce-type-conversion-rules.md) 준수 하는 옵션 동작입니다. 이러한 옵션을 기본값으로 비준수 동작 합니다. 특정 전달할 수 있습니다 **/Zc** 한 후 옵션 **/ permissive-** 이 동작을 재정의 하려면 명령줄에서.

버전의 Visual Studio 2017 버전 15.3에서에서 컴파일러 시작 합니다 **생성-** 옵션 집합을 [/zc: ternary](zc-ternary.md) 옵션입니다. 또한 컴파일러에서는 2 단계 이름 조회에 대 한 요구 사항을 자세히 구현합니다. 경우는 **관대 한 /-** 옵션을 설정 하면 컴파일러는 함수 및 클래스 템플릿 정의 구문 분석 하 고 템플릿을 사용 하는 종속 및 종속 되지 않는 이름을 식별 합니다. 이 릴리스에서 이름 종속성 분석만 수행 됩니다.

환경별 확장 및 구현에 따라 남겨 두고 표준 언어 영역 받지 **/ permissive-** 합니다. 예를 들어 Microsoft 전용 `__declspec`, 호출 규칙 및 구조적된 예외 처리 키워드 및 컴파일러 별 pragma 지시문 또는 특성의 컴파일러로 플래그가 지정 되지 않습니다 **/ permissive-** 모드입니다.

**/ permissive-** 옵션은 어떤 언어 구문이 됩니다 비준수를 확인 하려면 현재 컴파일러 버전의 규칙 지원을 사용 합니다. 옵션은 코드의 특정 버전을 준수 하는지 확인 하지 않습니다는 C++ 표준입니다. 최신 초안 표준에 대 한 모든 구현 된 컴파일러 지원을 사용 하려면 사용 합니다 [/std:latest](std-specify-language-standard-version.md) 옵션입니다. 현재 구현 된 c++17 표준에 컴파일러 지원을 제한 하려면 합니다 [/std: c + + 17](std-specify-language-standard-version.md) 옵션입니다. 제한 된 c++14 표준와 비슷하도록 컴파일러 지원을 사용 합니다 [/std: c + + 14](std-specify-language-standard-version.md) 옵션을 기본값인 합니다.

모든 c++11, c++14 또는 C + + 17 표준을 준수 하지 코드는 모든 버전의 Visual Studio 2017의 MSVC 컴파일러에 의해 지원 됩니다. Visual Studio의 버전에 따라 합니다 **/ permissive-** 옵션에는 2 단계 이름 조회의 일부 측면에 대 한, 비 const 참조를 임시 바인딩, 직접 초기화로 복사 초기화를 처리 하는 방법, 허용 문제를 검색할 수 없는 경우 여러 개의 사용자 정의 변환을 초기화 또는 대체 토큰에서 논리 연산자에 대 한 및 기타 지원 되지 않는 규칙 영역입니다. Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요. 최대한 활용 가져오려고 **관대 한 /-**, Visual Studio 최신 버전으로 업데이트 합니다.

### <a name="how-to-fix-your-code"></a>코드를 수정 하는 방법

비준수 사용 하는 경우로 검색 되는 코드의 예로 다음과 같습니다 **/ permissive-** 를 함께 문제를 해결 하는 방법이 제안된 합니다.

#### <a name="use-default-as-an-identifier-in-native-code"></a>네이티브 코드의 식별자로 사용 하 여 기본

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="look-up-members-in-dependent-base"></a>종속 된 기본 멤버 조회

```cpp
template <typename T>
struct B {
    void f();
};

template <typename T>
struct D : public B<T> // B is a dependent base because its type
                       // depends on the type of T.
{
    // One possible fix is to uncomment the following line.
    // If this is a type, don't forget the 'typename' keyword.
    // using B<T>::f;

    void g() {
        f(); // error C3861: 'f': identifier not found
             // Another fix is to change it to 'this->f();'
    }
};

void h() {
    D<int> d;
    d.g();
}
```

#### <a name="use-of-qualified-names-in-member-declarations"></a>멤버 선언에 정규화 된 이름 사용

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>멤버 이니셜라이저에서 여러 공용 구조체 멤버를 초기화 합니다.

```cpp
union U
{
    U()
        : i(1), j(1) // error C3442: Initializing multiple members of
                     // union: 'U::i' and 'U::j'.
                     // Remove all but one of the initializations to fix.
    {}
    int i;
    int j;
};
```

#### <a name="hidden-friend-name-lookup-rules"></a>숨겨진된 friend 이름 조회 규칙

```cpp
// Example 1
struct S {
    friend void f(S *);
};
// Uncomment this declaration to make the hidden friend visible:
// void f(S *); // This declaration makes the hidden friend visible

using type = void (*)(S *);
type p = &f; // error C2065: 'f': undeclared identifier.
```

```cpp
// Example 2
struct S {
    friend void f(S *);
};
void g() {
    // Using nullptr instead of S prevents argument dependent lookup in S
    f(nullptr); // error C3861: 'f': identifier not found

    S *p = nullptr;
    f(S); // Hidden friend now found via argument-dependent lookup.
}
```

#### <a name="use-scoped-enums-in-array-bounds"></a>배열 범위 내에 범위가 지정 된 열거형을 사용 하 여

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>각 네이티브 코드에 사용 하 여

```cpp
void func() {
    int array[] = {1, 2, 30, 40};
    for each (int i in array) // error C4496: nonstandard extension
                              // 'for each' used: replace with
                              // ranged-for statement:
                              // for (int i: array)
    {
        // ...
    }
}
```

#### <a name="use-of-atl-attributes"></a>ATL 특성 사용

```cpp
// Example 1
[uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]
class A {};
```

```cpp
// Fix for example 1
class __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) B {};
```

```cpp
// Example 2
[emitidl];
[module(name="Foo")];

[object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]
__interface ICustom {
    HRESULT Custom([in] longl, [out, retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out, retval] long*pLong);
};

[coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]
class CFoo : public ICustom
{};
```

```cpp
// Fix for example 2
// First, create the *.idl file. The vc140.idl generated file can be
// used to automatically obtain a *.idl file for the interfaces with
// annotation. Second, add a midl step to your build system to make
// sure that the C++ interface definitions are outputted.
// Last, adjust your existing code to use ATL directly as shown in
// the atl implementation section.

-- IDL  FILE--
import "docobj.idl";

[object, local, uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)]
interface ICustom : IUnknown {
    HRESULT Custom([in] longl, [out,retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out,retval] long*pLong);
};

[ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]
library Foo {
    importlib("stdole2.tlb");
    importlib("olepro32.dll");

    [version(1.0), appobject, uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)]
    coclass CFoo { interface ICustom; };
}

-- ATL IMPLEMENTATION--
#include <idl.header.h>
#include <atlbase.h>

class ATL_NO_VTABLE CFooImpl : public ICustom,
    public ATL::CComObjectRootEx<CComMultiThreadModel>
{
    public:BEGIN_COM_MAP(CFooImpl)
    COM_INTERFACE_ENTRY(ICustom)
    END_COM_MAP()
};
```

#### <a name="ambiguous-conditional-operator-arguments"></a>모호한 조건부 연산자 인수

버전의 Visual Studio 2017 버전 15.3 되기 전에 컴파일러에서 컴파일러는 조건부 연산자 (또는 삼항 연산자)에 대 한 인수를 수락 `?:` 표준 모호한 간주 합니다. **/ permissive-** 모드에서는 이제 컴파일러가 이전 버전에서 진단 없이 컴파일되는 경우에서 하나 이상의 진단 합니다.

이러한 변경으로 인해 발생할 수 있는 일반적인 오류는 다음과 같습니다.

- 오류 C2593: 'operator?' 모호합니다.

- 오류 C2679: 이진 '?': 오른쪽 피연산자로 형식의 사용 하는 'B' 연산자 없습니다 (또는 허용 된 변환이)

- 오류 C2678: 이진 '?': 'A' 형식의 왼쪽 피연산자를 사용 하는 연산자 없습니다 (또는 허용 된 변환이)

- 오류 C2446: ':': 'B'에서 'A'로 변환 되지 않았습니다

이 문제를 일으킬 수 있는 일반적인 코드 패턴은 일부 클래스 C 형식은 T 형식 T 다른 형식에서 비 명시적 생성자 및 비 명시적 변환 연산자를 모두 제공 하는 경우 이 경우 세 번째 인수의 형식으로 변환 하는 두 번째 인수가 두 번째 인수의 형식으로 변환 하는 세 번째 인수의 모두 유효한 변환 합니다. 둘 다 유효 하므로 표준에 따라 모호 합니다.

```cpp
// Example 1: class that provides conversion to and initialization from some type T
struct A
{
    A(int);
    operator int() const;
};

extern bool cond;

A a(42);
// Accepted when /Zc:ternary or /permissive- is not used:
auto x = cond ? 7 : a; // A: permissive behavior prefers A(7) over (int)a
// Accepted always:
auto y = cond ? 7 : int(a);
auto z = cond ? A(7) : a;
```

있는 경우 예외적이 일반적인 패턴으로 T null로 끝나는 문자열 형식 중 하나를 나타냅니다 (예를 들어 `const char *`, `const char16_t *`등) 및 실제 인수를 `?:` 문자열인 해당 형식의 리터럴. C + + 17 c++14에서 의미 체계를 변경 했습니다. 아래 예제 2의에서 코드는 허용 하는 결과적으로 **/std: c + + 14** 고에서 거부 **/std: c + + 17** 때 **/zc: ternary** 또는 **/permissive-** 사용 됩니다.

```cpp
// Example 2: exception from the above
struct MyString
{
    MyString(const char* s = "") noexcept;  // from char*
    operator const char* () const noexcept; //   to char*
};

extern bool cond;

MyString s;
// Using /std:c++14, /permissive- or /Zc:ternary behavior
// is to prefer MyString("A") over (const char*)s
// but under /std:c++17 this line causes error C2445:
auto x = cond ? "A" : s;
// You can use a static_cast to resolve the ambiguity:
auto y = cond ? "A" : static_cast<const char*>(s);
```

다른 오류가 표시 될 수 있는 경우 인수 형식 중 하나를 사용 하 여 조건부 연산자의 `void`합니다. 이 경우 같은 ASSERT 매크로에서 일반적으로 될 수 있습니다.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

템플릿 메타 프로그래밍, 조건부 연산자의 결과 형식에서 변경 될 수 있습니다 위치에서 오류를 보게 될 **/zc: ternary** 하 고 **관대 한 /-** 합니다. 사용 하는 것이 문제를 해결 하려면 단방향 [std::remove_reference](../../standard-library/remove-reference-class.md) 결과 형식입니다.

```cpp
// Example 4: different result types
extern bool cond;
extern int count;
char  a = 'A';
const char  b = 'B';
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary
```

#### <a name="two-phase-name-look-up"></a>2 단계 이름 조회

경우는 **/ permissive-** 옵션을 설정 하면 컴파일러가 식별 종속 및 종속 되지 않는 이름의 2 단계 이름 조회에 대 한 필요에 따라 템플릿에 사용 되는 함수 및 클래스 템플릿 정의 구문 분석 합니다. Visual Studio 2017 버전 15.3에서에서 이름 종속성 분석이 수행 됩니다. 특히 템플릿 정의의 컨텍스트에서 선언 되지 않은 종속 되지 않는 이름을 하면 진단 메시지가 표시 된 ISO에서 필요에 따라 C++ 표준입니다. Visual Studio 2017 버전 15.7에서에서 바인딩은 정의 컨텍스트에서 인수 종속 조회를 필요로 하는 종속 되지 않는 이름의 수행 됩니다.

```cpp
// dependent base
struct B {
    void g() {}
};

template<typename T>
struct D : T {
    void f() {
        // The call to g was incorrectly allowed in VS2017:
        g();  // Now under /permissive-: C3861
        // Possible fixes:
        // this->g();
        // T::g();
    }
};

int main()
{
    D<B> d;
    d.f();
}
```

경우 레거시 동작 2 단계 조회에 대 한 하지만 하려는 고, 그렇지 **관대 한 /-** 동작을 추가 합니다 **/zc: twophase-** 옵션입니다.

### <a name="windows-header-issues"></a>Windows 헤더 문제

**관대 한 /-** 옵션은 Windows Fall Creators 업데이트 SDK (10.0.16299.0) 하기 전에 Windows 키트의 버전 또는 Windows Driver Kit (WDK) 버전 1709에 대 한 지나치게 엄격 합니다. 사용 하려면 Windows 키트의 최신 버전으로 업데이트 하는 것이 좋습니다 **/ permissive-** Windows 또는 장치 드라이버 코드에서.

2018 Update SDK (10.0.17134.0), Windows Fall Creators 업데이트 SDK (10.0.16299.0) 또는 Windows 드라이버 키트 (WDK) 1709 Windows 4 월에 특정 헤더 파일의 사용과 호환 되지 않는 있도록 하는 문제가 있는 **/permissive-**. 이러한 문제를 해결 하려면 파일에 대해서만 소스 코드 필요 하 고 제거 하는 이러한 헤더의 사용을 제한 권장는 **생성-** 해당 특정 원본 코드 파일을 컴파일할 때 옵션입니다.

출시 이러한 WinRT WRL 헤더는 Windows 2018 년 4 월 업데이트 SDK (10.0.17134.0) 된 항목에 사용 하 여 정리 **/ permissive-** 합니다. 이러한 문제를 해결 하려면 사용 하지 **관대 한 /-** 를 사용할지 **생성-** 사용 하 여 **/zc: twophase-** 이러한 헤더를 사용 하 여 작업 하는 경우:

- Winrt/wrl/async.h 문제

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- Winrt/wrl/implements.h에서 문제 발생

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

이러한 사용자 모드 헤더 출시는 Windows 2018 년 4 월 업데이트 SDK (10.0.17134.0) 된 항목에 사용 하 여 정리 **관대 한 /-** 합니다. 이러한 문제를 해결 하려면 사용 하지 말고 **/ permissive-** 이러한 헤더를 사용 하 여 작업 하는 경우:

- Um/Tune.h 문제

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- Um/spddkhlp.h에서 문제 발생

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- Um/refptrco.h 문제

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

이러한 문제는 Windows Fall Creators 업데이트 SDK (10.0.16299.0)에서 사용자 모드 헤더에 특정 합니다.

- Um/Query.h에서 문제 발생

   사용 하는 경우는 **관대 한 /-** 컴파일러 스위치를는 `tagRESTRICTION` 구조 case(RTOr) 멤버 인해 컴파일되지 않습니다. '또는'.

   ```cpp
   struct tagRESTRICTION
   {
       ULONG rt;
       ULONG weight;
       /* [switch_is][switch_type] */ union _URes
       {
           /* [case()] */ NODERESTRICTION ar;
           /* [case()] */ NODERESTRICTION or;  // error C2059: syntax error: '||'
           /* [case()] */ NODERESTRICTION pxr;
           /* [case()] */ VECTORRESTRICTION vr;
           /* [case()] */ NOTRESTRICTION nr;
           /* [case()] */ CONTENTRESTRICTION cr;
           /* [case()] */ NATLANGUAGERESTRICTION nlr;
           /* [case()] */ PROPERTYRESTRICTION pr;
           /* [default] */  /* Empty union arm */
       } res;
   };
   ```

   이 문제를 해결 하기 위해 컴파일 없이 Query.h를 포함 하는 파일을 **관대 한 /-** 옵션입니다.

- Um/cellularapi_oem.h에서 문제 발생

   사용 하는 경우는 **관대 한 /-** 컴파일러 스위치의 정방향 선언은 `enum UICCDATASTOREACCESSMODE` 는 경고를 발생 합니다.

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   범위가 지정 되지 않은 열거형의 정방향 선언은 Microsoft 확장입니다. 이 문제를 해결 하기 위해 컴파일 없이 cellularapi_oem.h를 포함 하는 파일을 **생성-** 옵션을 사용 하거나 사용 하 여를 [/wd](compiler-option-warning-level.md) C4471 경고를 억제 하는 옵션입니다.

- Um/omscript.h에서 문제 발생

   C + + 03 BSTR 문자열 리터럴로 변환에서에서 (에 대 한 typedef 인 ' wchar_t *') 사용 되지 않지만 허용 됩니다. C++11에서 변환이 더 이상 허용 됩니다.

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   이 문제를 해결 하기 위해 컴파일 없이 omscript.h를 포함 하는 파일을 **관대 한 /-** 옵션을 사용 하거나 사용 하 여 **/Zc:strictStrings-** 대신 합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

Visual Studio 2017 버전 15.5 이상 버전에서이 절차를 따르십시오.

1. 프로젝트를 엽니다 **속성 페이지** 대화 상자.

1. 선택 된 **구성 속성** > **C /C++** > **언어** 속성 페이지.

1. 변경 된 **준수 모드** 속성 값을 **예 (관대 한 /-)**. 선택 **확인** 하거나 **적용** 변경 내용을 저장 합니다.

Visual Studio 2017 버전 15.5 이전 버전에서는이 절차를 따르십시오.

1. 프로젝트를 엽니다 **속성 페이지** 대화 상자.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 입력 합니다 **관대 한 /-** 컴파일러 옵션을 **추가 옵션** 상자. 선택 **확인** 하거나 **적용** 변경 내용을 저장 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

- [MSVC 컴파일러 옵션](compiler-options.md)
- [MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
