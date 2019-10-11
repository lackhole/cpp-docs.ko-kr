---
title: 링커 도구 오류 LNK2019
ms.date: 12/15/2017
f1_keywords:
- LNK2019
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
ms.openlocfilehash: 3c4e5578c7b0f496feb4d40933af624f462a31d2
ms.sourcegitcommit: 680a155cc44a38f88bb2b1c5a1ef6dcb7141c011
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2019
ms.locfileid: "72252629"
---
# <a name="linker-tools-error-lnk2019"></a>링커 도구 오류 LNK2019

'*function*' 함수에서 참조 되는 확인 되지 않은 외부 기호 '*symbol*'

컴파일된 코드 *함수* 는 *기호*에 대 한 참조 또는 호출을 만들지만 링커에 지정 된 라이브러리나 개체 파일에는 해당 기호가 정의 되어 있지 않습니다.

이 오류 메시지 다음에 심각한 오류 [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md)이 발생 합니다. 오류 LNK1120를 수정 하려면 모든 LNK2001 및 LNK2019 오류를 수정 해야 합니다.

## <a name="possible-causes"></a>가능한 원인

이 오류는 여러 가지 방법으로 가져올 수 있지만, 모든 방법에는 링커가 *확인할*수 없는 함수 또는 변수에 대 한 참조가 포함 되어 있습니다. 또는에 대 한 정의를 찾을 수 없습니다. 컴파일러가 기호가 *선언*되지 않은 경우를 식별할 수 있지만 *정의 되지 않은*경우에는 정의가 다른 소스 파일이 나 라이브러리에 있을 수 있습니다. 기호가 참조 되었지만 정의 되지 않은 경우 링커에서 확인 되지 않은 외부 기호 오류를 생성 합니다.

LNK2019를 일으키는 일반적인 문제는 다음과 같습니다.

### <a name="the-object-file-or-library-that-contains-the-definition-of-the-symbol-is-not-linked"></a>기호 정의를 포함 하는 개체 파일 또는 라이브러리가 연결 되어 있지 않습니다.

Visual Studio에서 정의가 포함 된 소스 파일이 빌드되고 프로젝트의 일부로 연결 되어 있는지 확인 합니다. 명령줄에서 정의를 포함 하는 소스 파일을 컴파일하고 결과 개체 파일이 연결할 파일 목록에 포함 되어 있는지 확인 합니다.

### <a name="the-declaration-of-the-symbol-is-not-spelled-the-same-as-the-definition-of-the-symbol"></a>기호 선언의 철자가 기호 정의와 동일 하지 않습니다.

선언과 정의 모두에 올바른 철자 및 대/소문자가 사용 되는지 확인 하 고 기호를 사용 하거나 호출할 때마다를 사용 합니다.

### <a name="a-function-is-used-but-the-type-or-number-of-the-parameters-do-not-match-the-function-definition"></a>함수가 사용 되지만 매개 변수의 형식이 나 개수가 함수 정의와 일치 하지 않습니다.

함수 선언은 정의와 일치해야 합니다. 함수 호출이 선언과 일치하며 선언이 정의와 일치하는지 확인하세요. 또한 템플릿 함수를 호출하는 코드에는 정의와 같은 템플릿 매개 변수가 포함되는 일치하는 템플릿 함수 선언이 있어야 합니다. 템플릿 선언 불일치에 대 한 예제는 예제 섹션에서 sample LNK2019e를 참조 하세요.

### <a name="a-function-or-variable-is-declared-but-not-defined"></a>함수 또는 변수가 선언 되었지만 정의 되지 않았습니다.

이는 일반적으로 선언이 헤더 파일에 있지만 일치 하는 정의가 구현 되지 않음을 의미 합니다. 멤버 함수 또는 정적 데이터 멤버의 경우 구현에 클래스 범위 선택기가 포함되어야 합니다. 예제를 보려면 [Missing Function Body or Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md)를 참조하십시오.

### <a name="the-calling-convention-is-different-between-the-function-declaration-and-the-function-definition"></a>함수 선언과 함수 정의 간에 호출 규칙이 다릅니다.

호출 규칙([__cdecl](../../cpp/cdecl.md), [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md)또는 [__vectorcall](../../cpp/vectorcall.md))은 트데코레이된 이름의 일부로써 인코딩됩니다. 호출 규칙이 동일한지 확인하세요.

### <a name="a-symbol-is-defined-in-a-c-file-but-declared-without-using-extern-c-in-a-c-file"></a>기호가 C 파일에 정의 되어 있지만 C++ 파일에서 Extern "C"를 사용 하지 않고 선언 되었습니다.

