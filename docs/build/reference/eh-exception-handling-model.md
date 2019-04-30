---
title: /EH(예외 처리 모델)
ms.date: 08/14/2018
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExceptionHandling
- /eh
- VC.Project.VCCLCompilerTool.ExceptionHandling
helpviewer_keywords:
- exception handling, compiler model
- cl.exe compiler, exception handling
- EH compiler option [C++]
- -EH compiler option [C++]
- /EH compiler option [C++]
ms.assetid: 754b916f-d206-4472-b55a-b6f1b0f2cb4d
ms.openlocfilehash: 9f5eed60ecb51abc1d8fbd3c38773bbf782b23a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271803"
---
# <a name="eh-exception-handling-model"></a>/EH(예외 처리 모델)

컴파일러에서 사용하는 예외 처리의 종류, 예외 검사를 최적화할 시기 및 예외로 인해 범위를 벗어나는 C++ 개체를 삭제할지 여부를 지정합니다. **/EH**를 지정하지 않으면 컴파일러에서 비동기 구조화된 예외와 C++ 예외를 catch하기 위해 코드를 사용하도록 설정하지만 비동기 예외로 인해 범위에서 벗어나게 되는 C++ 개체는 제거하지 않습니다.

## <a name="syntax"></a>구문

> **/EH**{**s**|**a**}[**c**][**r**][**-**]

## <a name="arguments"></a>인수

**a**<br/>
`catch(...)` 구문을 사용하여 비동기(구조적) 및 동기(C++) 예외를 모두 catch하는 예외 처리 모델입니다.

**s**<br/>
동기(C++) 예외만 catch하고 **extern "C"**로 선언된 함수가 예외를 throw할 수 있다고 가정하도록 컴파일러에 지시하는 예외 처리 모델입니다.

**c**<br/>
**s**(**/EHsc**)와 함께 사용하면 C++ 예외만 catch하고 **extern "C"**로 선언된 함수는 절대로 C++ 예외를 throw하지 않는다고 가정할 것을 컴파일러에게 지시합니다. **/EHca**는 **/EHa**와 같습니다.

**r**<br/>
모든에 대해 항상 런타임 종료 검사를 생성 하도록 컴파일러에 지시 **noexcept** 함수입니다. 기본적으로 런타임 검사에 대 한 **noexcept** 컴파일러만 throw 되지 않는 함수를 호출 하는 함수를 결정 하는 경우 지금 최적화 될 수 있습니다.

## <a name="remarks"></a>설명

