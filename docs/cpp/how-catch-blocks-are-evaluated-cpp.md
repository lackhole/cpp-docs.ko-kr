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
ms.openlocfilehash: 7504439c565d4dfb720bc2fa7e097e3230733423
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153686"
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Catch 블록 평가 방법 (C++)

일반적으로 std::exception에서 파생되는 형식을 throw할 것을 권장하지만 C++를 사용하면 모든 형식의 예외를 throw할 수 있습니다. C++ 에서 예외를 낼 수 있습니다는 **catch** throw 된 예외 또는 모든 형식의 예외를 catch 할 수 있는 처리기에서 동일한 형식을 지정 하는 처리기.

throw된 예외의 형식이 하나의 기본 클래스 또는 여러 개의 클래스를 가진 클래스인 경우 예외 형식의 기본 클래스 및 예외 형식의 기본에 대한 참조를 허용하는 처리기로 catch할 수 있습니다. 예외가 참조에 의해 catch될 때 실제 throw된 예외 개체에 바인딩됩니다. 바인딩되지 않는 예외는 복사본입니다(함수에 대한 인수와 동일).

예외가 throw 되 면 다음 형식에 따라 걸러 질 수 있습니다 **catch** 처리기:

- 줄임표 구문을 사용하여 모든 형식을 받아들일 수 있는 처리기.

- 예외 개체와 동일한 형식을 허용 하는 처리기 에 복사본 이므로 **const** 하 고 **volatile** 한정자가 무시 됩니다.

- 예외 개체와 동일한 형식에 대한 참조를 허용하는 처리기.

- 에 대 한 참조를 허용 하는 처리기를 **const** 또는 **volatile** 형식의 예외 개체와 동일한 형식입니다.

- 예외 개체와 동일한 형식의 기본 클래스를 허용 하는 처리기 에 복사본 이므로 **상수** 및 **volatile** 한정자가 무시 됩니다. 합니다 **catch** 기본 클래스에 대 한 처리기를 붙이지 해야 합니다 **catch** 파생된 클래스에 대 한 처리기입니다.

- 예외 개체와 동일한 형식의 기본 클래스에 대한 참조를 허용하는 처리기.

- 에 대 한 참조를 허용 하는 처리기를 **상수** 또는 **volatile** 예외 개체와 동일한 형식의 기본 클래스의 형식입니다.

- throw된 포인터 개체가 표준 포인터 변환 규칙을 통해 변환될 수 있는 대상 포인터를 허용하는 처리기.

순서 **catch** 처리기 중요는 표시 하기 때문에 대 한 처리기를 지정 **시도** 블록 표시 되는 순서 대로 검사 됩니다. 예를 들어 파생 클래스의 처리기 앞에 기본 클래스의 처리기를 배치하면 오류가 발생합니다. 일치 하는 **catch** 처리기가 발견, 면 처리기 검사 하지 않습니다. 결과적으로 줄임표가 **catch** 처리기의 마지막 처리기 여야 합니다 해당 **시도** 블록입니다. 예를 들어:

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

이 예제에서는 줄임표 **catch** 처리기를 검사 하는 유일한 처리기입니다.

## <a name="see-also"></a>참고자료

[C++ 예외 처리](../cpp/cpp-exception-handling.md)