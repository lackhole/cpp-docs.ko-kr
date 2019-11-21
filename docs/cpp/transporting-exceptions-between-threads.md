---
title: 스레드 간 예외 전송
ms.date: 05/07/2019
helpviewer_keywords:
- std::current_exception
- transporting exceptions between threads
- std::copy_exception
- exception_ptr
- std::exception_ptr
- std::rethrow_exception
- current_exception
- transport exceptions between threads
- copy_exception
- rethrow_exception
- move exceptions between threads
ms.assetid: 5c95d57b-acf5-491f-8122-57c5df0edd98
ms.openlocfilehash: 25b09c508b932a4d1470f6b23f03aa52e62c68cc
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246305"
---
# <a name="transporting-exceptions-between-threads"></a>스레드 간 예외 전송

The Microsoft C++ compiler (MSVC) supports *transporting an exception* from one thread to another. 예외 전송으로 하나의 스레드에서 예외를 잡아내어 다른 스레드에서 예외가 throw되어 나타나도록 합니다. 예를 들어, 이 기능을 사용하여 기본 스레드가 보조 스레드에서 throw되는 모든 예외를 처리하는 위치에 있는 다중 스레드 애플리케이션을 작성할 수 있습니다. 예외 전송 병렬 프로그래밍 라이브러리를 만들거나 시스템 개발자에 주로 유용합니다. To implement transporting exceptions, MSVC provides the [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) type and the [current_exception](../standard-library/exception-functions.md#current_exception), [rethrow_exception](../standard-library/exception-functions.md#rethrow_exception), and [make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr) functions.

## <a name="syntax"></a>구문

```cpp
namespace std
{
   typedef unspecified exception_ptr;
   exception_ptr current_exception();
   void rethrow_exception(exception_ptr p);
   template<class E>
       exception_ptr make_exception_ptr(E e) noexcept;
}
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*unspecified*|`exception_ptr` 형식을 구현하는 데 사용되는 지정되지 않은 내부 클래스입니다.|
|*p*|예외를 참조하는 `exception_ptr` 개체입니다.|
|*E*|예외를 나타내는 클래스입니다.|
|*e*|매개 변수 `E` 클래스의 인스턴스입니다.|

## <a name="return-value"></a>반환 값

`current_exception` 함수는 현재 진행 중인 예외를 참조하는 `exception_ptr` 개체를 반환합니다. 예외가 진행 중인 경우에 함수는 어떤 예외와도 관련되지 않은 `exception_ptr` 개체를 반환합니다.

The `make_exception_ptr` function returns an `exception_ptr` object that references the exception specified by the *e* parameter.

## <a name="remarks"></a>주의

### <a name="scenario"></a>시나리오

확장을 통해 변하는 작업량을 처리할 수 있는 애플리케이션을 만들려는 경우를 가정합니다. 이 목적을 달성하기 위해 그 작업을 수행하는 데 필요한 만큼의 2차 스레드를 초기의 1차 스레드가 생성하는 다중 스레드 애플리케이션을 설계해야 합니다. 보조 스레드는 주 스레드가 리소스를 관리하고 부하 균형을 조정하며 처리량을 향상시키도록 도와 줍니다. 다중 스레드 애플리케이션은 작업을 분산하여 단일 스레드 애플리케이션보다 성능을 높입니다.

하지만 보조 스레드에서 예외를 throw하는 경우 기본 스레드가 이를 처리하도록 합니다. 이것은 애플리케이션에서 2차 스레드의 수에 관계없이 일관성 있으며 통합된 방식으로 예외를 다루기를 원하기 때문입니다.

### <a name="solution"></a>솔루션

앞의 시나리오를 처리하기 위해 스레드 간에 예외를 전송할 때 C++ 표준이 지원됩니다. If a secondary thread throws an exception, that exception becomes the *current exception*. By analogy to the real world, the current exception is said to be *in flight*. 현재 예외는 throw되는 시점부터 이 예외를 catch하는 예외 처리기가 반환될 때까지 발생 중입니다.

The secondary thread can catch the current exception in a **catch** block, and then call the `current_exception` function to store the exception in an `exception_ptr` object. `exception_ptr` 개체는 보조 스레드 및 기본 스레드에서 사용할 수 있어야 합니다. 예를 들어, `exception_ptr` 개체는 전역 변수일 수 있습니다. 전역 변수의 액세스는 뮤텍스로 제어됩니다. The term *transport an exception* means an exception in one thread can be converted to a form that can be accessed by another thread.

다음으로, 기본 스레드는 `rethrow_exception` 개체에서 예외를 추출하고 throw하는 `exception_ptr` 함수를 호출합니다. 예외가 throw되면 해당 주 스레드에 있는 현재 예외가 됩니다. 즉, 예외는 기본 스레드에서 발생되는 것처럼 보입니다.

Finally, the primary thread can catch the current exception in a **catch** block and then process it or throw it to a higher level exception handler. 또는 주 스레드가 예외를 무시하고 프로세스를 끝낼 수 있습니다.

대부분의 애플리케이션은 스레드 사이에 예외를 전송하지 않아도 됩니다. 그러나 이 기능은 시스템에서 시스템 보조 스레드, 프로세서 또는 코어 간 작업을 분할할 수 있기 때문에 병렬 컴퓨팅 시스템에서 유용합니다. 병렬 컴퓨팅 환경에서는 단일, 전용 스레드가 보조 스레드의 모든 예외를 처리할 수 있으며 모든 애플리케이션에 대해 일관적인 예외 처리 모델을 제공할 수 있습니다.

C++ 표준 위원회 제안서에 대한 자세한 내용은 문서 번호 N2179, "스레드 간 예외 전송에 대한 언어 지원"이라는 제목의 인터넷을 검색하십시오.

### <a name="exception-handling-models-and-compiler-options"></a>Exception-handling models and compiler options

애플리케이션의 예외 처리 모델은 예외를 catch 및 전송할 수 있는지 여부를 결정합니다. Visual C++는 C++ 예외, 구조적 예외 처리(SEH) 예외 및 공용 언어 런타임(CLR) 예외를 처리할 수 있는 세 가지 모델을 지원합니다. Use the [/EH](../build/reference/eh-exception-handling-model.md) and [/clr](../build/reference/clr-common-language-runtime-compilation.md) compiler options to specify your application's exception-handling model.

다음 컴파일러 옵션 및 프로그래밍 문의 다음 조합만 예외를 전송할 수 있습니다. 다른 조합은 예외는 catch할 수 없거나 catch할 수는 있지만 예외를 전송할 수 없습니다.

- The **/EHa** compiler option and the **catch** statement can transport SEH and C++ exceptions.

- The **/EHa**, **/EHs**, and **/EHsc** compiler options and the **catch** statement can transport C++ exceptions.

- The **/CLR** compiler option and the **catch** statement can transport C++ exceptions. The **/CLR** compiler option implies specification of the **/EHa** option. 컴파일러는 관리되는 예외의 전송을 지원하지 않습니다. This is because managed exceptions, which are derived from the [System.Exception class](../standard-library/exception-class.md), are already objects that you can move between threads by using the facilities of the common languange runtime.

   > [!IMPORTANT]
   > We recommend that you specify the **/EHsc** compiler option and catch only C++ exceptions. You expose yourself to a security threat if you use the **/EHa** or **/CLR** compiler option and a **catch** statement with an ellipsis *exception-declaration* (`catch(...)`). You probably intend to use the **catch** statement to capture a few specific exceptions. 하지만 `catch(...)` 문은 예기치 않은 심각한 예외를 포함하여 모든 C++ 및 SEH 예외를 캡처합니다. 예기치 않은 예외를 무시하거나 잘못 처리하는 경우 악성 코드가 이 기회를 이용하여 프로그램 보안을 해칠 수 있습니다.

## <a name="usage"></a>사용 현황

The following sections describe how to transport exceptions by using the `exception_ptr` type, and the `current_exception`, `rethrow_exception`, and `make_exception_ptr` functions.

## <a name="exception_ptr-type"></a>exception_ptr type

`exception_ptr` 개체를 사용하여 현재 예외 또는 사용자 지정 예외의 인스턴스를 참조합니다. Microsoft 구현에서 예외가 [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) 구조체에 의해 표시됩니다. 각 `exception_ptr` 개체에는 예외를 나타내는 `EXCEPTION_RECORD` 구조체의 복사본을 가리키는 예외 참조 필드가 포함됩니다.

`exception_ptr` 변수를 선언할 때 변수는 예외와 관련되지 않습니다. 즉, 해당 예외 참조 필드는 NULL입니다. 이러한 `exception_ptr` 개체를 *null exception_ptr*라고 합니다.

`current_exception` 또는 `make_exception_ptr` 함수를 사용하여 `exception_ptr` 개체에 예외를 지정합니다. `exception_ptr` 변수에 예외를 할당하면, 변수 예외 참조 필드는 예외 복사본을 가리킵니다. 메모리가 부족하여 예외를 복사할 수 없는 경우 예외 참조 필드는 [std::bad_alloc](../standard-library/bad-alloc-class.md) 예외의 복사본을 가리킵니다. If the `current_exception` or `make_exception_ptr` function cannot copy the exception for any other reason, the function calls the [terminate](../c-runtime-library/reference/terminate-crt.md) function to exit the current process.

그 이름에도 불구하고 `exception_ptr` 개체 자체는 포인터가 아닙니다. It does not obey pointer semantics and cannot be used with the pointer member access (`->`) or indirection (`*`) operators. `exception_ptr` 개체에는 공용 데이터 멤버 또는 멤버 함수가 없습니다.

### <a name="comparisons"></a>비교

등호(`==`) 및 부등호(`!=`) 연산자를 사용하여 두 개의 `exception_ptr` 개체를 비교할 수 있습니다. 연산자는 예외를 나타내는 `EXCEPTION_RECORD` 구조의 이진 값(비트 패턴)을 비교하지 않습니다. 대신, 연산자는 `exception_ptr` 개체의 예외 참조 필드 주소를 비교합니다. 따라서 null `exception_ptr`과 NULL 값이 동일한 것으로 비교됩니다.

## <a name="current_exception-function"></a>current_exception function

Call the `current_exception` function in a **catch** block. If an exception is in flight and the **catch** block can catch the exception, the `current_exception` function returns an `exception_ptr` object that references the exception. 그렇지 않으면 인수가 null `exception_ptr` 개체를 반환합니다.

### <a name="details"></a>설명

The `current_exception` function captures the exception that is in flight regardless of whether the **catch** statement specifies an [exception-declaration](../cpp/try-throw-and-catch-statements-cpp.md) statement.

The destructor for the current exception is called at the end of the **catch** block if you do not rethrow the exception. 그러나 소멸자에 있는`current_exception` 함수를 호출하는 경우, 함수는 현재 예외를 참조하는 `exception_ptr` 개체를 반환합니다.

`current_exception` 수식에 대한 연속 호출은 현재 예외 건의 다른 복사본을 뜻하는 `exception_ptr` 개체를 반환합니다. 따라서 개체는 복사본에 같은 이진 값이 있더라도 다른 복사본을 참조하기 때문에 같지 않은 것으로 비교합니다.

### <a name="seh-exceptions"></a>SEH exceptions

If you use the **/EHa** compiler option, you can catch an SEH exception in a C++ **catch** block. `current_exception` 함수는 SEH 예외를 참조하는 `exception_ptr` 개체를 반환합니다. And the `rethrow_exception` function throws the SEH exception if you call it with thetransported `exception_ptr` object as its argument.

The `current_exception` function returns a null `exception_ptr` if you call it in an SEH **__finally** termination handler, an **__except** exception handler, or the **__except** filter expression.

전송된 예외는 중첩된 예외를 지원하지 않습니다. 예외가 처리되는 동안 다른 예외가 throw되는 경우 중첩된 예외가 발생합니다. 중첩된 예외를 catch하는 경우 `EXCEPTION_RECORD.ExceptionRecord` 데이터 멤버는 연결된 예외를 설명하는 `EXCEPTION_RECORD` 구조체의 체인을 가리킵니다. `current_exception` 함수는 `exception_ptr` 데이터 멤버가 0이 되는 `ExceptionRecord` 개체를 반환하기 때문에 중첩된 예외를 지원하지 않습니다.

SEH 예외를 catch하는 경우 `EXCEPTION_RECORD.ExceptionInformation` 데이터 멤버 배열의 임의의 포인터가 참조하는 메모리를 관리해야 합니다. 해당 `exception_ptr` 개체의 수명 중 메모리가 유효하며 `exception_ptr` 개체가 삭제될 때 메모리가 해제되는지 확인해야 합니다.

구조적 예외(SE) 변환기 함수를 전송 예외 기능과 함께 사용할 수 있습니다. SEH 예외가 C++ 예외로 번역되는 경우 `current_exception` 함수는 원래 SEH 예외가 아니라 번역된 예외를 참조하는 `exception_ptr`을 반환합니다. `rethrow_exception` 함수는 이후에 원래 예외가 아닌 번역된 예외를 throw합니다. For more information about SE translator functions, see [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).

## <a name="rethrow_exception-function"></a>rethrow_exception function

`exception_ptr` 개체에서 catch된 예외를 저장한 후 기본 스레드에서 개체를 처리할 수 있습니다. 기본 스레드에서 `rethrow_exception` 개체와 함께 작동하는 `exception_ptr` 함수를 호출합니다. `rethrow_exception` 함수는 `exception_ptr` 개체에서 예외를 추출하고, 주 스레드의 컨텍스트에서 예외를 throw합니다. If the *p* parameter of the `rethrow_exception` function is a null `exception_ptr`, the function throws [std::bad_exception](../standard-library/bad-exception-class.md).

이제 추출된 예외는 기본 스레드에서 현재 예외이며 이를 다른 예외와 동일한 방식으로 처리할 수 있습니다. If you catch the exception, you can handle it immediately or use a **throw** statement to send it to a higher level exception handler. 그렇지 않으면 아무 작업도 수행하지 말고 기본 시스템 예외 처리기로 해당 프로세스를 종료합니다.

## <a name="make_exception_ptr-function"></a>make_exception_ptr 함수

`make_exception_ptr` 함수는 클래스의 인스턴스를 인수로 사용한 다음 인스턴스를 참조하는 `exception_ptr`을 반환합니다. 모든 클래스 개체를 인수로 사용할 수 있지만, 일반적으로 [예외 클래스](../standard-library/exception-class.md) 개체를 `make_exception_ptr` 함수의 인수로 지정합니다.

Calling the `make_exception_ptr` function is equivalent to throwing a C++ exception, catching it in a **catch** block, and then calling the `current_exception` function to return an `exception_ptr` object that references the exception. `make_exception_ptr` 함수의 Microsoft 구현은 예외를 throw한 후 catch하는 것보다 더 효율적입니다.

애플리케이션에는 일반적으로 `make_exception_ptr` 함수가 필요하지 않으며 이 함수를 사용하지 않는 것이 좋습니다.

## <a name="example"></a>예제

다음 예제에서는 표준 C++ 예외와 사용자 지정 C++ 예외를 한 스레드에서 다른 스레드로 전송합니다.

```cpp
// transport_exception.cpp
// compile with: /EHsc /MD
#include <windows.h>
#include <stdio.h>
#include <exception>
#include <stdexcept>

using namespace std;

// Define thread-specific information.
#define THREADCOUNT 2
exception_ptr aException[THREADCOUNT];
int           aArg[THREADCOUNT];

DWORD WINAPI ThrowExceptions( LPVOID );

// Specify a user-defined, custom exception.
// As a best practice, derive your exception
// directly or indirectly from std::exception.
class myException : public std::exception {
};
int main()
{
    HANDLE aThread[THREADCOUNT];
    DWORD ThreadID;

    // Create secondary threads.
    for( int i=0; i < THREADCOUNT; i++ )
    {
        aArg[i] = i;
        aThread[i] = CreateThread(
            NULL,       // Default security attributes.
            0,          // Default stack size.
            (LPTHREAD_START_ROUTINE) ThrowExceptions,
            (LPVOID) &aArg[i], // Thread function argument.
            0,          // Default creation flags.
            &ThreadID); // Receives thread identifier.
        if( aThread[i] == NULL )
        {
            printf("CreateThread error: %d\n", GetLastError());
            return -1;
        }
    }

    // Wait for all threads to terminate.
    WaitForMultipleObjects(THREADCOUNT, aThread, TRUE, INFINITE);
    // Close thread handles.
    for( int i=0; i < THREADCOUNT; i++ ) {
        CloseHandle(aThread[i]);
    }

    // Rethrow and catch the transported exceptions.
    for ( int i = 0; i < THREADCOUNT; i++ ) {
        try {
            if (aException[i] == NULL) {
                printf("exception_ptr %d: No exception was transported.\n", i);
            }
            else {
                rethrow_exception( aException[i] );
            }
        }
        catch( const invalid_argument & ) {
            printf("exception_ptr %d: Caught an invalid_argument exception.\n", i);
        }
        catch( const myException & ) {
            printf("exception_ptr %d: Caught a  myException exception.\n", i);
        }
    }
}
// Each thread throws an exception depending on its thread
// function argument, and then ends.
DWORD WINAPI ThrowExceptions( LPVOID lpParam )
{
    int x = *((int*)lpParam);
    if (x == 0) {
        try {
            // Standard C++ exception.
            // This example explicitly throws invalid_argument exception.
            // In practice, your application performs an operation that
            // implicitly throws an exception.
            throw invalid_argument("A C++ exception.");
        }
        catch ( const invalid_argument & ) {
            aException[x] = current_exception();
        }
    }
    else {
        // User-defined exception.
        aException[x] = make_exception_ptr( myException() );
    }
    return TRUE;
}
```

```Output
exception_ptr 0: Caught an invalid_argument exception.
exception_ptr 1: Caught a  myException exception.
```

## <a name="requirements"></a>요구 사항

**헤더:** \<exception>

## <a name="see-also"></a>참조

[예외 처리](../cpp/exception-handling-in-visual-cpp.md)<br/>
[/EH(예외 처리 모델)](../build/reference/eh-exception-handling-model.md)<br/>
[/clr(공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)
