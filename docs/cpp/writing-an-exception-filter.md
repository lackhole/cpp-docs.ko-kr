---
title: 예외 필터 작성
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [C++], filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
ms.openlocfilehash: aaf0dc77207399d7c6be86127d7decf03895ced5
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245982"
---
# <a name="writing-an-exception-filter"></a>예외 필터 작성

예외 처리기의 수준으로 이동하거나 계속 실행하여 예외를 처리할 수 있습니다. Instead of using the exception handler code to handle the exception and falling through, you can use *filter* to clean up the problem and then, by returning -1, resume normal flow without clearing the stack.

> [!NOTE]
>  일부 예외는 계속할 수 없습니다. If *filter* evaluates to -1 for such an exception, the system raises a new exception. When you call [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception), you determine whether the exception will continue.

For example, the following code uses a function call in the *filter* expression: this function handles the problem and then returns -1 to resume normal flow of control:

```cpp
// exceptions_Writing_an_Exception_Filter.cpp
#include <windows.h>
int main() {
   int Eval_Exception( int );

   __try {}

   __except ( Eval_Exception( GetExceptionCode( ))) {
      ;
   }

}
void ResetVars( int ) {}
int Eval_Exception ( int n_except ) {
   if ( n_except != STATUS_INTEGER_OVERFLOW &&
      n_except != STATUS_FLOAT_OVERFLOW )   // Pass on most exceptions
   return EXCEPTION_CONTINUE_SEARCH;

   // Execute some code to clean up problem
   ResetVars( 0 );   // initializes data to 0
   return EXCEPTION_CONTINUE_EXECUTION;
}
```

It is a good idea to use a function call in the *filter* expression whenever *filter* needs to do anything complex. 식을 계산하면 함수가 실행됩니다. 이 경우에는 `Eval_Exception`입니다.

Note the use of [GetExceptionCode](/windows/win32/Debug/getexceptioncode) to determine the exception. 필터 자체 내에서 이 함수를 호출해야 합니다. `Eval_Exception` cannot call `GetExceptionCode`, but it must have the exception code passed to it.

이 처리기는 예외가 정수 또는 부동 소수점 오버플로가 아닌 경우 제어를 다른 처리기에 전달합니다. 그럴 경우 처리기는 함수(`ResetVars`가 유일한 예이며, API 함수가 아님)를 호출하여 일부 전역 변수를 다시 설정합니다. *Statement-block-2*, which in this example is empty, can never be executed because `Eval_Exception` never returns EXCEPTION_EXECUTE_HANDLER (1).

함수 호출 사용은 복잡한 필터 식을 처리하는 좋은 일반 용도의 기술입니다. 유용한 두 개의 다른 C 언어 기능은 다음과 같습니다.

- 조건 연산자

- 쉼표 연산자

조건 연산자는 특정 반환 코드를 검사한 다음 서로 다른 두 값 중 하나를 반환하는 데 사용될 수 있기 때문에 대개 유용합니다. For example, the filter in the following code recognizes the exception only if the exception is STATUS_INTEGER_OVERFLOW:

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {
```

다음 코드는 동일한 결과를 생성하므로 이 경우 조건 연산자의 목적은 선명도를 제공하는 것입니다.

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {
```

The conditional operator is more useful in situations where you might want the filter to evaluate to -1, EXCEPTION_CONTINUE_EXECUTION.

쉼표 연산자를 사용하면 단일 식 내의 여러 독립적인 연산을 수행할 수 있습니다. 여러 문을 실행한 다음 마지막 식의 값을 반환하는 효과와 대체로 비슷합니다. 예를 들어 다음 코드는 예외 코드를 변수에 저장한 다음 테스트합니다.

```cpp
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )
```

## <a name="see-also"></a>참조

[Writing an exception handler](../cpp/writing-an-exception-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)