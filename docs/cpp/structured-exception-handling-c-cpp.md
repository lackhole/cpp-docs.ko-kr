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
ms.openlocfilehash: e948d941afa1459623619e385aa67b1c60490245
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221953"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)

구조적된 예외 처리 (SEH)는 하드웨어 오류와 같은 특정 예외 코드 상황을 정상적으로 처리 하는 C에 대 한 Microsoft 확장입니다. 하지만 Windows 및 Microsoft C++ SEH를 지원 합니다. ISO 표준을 사용 하는 것이 좋습니다 C++ 포팅 가능 하 고 유연한 코드를 했기 때문에 예외 처리 합니다. 그럼에도 불구 하 고 기존 코드를 유지 하기 위해 또는 특정 종류의 프로그램을 계속 해야 SEH를 사용 합니다.

**Microsoft 전용:**

## <a name="grammar"></a>문법

*try-except-statement* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try** *compound-statement* **__except** **(** *expression* **)** *compound-statement*

*try-finally-statement* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__try** *compound-statement* **__finally** *compound-statement*

## <a name="remarks"></a>설명

SEH를 사용 하 여 실행이 예기치 않게 종료 되는 경우 메모리 블록 및 파일과 같은 리소스가 제대로 해제를 확인할 수 있습니다. 특정 문제를 처리할 수도 있습니다-메모리가 부족 하 여 예를 들어-에 의존 하지 않는 간결한 구조의 코드나 사용 하 여 **goto** 문이나 반환 코드의 정교한 테스트 합니다.

이 문서에서 참조된 try-except 및 try-finally 문은 C 언어에 대한 Microsoft 확장입니다. 둘 다 응용 프로그램이 그렇지 않을 경우 실행을 종료하는 이벤트 후에 프로그램을 제어할 수 있도록 하여 SEH를 지원합니다. SEH는 C++ 소스 파일에서 작동하지만 C++용으로 특별히 설계된 것은 아닙니다. SEH를 사용 하는 경우는 C++ 를 사용 하 여 컴파일하는 프로그램을 [/EHa 또는 /EHsc](../build/reference/eh-exception-handling-model.md) 옵션을 소멸자 로컬 개체를 호출 했지만 다른 실행 동작은 예상과 되지 않을 수 있습니다. 예시의 경우이 문서의 뒷부분에 나오는 예제를 참조 하세요. 대부분의 경우에서 SEH 대신 것이 좋습니다 ISO 표준을 사용 하는 [ C++ 예외 처리](../cpp/try-throw-and-catch-statements-cpp.md)는 Microsoft C++ 컴파일러도 지원 합니다. C++ 예외 처리를 사용하면 코드 포팅 가능성이 향상되며 모든 형식의 예외를 처리할 수 있습니다.

C 코드 SEH를 사용 하는 경우와 함께 사용할 수 있습니다 C++ 코드를 사용 하는 C++ 예외 처리 합니다. 정보를 참조 하세요 [의 구조적된 예외 처리 C++ ](../cpp/exception-handling-differences.md)합니다.

SEH 메커니즘에는 다음 두 가지가 있습니다.

- [예외 처리기](../cpp/writing-an-exception-handler.md), 또는 **__except** 블록에 응답 하거나 예외를 해제할 수 있습니다.

- [종료 처리기](../cpp/writing-a-termination-handler.md), 또는 **__finally** 이라고 하는 항상, 여부 예외로 인해 종료 여부를 차단 합니다.

이러한 두 종류의 처리기는 별개이지만 "스택 해제"라는 프로세스를 통해 긴밀하게 연결됩니다. 구조적된 예외가 발생 하는 경우 Windows는 현재 활성 상태인 가장 최근에 설치 된 예외 처리기를 찾습니다. 처리기는 다음 세 가지 작업 중 하나를 수행할 수 있습니다.

- 예외를 인식하지 못하고 다른 처리기에 제어를 전달합니다.

- 예외를 인식하지만 해제합니다.

- 예외를 인식하고 처리합니다.

예외가 발생할 때 실행 중이던 함수에 예외를 인식하는 예외 처리기가 없을 수 있습니다. 스택의 훨씬 상위 함수에 있는 경우도 있습니다. 현재 실행 중인 함수 및 스택 프레임의 다른 모든 함수가 종료됩니다. 이 과정에서 해제 될 때 "스택이"해제 스택에서 종료 된 함수의 지역 비정적 변수, 즉 지워집니다.

스택을 해제할 때 운영 체제는 각 함수에 대해 작성된 종료 처리기를 모두 호출합니다. 종료 처리기를 사용하면 그렇지 않을 경우 비정상적인 종료 때문에 열려 있을 리소스를 정리할 수 있습니다. 중요 섹션에서 입력 한 경우에 종료 처리기에 끝낼 수 있습니다. 프로그램이 종료되는 경우 임시 파일 닫기 및 제거와 같은 기타 관리 작업을 수행할 수 있습니다.

## <a name="next-steps"></a>다음 단계

- [예외 처리기 작성](../cpp/writing-an-exception-handler.md)

- [종료 처리기 작성](../cpp/writing-a-termination-handler.md)

- [C++에서 구조적 예외 처리](../cpp/exception-handling-differences.md)

## <a name="example"></a>예제

앞에서 설명한 대로, 소멸자에 SEH를 사용 하는 경우 로컬 개체 라고에 대 한는 C++ 프로그램 및 사용 하 여 컴파일하는 **/EHa** 또는 **/EHsc** 옵션입니다. 그러나 C++ 예외도 사용하는 경우 실행 중의 동작은 예상과 다를 수 있습니다. 이 예제에서는 이러한 동작의 차이 보여 줍니다.

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

사용 하는 경우 **/EHsc** 로컬 테스트 컨트롤 매크로 하지만이 코드를 컴파일하려면 `CPPEX` 가 정의 되지 않은 실행이 없습니다의 `TestClass` 소멸자 및 보입니다 같이:

```Output
Triggering SEH exception
Executing SEH __except block
```

사용 하는 경우 **/EHsc** 코드를 컴파일하려면 코드 및 `CPPEX` 를 사용 하 여 정의 됩니다 `/DCPPEX` (있도록를 C++ 예외가 throw 됩니다), `TestClass` 소멸자가 실행 되며 출력은 다음과 같습니다.

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

사용 하는 경우 **/EHa** 코드를 컴파일하려면 합니다 `TestClass` 사용 하 여 예외를 throw 하는 여부에 관계 없이 소멸자가 실행 `std::throw` 트리거, 예외를 SEH를 사용 하 여 여부를 `CPPEX` 정의 또는 되지 않습니다. 출력은 다음과 같습니다.

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

자세한 내용은 [/EH(예외 처리 모델)](../build/reference/eh-exception-handling-model.md)를 참조하세요.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[예외 처리](../cpp/exception-handling-in-visual-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[\<exception>](../standard-library/exception.md)<br/>
[오류 및 예외 처리(모던 C++)](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[구조적된 예외 처리 (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms680657.aspx)
