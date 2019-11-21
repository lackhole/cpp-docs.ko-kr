---
title: C++ 예외 및 스택 해제
ms.date: 11/19/2019
ms.assetid: a1a57eae-5fc5-4c49-824f-3ce2eb8129ed
ms.openlocfilehash: 11657206e86dbc81eb62c1e11b49fd87777f11d8
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246562"
---
# <a name="exceptions-and-stack-unwinding-in-c"></a>C++에서 예외 및 스택 해제

C++ 예외 메커니즘에서 컨트롤은 throw 문에서 throw된 형식을 처리할 수 있는 첫 번째 catch 문으로 이동합니다. When the catch statement is reached, all of the automatic variables that are in scope between the throw and catch statements are destroyed in a process that is known as *stack unwinding*. 스택 해제에서 실행은 다음과 같이 진행됩니다.

1. Control reaches the **try** statement by normal sequential execution. The guarded section in the **try** block is executed.

1. If no exception is thrown during execution of the guarded section, the **catch** clauses that follow the **try** block are not executed. Execution continues at the statement after the last **catch** clause that follows the associated **try** block.

1. If an exception is thrown during execution of the guarded section or in any routine that the guarded section calls either directly or indirectly, an exception object is created from the object that is created by the **throw** operand. (This implies that a copy constructor may be involved.) At this point, the compiler looks for a **catch** clause in a higher execution context that can handle an exception of the type that is thrown, or for a **catch** handler that can handle any type of exception. The **catch** handlers are examined in order of their appearance after the **try** block. If no appropriate handler is found, the next dynamically enclosing **try** block is examined. This process continues until the outermost enclosing **try** block is examined.

1. 일치하는 처리기를 여전히 찾을 수 없거나 해제 프로세스 중 처리기가 컨트롤을 갖기 전에 예외가 발생하는 경우 미리 정의된 런타임 함수 `terminate`가 호출됩니다. 예외가 throw되었지만 해제 작업을 시작하기 전에 예외가 발생하는 경우 `terminate`가 호출됩니다.

1. If a matching **catch** handler is found, and it catches by value, its formal parameter is initialized by copying the exception object. 참조로 catch하면 예외 개체를 참조하도록 매개 변수가 초기화됩니다. 정식 매개 변수가 초기화된 후 스택 해제 프로세스가 시작됩니다. This involves the destruction of all automatic objects that were fully constructed—but not yet destructed—between the beginning of the **try** block that is associated with the **catch** handler and the throw site of the exception. 소멸은 생성과 반대 순서로 발생합니다. The **catch** handler is executed and the program resumes execution after the last handler—that is, at the first statement or construct that is not a **catch** handler. Control can only enter a **catch** handler through a thrown exception, never through a **goto** statement or a **case** label in a **switch** statement.

## <a name="stack-unwinding-example"></a>Stack unwinding example

다음 예제에서는 예외가 throw되면 어떻게 스택이 해제되는지 보여 줍니다. 스레드에서의 실행은 방식에 따라 각 함수를 해제하면서 `C`의 throw 문에서 `main`의 catch 문으로 점프합니다. `Dummy` 개체가 만들어진 다음 범위에서 벗어날 때 제거되는 순서를 살펴보십시오. 또한 catch 문이 포함된 `main`을 제외하고는 어떤 함수도 완료할 수 없습니다. 함수 `A`는 `B()` 호출에서 반환되지 않으며 `B`도 `C()` 호출에서 반환되지 않습니다. `Dummy` 포인터의 정의 및 해당 delete 문에 대한 주석 처리를 제거한 다음 프로그램을 실행하면 포인터가 삭제되지 않습니다. 이는 함수가 예외 보장을 제공하지 않는 경우 발생할 수 있음을 보여 줍니다. 자세한 내용은 방법: 예외 디자인을 참조하십시오. catch 문을 주석으로 처리하는 경우 처리되지 않은 예외로 인해 프로그램을 종료할 때 나타나는 현상을 확인할 수 있습니다.

```cpp
#include <string>
#include <iostream>
using namespace std;

class MyException{};
class Dummy
{
    public:
    Dummy(string s) : MyName(s) { PrintMsg("Created Dummy:"); }
    Dummy(const Dummy& other) : MyName(other.MyName){ PrintMsg("Copy created Dummy:"); }
    ~Dummy(){ PrintMsg("Destroyed Dummy:"); }
    void PrintMsg(string s) { cout << s  << MyName <<  endl; }
    string MyName;
    int level;
};

void C(Dummy d, int i)
{
    cout << "Entering FunctionC" << endl;
    d.MyName = " C";
    throw MyException();

    cout << "Exiting FunctionC" << endl;
}

void B(Dummy d, int i)
{
    cout << "Entering FunctionB" << endl;
    d.MyName = "B";
    C(d, i + 1);
    cout << "Exiting FunctionB" << endl;
}

void A(Dummy d, int i)
{
    cout << "Entering FunctionA" << endl;
    d.MyName = " A" ;
  //  Dummy* pd = new Dummy("new Dummy"); //Not exception safe!!!
    B(d, i + 1);
 //   delete pd;
    cout << "Exiting FunctionA" << endl;
}

int main()
{
    cout << "Entering main" << endl;
    try
    {
        Dummy d(" M");
        A(d,1);
    }
    catch (MyException& e)
    {
        cout << "Caught an exception of type: " << typeid(e).name() << endl;
    }

    cout << "Exiting main." << endl;
    char c;
    cin >> c;
}

/* Output:
    Entering main
    Created Dummy: M
    Copy created Dummy: M
    Entering FunctionA
    Copy created Dummy: A
    Entering FunctionB
    Copy created Dummy: B
    Entering FunctionC
    Destroyed Dummy: C
    Destroyed Dummy: B
    Destroyed Dummy: A
    Destroyed Dummy: M
    Caught an exception of type: class MyException
    Exiting main.

*/
```
