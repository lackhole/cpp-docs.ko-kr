---
title: Structured Exception Handling (C/C++)
ms.date: 08/14/2018
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
ms.openlocfilehash: 942a7e48e4315454476bfe93c68169f461b006b2
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245124"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)

Structured exception handling (SEH) is a Microsoft extension to C to handle certain exceptional code situations, such as hardware faults, gracefully. Although Windows and Microsoft C++ support SEH, we recommend that you use ISO-standard C++ exception handling because it makes your code more portable and flexible. Nevertheless, to maintain existing code or for particular kinds of programs, you still might have to use SEH.

**Microsoft specific:**

## <a name="grammar"></a>문법

*try-except-statement* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *compound-statement* **__except** **(** *expression* **)** *compound-statement*

*try-finally-statement* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__try** *compound-statement* **__finally** *compound-statement*

## <a name="remarks"></a>주의

With SEH, you can ensure that resources such as memory blocks and files are released correctly if execution unexpectedly terminates. You can also handle specific problems—for example, insufficient memory—by using concise structured code that does not rely on **goto** statements or elaborate testing of return codes.

이 문서에서 참조된 try-except 및 try-finally 문은 C 언어에 대한 Microsoft 확장입니다. 둘 다 애플리케이션이 그렇지 않을 경우 실행을 종료하는 이벤트 후에 프로그램을 제어할 수 있도록 하여 SEH를 지원합니다. SEH는 C++ 소스 파일에서 작동하지만 C++용으로 특별히 설계된 것은 아닙니다. If you use SEH in a C++ program that you compile by using the [/EHa or /EHsc](../build/reference/eh-exception-handling-model.md) option, destructors for local objects are called but other execution behavior might not be what you expect. For an illustration, see the example later in this article. In most cases, instead of SEH we recommend that you use ISO-standard [C++ exception handling](../cpp/try-throw-and-catch-statements-cpp.md), which the Microsoft C++ compiler also supports. C++ 예외 처리를 사용하면 코드 포팅 가능성이 향상되며 모든 형식의 예외를 처리할 수 있습니다.

If you have C code that uses SEH, you can mix it with C++ code that uses C++ exception handling. For information, see [Handle structured exceptions in C++](../cpp/exception-handling-differences.md).

SEH 메커니즘에는 다음 두 가지가 있습니다.

- [Exception handlers](../cpp/writing-an-exception-handler.md), or **__except** blocks, which can respond to or dismiss the exception.

- [Termination handlers](../cpp/writing-a-termination-handler.md), or **__finally** blocks, which are always called, whether an exception causes termination or not.

이러한 두 종류의 처리기는 별개이지만 "스택 해제"라는 프로세스를 통해 긴밀하게 연결됩니다. When a structured exception occurs, Windows looks for the most recently installed exception handler that is currently active. 처리기는 다음 세 가지 작업 중 하나를 수행할 수 있습니다.

- 예외를 인식하지 못하고 다른 처리기에 제어를 전달합니다.

- 예외를 인식하지만 해제합니다.

- 예외를 인식하고 처리합니다.

예외가 발생할 때 실행 중이던 함수에 예외를 인식하는 예외 처리기가 없을 수 있습니다. 스택의 훨씬 상위 함수에 있는 경우도 있습니다. 현재 실행 중인 함수 및 스택 프레임의 다른 모든 함수가 종료됩니다. During this process, the stack is "unwound;" that is, local non-static variables of terminated functions are cleared from the stack.

스택을 해제할 때 운영 체제는 각 함수에 대해 작성된 종료 처리기를 모두 호출합니다. 종료 처리기를 사용하면 그렇지 않을 경우 비정상적인 종료 때문에 열려 있을 리소스를 정리할 수 있습니다. If you've entered a critical section, you can exit it in the termination handler. 프로그램이 종료되는 경우 임시 파일 닫기 및 제거와 같은 기타 관리 작업을 수행할 수 있습니다.

## <a name="next-steps"></a>다음 단계

- [Writing an exception handler](../cpp/writing-an-exception-handler.md)

- [Writing a termination handler](../cpp/writing-a-termination-handler.md)

- [C++에서 구조적 예외 처리](../cpp/exception-handling-differences.md)

## <a name="example"></a>예제

As stated earlier, destructors for local objects are called if you use SEH in a C++ program and compile it by using the **/EHa** or **/EHsc** option. 그러나 C++ 예외도 사용하는 경우 실행 중의 동작은 예상과 다를 수 있습니다. This example demonstrates these behavioral differences.

```cpp
#include <stdio.h>
#include <Windows.h>
#include <exception>

class TestClass
{
public:
    ~TestClass()
    {
        printf("Destroying TestClass!\r\n");
    }
};

__declspec(noinline) void TestCPPEX()
{
#ifdef CPPEX
    printf("Throwing C++ exception\r\n");
    throw std::exception("");
#else
    printf("Triggering SEH exception\r\n");
    volatile int *pInt = 0x00000000;
    *pInt = 20;
#endif
}

__declspec(noinline) void TestExceptions()
{
    TestClass d;
    TestCPPEX();
}

int main()
{
    __try
    {
        TestExceptions();
    }
    __except(EXCEPTION_EXECUTE_HANDLER)
    {
        printf("Executing SEH __except block\r\n");
    }

    return 0;
}
```

If you use **/EHsc** to compile this code but the local test control macro `CPPEX` is undefined, there is no execution of the `TestClass` destructor and the output looks like this:

```Output
Triggering SEH exception
Executing SEH __except block
```

If you use **/EHsc** to compile the code and `CPPEX` is defined by using `/DCPPEX` (so that a C++ exception is thrown), the `TestClass` destructor executes and the output looks like this:

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

If you use **/EHa** to compile the code, the `TestClass` destructor executes regardless of whether the exception was thrown by using `std::throw` or by using SEH to trigger the exception, that is, whether `CPPEX` defined or not. 출력은 다음과 같습니다.

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

자세한 내용은 [/EH(예외 처리 모델)](../build/reference/eh-exception-handling-model.md)를 참조하세요.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[예외 처리](../cpp/exception-handling-in-visual-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[\<exception>](../standard-library/exception.md)<br/>
[Errors and Exception Handling](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Structured Exception Handling (Windows)](/windows/win32/debug/structured-exception-handling)