[extern "C"](../../cpp/using-extern-to-specify-linkage.md) 한정자를 사용하는 경우를 제외하고, C로 컴파일된 파일에 정의된 기호에 C++ 파일에 선언된 기호와 다른 트데코레이된 이름이 있습니다. 선언이 각 기호의 컴파일 링크와 일치하는지 확인하세요. 마찬가지로, C 프로그램에서 사용할 기호를 C++ 파일에서 정의하는 경우 정의에 `extern "C"` 을 사용하세요.

### <a name="a-symbol-is-defined-as-static-and-then-later-referenced-outside-the-file"></a>기호는 정적으로 정의 된 후 나중에 파일 외부에서 참조 됩니다.

C와 달리 C++에서는 [전역 상수](../../error-messages/tool-errors/global-constants-in-cpp.md) 에 `static` 링크가 있습니다. 이 제한을 해결하기 위해 헤더 파일에 `const` 초기화를 포함하고 .cpp 파일에 해당 헤더를 포함하거나, 변수를 비상수로 만들고 상수 참조를 사용하여 액세스할 수 있습니다.

### <a name="a-static-member-of-a-class-is-not-defined"></a>클래스의 정적 멤버가 정의 되지 않았습니다.

정적 클래스 멤버에는 고유한 정의가 있어야 합니다. 그렇지 않으면 단일 정의 규칙을 위반하게 됩니다. 인라인으로 정의될 수 없는 정적 클래스 멤버는 정규화된 이름을 사용하여 한 소스 파일에 정의되어야 합니다. 전혀 정의되지 않은 경우 링커는 LNK2019를 생성합니다.

### <a name="a-build-dependency-is-only-defined-as-a-project-dependency-in-the-solution"></a>빌드 종속성은 솔루션의 프로젝트 종속성 으로만 정의 됩니다.

이전 버전의 Visual Studio에서는이 수준의 종속성이 충분 했습니다. 그러나 visual Studio 2010부터 Visual Studio에 [프로젝트 간 참조가](/visualstudio/ide/managing-references-in-a-project)필요 합니다. 프로젝트에 프로젝트 간 참조가 없는 경우 이 링커 오류가 발생할 수 있습니다. 프로젝트 간 참조를 추가하여 오류를 해결하세요.

### <a name="an-entry-point-is-not-defined"></a>진입점이 정의 되지 않았습니다.

