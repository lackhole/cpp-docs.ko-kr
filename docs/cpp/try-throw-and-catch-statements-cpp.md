---
title: Try, Throw 및 Catch 문(C++)
ms.date: 11/04/2016
f1_keywords:
- catch_cpp
- try_cpp
- throw_cpp
helpviewer_keywords:
- catch keyword [C++]
- keywords [C++], exception handling
- C++ exception handling, statement syntax
- try-catch keyword [C++], about try-catch exception handling
- throw keyword [C++]
- try-catch keyword [C++]
- try-catch keyword [C++], exception handling
- throwing exceptions [C++], throw keyword
- try-catch keyword [C++], throw keyword [C++]s
- throwing exceptions [C++], implementing C++ exception handling
- throwing exceptions [C++]
- throw keyword [C++], throw() vs. throw(...)
ms.assetid: 15e6a87b-b8a5-4032-a7ef-946c644ba12a
ms.openlocfilehash: 31ed5f7a17b9b45dbbecf5ccb29d2b51a7635eaa
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245138"
---
# <a name="try-throw-and-catch-statements-c"></a>Try, Throw 및 Catch 문(C++)

To implement exception handling in C++, you use **try**, **throw**, and **catch** expressions.

First, use a **try** block to enclose one or more statements that might throw an exception.

A **throw** expression signals that an exceptional condition—often, an error—has occurred in a **try** block. You can use an object of any type as the operand of a **throw** expression. 일반적으로 이 개체는 일반적으로 오류 정보를 전달하는 데 사용됩니다. In most cases, we recommend that you use the [std::exception](../standard-library/exception-class.md) class or one of the derived classes that are defined in the standard library. 그 중 하나가 적합하지 않은 경우 `std::exception`에서 사용자 고유의 예외를 파생하는 것이 좋습니다.

To handle exceptions that may be thrown, implement one or more **catch** blocks immediately following a **try** block. Each **catch** block specifies the type of exception it can handle.

This example shows a **try** block and its handlers. `GetNetworkResource()`가 네트워크 연결을 통해 데이터를 받고 두 개의 예외 형식은 `std::exception`에서 파생된 사용자 정의 클래스라고 가정합니다. Notice that the exceptions are caught by **const** reference in the **catch** statement. 값으로 예외를 throw하고 상수 참조로 catch하는 것이 좋습니다.

## <a name="example"></a>예제

```cpp
MyData md;
try {
   // Code that could throw an exception
   md = GetNetworkResource();
}
catch (const networkIOException& e) {
   // Code that executes when an exception of type
   // networkIOException is thrown in the try block
   // ...
   // Log error message in the exception object
   cerr << e.what();
}
catch (const myDataFormatException& e) {
   // Code that handles another exception type
   // ...
   cerr << e.what();
}

// The following syntax shows a throw expression
MyData GetNetworkResource()
{
   // ...
   if (IOSuccess == false)
      throw networkIOException("Unable to connect");
   // ...
   if (readError)
      throw myDataFormatException("Format error");
   // ...
}
```

## <a name="remarks"></a>주의

The code after the **try** clause is the guarded section of code. The **throw** expression *throws*—that is, raises—an exception. The code block after the **catch** clause is the exception handler. This is the handler that *catches* the exception that's thrown if the types in the **throw** and **catch** expressions are compatible. For a list of rules that govern type-matching in **catch** blocks, see [How Catch Blocks are Evaluated](../cpp/how-catch-blocks-are-evaluated-cpp.md). If the **catch** statement specifies an ellipsis (...) instead of a type, the **catch** block handles every type of exception. When you compile with the [/EHa](../build/reference/eh-exception-handling-model.md) option, these can include C structured exceptions and system-generated or application-generated asynchronous exceptions such as memory protection, divide-by-zero, and floating-point violations. Because **catch** blocks are processed in program order to find a matching type, an ellipsis handler must be the last handler for the associated **try** block. `catch(...)`를 주의해서 사용하십시오. catch 블록이 catch되는 특정 예외를 처리하는 방법을 알고 있는 경우가 아니면 프로그램을 계속 실행하지 마십시오. 일반적으로 `catch(...)` 블록은 오류를 기록하고 프로그램 실행을 중지하기 전에 특별한 정리 작업을 수행하는 데 사용합니다.

A **throw** expression that has no operand re-throws the exception currently being handled. 예외를 다시 throw할 때 원래 예외의 다형 형식 정보를 보존하므로 이 폼을 사용하는 것이 좋습니다. Such an expression should only be used in a **catch** handler or in a function that's called from a **catch** handler. 다시 throw된 예외 개체는 복사본이 아닌 원본 예외 개체입니다.

```cpp
try {
   throw CSomeOtherException();
}
catch(...) {
   // Catch all exceptions - dangerous!!!
   // Respond (perhaps only partially) to the exception, then
   // re-throw to pass the exception to some other handler
   // ...
   throw;
}
```

## <a name="see-also"></a>참조

[Modern C++ best practices for exceptions and error handling](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[처리되지 않은 C++ 예외](../cpp/unhandled-cpp-exceptions.md)<br/>
[__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)