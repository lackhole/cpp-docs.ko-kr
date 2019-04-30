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
ms.openlocfilehash: a55c1f2d5c2e73028b337d17b74fe1280f670707
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266786"
---
# <a name="try-throw-and-catch-statements-c"></a>Try, Throw 및 Catch 문(C++)

예외 처리를 구현 하 C++를 사용 하면 **시도**, **throw**, 및 **catch** 식.

먼저 사용 하 여는 **시도** 블록이 예외를 throw 할 수 있는 하나 이상의 문을 묶습니다.

A **throw** 식을 나타냅니다 예외 상황이-오류가 종종-에서 발생 한를 **시도** 블록입니다. 모든 형식의 개체의 피연산자로 사용할 수 있습니다는 **throw** 식입니다. 일반적으로 이 개체는 일반적으로 오류 정보를 전달하는 데 사용됩니다. 대부분의 경우에서 사용 하는 권장 합니다 [std:: exception](../standard-library/exception-class.md) 클래스 또는 표준 라이브러리에 정의 된 파생된 클래스 중 하나입니다. 그 중 하나가 적합하지 않은 경우 `std::exception`에서 사용자 고유의 예외를 파생하는 것이 좋습니다.

Throw 될 수 있는 예외를 처리 하려면 하나 이상의 구현 **catch** 바로 다음 요소를 **시도** 블록입니다. 각 **catch** 블록 처리할 수 있는 예외 형식을 지정 합니다.

이 예제는 **시도** 블록과 해당 처리기입니다. `GetNetworkResource()`가 네트워크 연결을 통해 데이터를 받고 두 개의 예외 형식은 `std::exception`에서 파생된 사용자 정의 클래스라고 가정합니다. 예외는 되었다는 **const** 에서 참조를 **catch** 문. 값으로 예외를 throw하고 상수 참조로 catch하는 것이 좋습니다.

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

## <a name="remarks"></a>설명

뒤에 코드를 합니다 **시도** 절은 코드의 보호 된 섹션입니다. 합니다 **throw** 식을 *throw*-발생-예외입니다. 뒤의 코드 블록을 **catch** 절은 예외 처리기입니다. 처리기입니다는 *catch* 오류가 throw 되는 예외 형식에는 **throw** 및 **catch** 호환 되는 합니다. 형식 일치를 제어 하는 규칙 목록은 **catch** 블록을 참조 하십시오 [방법을 Catch 블록의 평가](../cpp/how-catch-blocks-are-evaluated-cpp.md)합니다. 경우는 **catch** 문이 형식 대신 줄임표 (...)를 지정 합니다 **catch** 블록이 모든 형식의 예외를 처리 합니다. 로 컴파일할 때 합니다 [/EHa](../build/reference/eh-exception-handling-model.md) 옵션 C 구조적 예외와 메모리 보호, 0으로 나누기 및 부동 소수점 위반 등 시스템에서 생성 된 또는 응용 프로그램에서 생성 된 비동기 예외 포함할 수 있습니다 . 때문에 **catch** 블록은 일치 하는 형식을 찾기 위해 프로그램 순서 처리, 줄임표 처리기는 연결 된 마지막 처리기 여야 합니다 **시도** 블록입니다. `catch(...)`를 주의해서 사용하십시오. catch 블록이 catch되는 특정 예외를 처리하는 방법을 알고 있는 경우가 아니면 프로그램을 계속 실행하지 마십시오. 일반적으로 `catch(...)` 블록은 오류를 기록하고 프로그램 실행을 중지하기 전에 특별한 정리 작업을 수행하는 데 사용합니다.

A **throw** 식 피연산자가 없는 현재 처리 중인 예외를 다시 throw 합니다. 예외를 다시 throw할 때 원래 예외의 다형 형식 정보를 보존하므로 이 폼을 사용하는 것이 좋습니다. 이러한 식에만 사용 해야는 **catch** 처리기 또는에서 호출한 함수에는 **catch** 처리기입니다. 다시 throw된 예외 개체는 복사본이 아닌 원본 예외 개체입니다.

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

## <a name="see-also"></a>참고자료

[C++ 예외 처리](../cpp/cpp-exception-handling.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[처리되지 않은 C++ 예외](../cpp/unhandled-cpp-exceptions.md)<br/>
[__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)