응용 프로그램 코드는 적절 한 진입점을 정의 해야 합니다. `main` 또는 콘솔 응용 프로그램의 경우-1, Windows 응용 프로그램의 경우 `WinMain` 또는 `wWinMain` @no__t 합니다. 자세한 내용은 [main을 참조 하세요. Program Startup @ no__t-0 또는 [WinMain 함수](/windows/win32/api/winbase/nf-winbase-winmain) 사용자 지정 진입점을 사용 하려면 [/entry (진입점 기호)](../../build/reference/entry-entry-point-symbol.md) 링커 옵션을 지정 합니다. 

### <a name="you-build-a-console-application-by-using-settings-for-a-windows-application"></a>Windows 응용 프로그램에 대 한 설정을 사용 하 여 콘솔 응용 프로그램을 빌드합니다.

오류 메시지가 **함수 function_name에서 참조 되는 확인 되지 않은 외부 기호 WinMain**과 비슷한 경우 **/SUBSYSTEM: WINDOWS**대신 **/SUBSYSTEM: CONSOLE** 을 사용 하 여 연결 합니다. 이 설정에 대한 자세한 내용과 Visual Studio에서 이 속성을 설정하는 방법에 대한 지침은 [/SUBSYSTEM (Specify Subsystem)](../../build/reference/subsystem-specify-subsystem.md)을 참조하세요.

### <a name="you-attempt-to-link-64-bit-libraries-to-32-bit-code-or-32-bit-libraries-to-64-bit-code"></a>32 비트 코드에 64 비트 라이브러리를 연결 하거나 32 비트 라이브러리를 64 비트 코드로 연결 하려고 합니다.

코드에 연결 된 라이브러리 및 개체 파일은 코드와 동일한 아키텍처에 대해 컴파일되어야 합니다. 프로젝트에서 참조 하는 라이브러리가 프로젝트와 동일한 아키텍처에 대해 컴파일되는지 확인 합니다. 링커에서 사용 하는 [/libpath](../../build/reference/libpath-additional-libpath.md) 또는 **추가 라이브러리 디렉터리** 경로 옵션이 올바른 아키텍처용 라이브러리를 가리키는지 확인 합니다.

### <a name="you-use-different-compiler-options-for-function-inlining-in-different-source-files"></a>다른 소스 파일의 함수 인라이닝에 대해 여러 컴파일러 옵션을 사용 합니다.

여러 소스 파일에서 .cpp 파일에 정의된 인라인된 함수를 사용하고 함수 인라이닝 컴파일러 옵션을 혼합하면 LNK2019가 발생할 수 있습니다. 자세한 내용은 [Function Inlining Problems](../../error-messages/tool-errors/function-inlining-problems.md)을 참조하세요.

### <a name="you-use-automatic-variables-outside-their-scope"></a>범위 밖의 자동 변수를 사용 합니다.

자동(함수 범위) 변수는 해당 함수의 범위 내에서만 사용할 수 있습니다. 이러한 변수는 `extern` 으로 선언할 수 없으며 다른 소스 파일에서 사용할 수 없습니다. 예제를 보려면 [Automatic (Function Scope) Variables](../../error-messages/tool-errors/automatic-function-scope-variables.md)를 참조하십시오.

### <a name="you-call-instrinsic-functions-or-pass-argument-types-to-intrinsic-functions-that-are-not-supported-on-your-target-architecture"></a>내장 함수를 호출 하거나 대상 아키텍처에서 지원 되지 않는 내장 함수에 인수 형식을 전달 합니다.

예들 들어 AVX2 내장 함수를 사용하지만 [/ARCH:AVX2](../../build/reference/arch-x86.md) 컴파일러 옵션을 지정하지 않은 경우, 컴파일러는 내장 함수가 외부 함수라고 가정합니다. 인라인 명령을 생성하는 대신 컴파일러는 내장 함수와 같은 이름의 외부 기호에 대해 호출을 생성합니다. 링커가 이 누락된 함수의 정의를 찾으려고 할 때 LNK2019가 생성됩니다. 대상 아키텍처에서 지원하는 내장 함수 및 형식만 사용하는지 확인하세요.

### <a name="you-mix-code-that-uses-native-wchar_t-with-code-that-doesnt"></a>네이티브 wchar @ no__t-0t를 사용 하는 코드를

C++Visual Studio 2005에서 수행한 언어 규칙 작업은 기본적으로 네이티브 형식 @no__t. 이전 버전의 Visual Studio를 사용 하 여 컴파일된 라이브러리 및 개체 파일과 호환 되는 코드를 생성 하려면 [/zc: wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 컴파일러 옵션을 사용 해야 합니다. 모든 파일이 동일한 **/zc: wchar @ no__t-1t** 설정을 사용 하 여 컴파일되지 않은 경우 형식 참조가 호환 되는 형식으로 확인 되지 않을 수 있습니다. 사용된 형식을 업데이트하거나 컴파일할 때 일관된 `wchar_t` 설정을 사용하여 모든 라이브러리 및 개체 파일의 **/Zc:wchar_t** 형식이 호환되는지 확인하세요.

## <a name="third-party-library-issues-and-vcpkg"></a>타사 라이브러리 문제 및 Vcpkg

빌드의 일부로 타사 라이브러리를 구성 하려고 할 때이 오류가 표시 되 면 Visual C++ 패키지 관리자 인 [Vcpkg](../../vcpkg.md)을 사용 하 여 라이브러리를 설치 하 고 빌드합니다. Vcpkg는 크고 증가 하는 [타사 라이브러리 목록을](https://github.com/Microsoft/vcpkg/tree/master/ports)지원 하 고 프로젝트의 일부로 성공한 빌드에 필요한 모든 구성 속성 및 종속성을 설정 합니다. 자세한 내용은 관련 [시각적 C++ 블로그](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) 게시물을 참조 하세요.

## <a name="diagnosis-tools"></a>진단 도구

링커가 특정 기호 정의를 찾을 수 없는 이유는 확인하기 어려울 수 있습니다. 빌드에 정의를 포함 하는 코드를 포함 하지 않았거나, 빌드 옵션에서 외부 기호에 대해 서로 다른 데코레이팅된 이름을 만든 경우 문제가 종종 발생 합니다. LNK2019 오류를 진단하는데 도움이 되는 여러 가지 도구 및 옵션이 있습니다.

- [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) 링커 옵션은 링커가 참조하는 파일을 확인하는데 도움이 될 수 있습니다. 기호 정의를 포함하는 파일이 빌드에 포함되어 있는지 여부를 확인할 수 있습니다.

- **DUMPBIN** 유틸리티의 [/Proerand](../../build/reference/dash-exports.md) [/SYMBOLS](../../build/reference/symbols.md) 옵션은 .dll 및 개체 또는 라이브러리 파일에 정의 된 기호를 찾는 데 도움이 될 수 있습니다. 내보낸 트데코레이된 이름이 링커가 검색하는 트데코레이된 이름과 일치하는지 확인하세요.

- **Undname.exe** 유틸리티는 데코레이팅된 이름에 해당 하는 데코레이팅되지 않은 외부 기호를 표시할 수 있습니다.

## <a name="examples"></a>예

LNK2019 오류를 해결하는 방법에 대한 정보와 함께, LNK2019 오류를 유발하는 여러 가지 코드 예제는 다음과 같습니다.

### <a name="a-symbol-is-declared-but-not-defined"></a>기호가 선언되었지만 정의되지 않았습니다.

이 예에서는 외부 변수가 선언 되었지만 정의 되지 않았습니다.

```cpp
// LNK2019.cpp
// Compile by using: cl /EHsc /W4 LNK2019.cpp
// LNK2019 expected
extern char B[100];   // B is not available to the linker
int main() {
   B[0] = ' ';   // LNK2019
}
```

변수 및 함수를 `extern`으로 선언 했지만 정의가 제공 되지 않는 또 다른 예는 다음과 같습니다.

```cpp
// LNK2019c.cpp
// Compile by using: cl /EHsc LNK2019c.cpp
// LNK2019 expected
extern int i;
extern void g();
void f() {
   i++;
   g();
}
int main() {}
```

@No__t-0 및 `g`이 빌드에 포함 된 파일 중 하나에 정의 되어 있지 않으면 링커가 LNK2019를 생성 합니다. 컴파일의 일부로써 정의를 포함하는 소스 코드 파일을 포함하여 오류를 해결할 수 있습니다. 또는 링커에 대 한 정의를 포함 하는 .obj 파일 또는 .lib 파일을 전달할 수 있습니다.

### <a name="a-static-data-member-is-declared-but-not-defined"></a>정적 데이터 멤버가 선언되었지만 정의되지 않았습니다.

정적 데이터 멤버가 선언되었지만 정의되지 않은 경우에도 LNK2019가 발생할 수 있습니다. 다음 샘플에서는 LNK2019가 생성되며 해결 방법을 보여 줍니다.

```cpp
// LNK2019b.cpp
// Compile by using: cl /EHsc LNK2019b.cpp
// LNK2019 expected
struct C {
   static int s;
};

// Uncomment the following line to fix the error.
// int C::s;

int main() {
   C c;
   C::s = 1;
}
```

### <a name="declaration-parameters-do-not-match-definition"></a>선언 매개 변수가 정의와 일치하지 않습니다.

템플릿 함수를 호출하는 코드에는 일치하는 템플릿 함수 선언이 있어야 합니다. 선언에는 정의와 동일한 템플릿 매개 변수가 포함되어야 합니다. 다음 샘플에서는 사용자 정의 연산자에 LNK2019가 생성되고 해결 방법을 보여 줍니다.

```cpp
// LNK2019e.cpp
// compile by using: cl /EHsc LNK2019e.cpp
// LNK2019 expected
#include <iostream>
using namespace std;

template<class T> class
Test {
   // The operator<< declaration does not match the definition below:
   friend ostream& operator<<(ostream&, Test&);
   // To fix, replace the line above with the following:
   // template<typename T> friend ostream& operator<<(ostream&, Test<T>&);
};

template<typename T>
ostream& operator<<(ostream& os, Test<T>& tt) {
   return os;
}

int main() {
   Test<int> t;
   cout << "Test: " << t << endl;   // LNK2019 unresolved external
}
```

### <a name="inconsistent-wchar_t-type-definitions"></a>일관성 없는 wchar_t 형식 정의

이 샘플에서는 `wchar_t`로 확인 되는 `WCHAR`을 사용 하는 내보내기가 있는 DLL을 만듭니다.

```cpp
// LNK2019g.cpp
// compile with: cl /EHsc /LD LNK2019g.cpp
#include "windows.h"
// WCHAR resolves to wchar_t
__declspec(dllexport) void func(WCHAR*) {}
```

다음 샘플은 이전 샘플에서 DLL을 사용 하 고 unsigned short *와 WCHAR @ no__t-0 형식이 동일 하지 않으므로 LNK2019를 생성 합니다.

```cpp
// LNK2019h.cpp
// compile by using: cl /EHsc LNK2019h LNK2019g.lib
// LNK2019 expected
__declspec(dllimport) void func(unsigned short*);

int main() {
   func(0);
}
```

이 오류를 해결 하려면 `unsigned short`을 `wchar_t` 또는 `WCHAR`로 변경 하거나 **/zc: wchar_t-** 를 사용 하 여 LNK2019g를 컴파일합니다.

## <a name="additional-resources"></a>추가 자료

LNK2001에 대 한 가능한 원인 및 해결 방법에 대 한 자세한 내용은 Stack Overflow 질문: [정의 되지 않은 참조/확인 되지 않은 외부 기호 오류 및 해결 방법](https://stackoverflow.com/q/12573816/2002113)을 참조 하세요.