**/EHa** 컴파일러 옵션은 네이티브 C++ `catch(...)` 절로 비동기 구조적 예외 처리(SEH)를 지원하는 데 사용됩니다. 지정 하지 않고 SEH를 구현 하려면 **/EHa**를 사용할 수 있습니다 합니다 **__try**, **__except**, 및 **__finally** 구문. 비록 Windows 및 Visual C++가 SEH를 지원하지만 이식 가능하고 유연한 코드를 만들기 위해 ISO 표준 C++ 예외 처리(**/EHs** 또는 **/EHsc**)를 사용하는 것이 좋습니다. 그럼에도 불구 하 고 기존 코드 또는 특정 종류의 프로그램-예를 들어, 공용 언어 런타임 지원 하기 위해 컴파일된 코드에서에서 ([/clr (공용 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md))-계속 해야 SEH를 사용 합니다. 자세한 내용은 [Structured Exception Handling (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)을 참조하세요.

**/EHa** 를 지정하고 `catch(...)` 를 사용하여 모든 예외를 처리하려고 하면 위험할 수 있습니다. 대부분의 경우 비동기 예외는 복구할 수 없고 치명적인 것으로 간주해야 합니다. Catch하고 진행하면 프로세스가 손상되고 찾아 수정할 수 없는 버그를 일으킬 수 있습니다.

**/EHs** 또는 **/EHsc**를 사용하는 경우 `catch(...)` 절은 비동기 구조적 예외를 catch하지 않습니다. 액세스 위반 및 관리되는 <xref:System.Exception?displayProperty=fullName> 예외가 catch되지 않고 비동기 예외가 발생할 때 비동기 예외가 처리되더라도 범위의 개체가 소멸되지 않습니다.

사용 하는 경우 **/EHa**, 이미지 클 수 있습니다 및 컴파일러 최적화 하지 않으므로 커지고 성능이 **시도** 블록을 적극적으로 합니다. 또한 컴파일러가 C++ 예외를 throw할 수 있는 모든 코드를 표시하지 않는 경우에도 모든 로컬 개체의 소멸자를 자동으로 호출하는 예외 필터를 유지합니다. 이렇게 하면 안전 스택이 C++ 예외뿐만 아니라 비동기 예외에 대해 해제됩니다. 사용 하는 경우 **/EHs**, 컴파일러 예외에만 발생할 수 있다고 가정를 **throw** 문 또는 함수 호출 합니다. 이렇게 하면 컴파일러가 해제할 수 있는 여러 개체의 수명을 추적하기 위한 코드를 제거할 수 있고 이에 따라 코드 크기가 상당히 줄어들 수 있습니다.

사용 하 여 컴파일된 개체 연결 하지 않는 것이 좋습니다 **/EHa** 사용 하 여 컴파일된 개체와 함께 **/EHs** 하거나 **/EHsc** 같은 실행 모듈에 있습니다. **/EHa** 를 사용하여 모듈의 아무 곳에서나 비동기 예외를 처리해야 할 경우 **/EHa** 를 사용하여 모듈의 모든 코드를 컴파일합니다. 구조적된 예외 처리 구문을 사용 하 여 컴파일되는 코드와 같은 모듈에서 사용할 수 있습니다 **/EHs**를 사용할 수 있지만 SEH 구문을 함께 없습니다 **시도**, **throw**, 및 **catch** 동일한 함수에서.

사용 하 여 **/EHa** 이외의 다른 방식으로 발생 하는 예외를 catch 하려는 경우를 **throw**합니다. 이 예제는 구조적 예외를 생성 및 catch합니다.

```cpp
// compiler_options_EHA.cpp
// compile with: /EHa
#include <iostream>
#include <excpt.h>
using namespace std;

void fail() {   // generates SE and attempts to catch it using catch(...)
   try {
      int i = 0, j = 1;
      j /= i;   // This will throw a SE (divide by zero).
      printf("%d", j);
   }
   catch(...) {   // catch block will only be executed under /EHa
      cout<<"Caught an exception in catch(...)."<<endl;
   }
}

int main() {
   __try {
      fail();
   }

   // __except will only catch an exception here
   __except(EXCEPTION_EXECUTE_HANDLER) {
      // if the exception was not caught by the catch(...) inside fail()
      cout << "An exception was caught in __except." << endl;
   }
}
```

**/EHc** 옵션을 사용하려면 **/EHs** 또는 **/EHa** 를 지정해야 합니다. 합니다 **/clr** 옵션 의미 **/EHa** (즉, **/clr** **/EHa** 중복 됩니다). 컴파일러 오류를 생성 하는 경우 **/EHs** 또는 **/EHsc** 후에 사용 됩니다 **/clr**합니다. 최적화는 이 동작에 영향을 미치지 않습니다. 예외가 catch되면 컴파일러는 예외와 같은 범위에 있는 개체에 대한 클래스 소멸자를 호출합니다. 예외가 catch되지 않으면 이들 소멸자는 실행되지 않습니다.

**/clr**에 따른 예외 처리 제한에 대한 자세한 내용은 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)를 참조하세요.

**-** 기호를 사용하면 옵션을 제거할 수 있습니다. 예를 들어 **/EHsc-** 로 해석 됩니다 **/EHs** **/EHc-** 와 같습니다 **/EHs**합니다.

**/EHr** 컴파일러 옵션을 갖는 모든 함수에서 런타임 종료 검사를 적용 한 **noexcept** 특성입니다. 기본적으로 런타임 검사는 컴파일러 백 엔드에서 함수가 *throw되지 않는* 함수만 호출하는 것을 확인하는 경우 최적화할 수 있습니다. throw되지 않는 함수는 예외가 throw될 수 없음을 지정하는 특성을 갖는 모든 함수입니다. 여기에 표시 된 함수 **noexcept**를 `throw()`를 `__declspec(nothrow)`, 및 **/EHc** 를 지정 하면 **extern "C"** 함수입니다. throw되지 않는 함수에는 컴파일러에서 검사에 의해 throw되지 않는 것으로 확인한 모든 함수도 포함됩니다. **/EHr-** 을 사용하여 기본값을 명시적으로 설정할 수 있습니다.

그러나 throw되지 않는 특성이 함수에 의해 예외가 throw되지 않음을 보장하지는 않습니다. 동작과 달리를 **noexcept** 함수를 MSVC 컴파일러를 사용 하 여 선언 된 함수에서 throw 된 예외가 고려 `throw()`, `__declspec(nothrow)`, 또는 **extern "C"** 정의 되지 않은 동작으로. 이러한 세 선언 특성을 사용하는 함수는 예외에 대해 런타임 종료 검사를 적용하지 않습니다. 사용할 수는 **/EHr** 이스케이프 하는 처리 되지 않은 예외에 대 한 런타임 검사를 생성 하도록 컴파일러를 강제 적용 하 여 정의 되지 않은 동작에이 쉽게 식별할 수 있도록 하는 옵션을 **noexcept** 함수입니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요 .

1. **구성 속성** > **C/C++** > **코드 생성**을 선택합니다.

1. **C++ 예외 처리 가능** 속성을 변경합니다.

   또는 **C++ 예외 처리 가능** 을 **아니요**로 설정하고, **명령줄** 속성 페이지에서, **추가 옵션** 상자에 컴파일러 옵션을 추가합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[오류 및 예외 처리(모던 C++)](../../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[예외 사양(throw)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[구조적 예외 처리(C/C++)](../../cpp/structured-exception-handling-c-cpp.md)
