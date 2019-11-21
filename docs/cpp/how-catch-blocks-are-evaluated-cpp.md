---
title: Catch 블록 평가 방법 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
ms.openlocfilehash: 027dc87923a588ea891dbf6dd835e2baba75a1cb
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245850"
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Catch 블록 평가 방법 (C++)

일반적으로 std::exception에서 파생되는 형식을 throw할 것을 권장하지만 C++를 사용하면 모든 형식의 예외를 throw할 수 있습니다. A C++ exception can be caught by a **catch** handler that specifies the same type as the thrown exception, or by a handler that can catch any type of exception.

throw된 예외의 형식이 하나의 기본 클래스 또는 여러 개의 클래스를 가진 클래스인 경우 예외 형식의 기본 클래스 및 예외 형식의 기본에 대한 참조를 허용하는 처리기로 catch할 수 있습니다. 예외가 참조에 의해 catch될 때 실제 throw된 예외 개체에 바인딩됩니다. 바인딩되지 않는 예외는 복사본입니다(함수에 대한 인수와 동일).

When an exception is thrown, it may be caught by the following types of **catch** handlers:

- 줄임표 구문을 사용하여 모든 형식을 받아들일 수 있는 처리기.

- A handler that accepts the same type as the exception object; because it is a copy, **const** and **volatile** modifiers are ignored.

- 예외 개체와 동일한 형식에 대한 참조를 허용하는 처리기.

- A handler that accepts a reference to a **const** or **volatile** form of the same type as the exception object.

- A handler that accepts a base class of the same type as the exception object; since it is a copy, **const** and **volatile** modifiers are ignored. The **catch** handler for a base class must not precede the **catch** handler for the derived class.

- 예외 개체와 동일한 형식의 기본 클래스에 대한 참조를 허용하는 처리기.

- A handler that accepts a reference to a **const** or **volatile** form of a base class of the same type as the exception object.

- throw된 포인터 개체가 표준 포인터 변환 규칙을 통해 변환될 수 있는 대상 포인터를 허용하는 처리기.

The order in which **catch** handlers appear is significant, because handlers for a given **try** block are examined in order of their appearance. 예를 들어 파생 클래스의 처리기 앞에 기본 클래스의 처리기를 배치하면 오류가 발생합니다. After a matching **catch** handler is found, subsequent handlers are not examined. As a result, an ellipsis **catch** handler must be the last handler for its **try** block. 예를 들어 다음과 같은 가치를 제공해야 합니다.

```cpp
// ...
try
{
    // ...
}
catch( ... )
{
    // Handle exception here.
}
// Error: the next two handlers are never examined.
catch( const char * str )
{
    cout << "Caught exception: " << str << endl;
}
catch( CExcptClass E )
{
    // Handle CExcptClass exception here.
}
```

In this example, the ellipsis **catch** handler is the only handler that is examined.

## <a name="see-also"></a>참조

[Modern C++ best practices for exceptions and error handling](../cpp/errors-and-exception-handling-modern-cpp.md)