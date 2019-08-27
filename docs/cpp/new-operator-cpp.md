---
title: new 연산자 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
ms.openlocfilehash: bcb7784e59966510970bd9b3ae0157ae982e462d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245389"
---
# <a name="new-operator-c"></a>new 연산자 (C++)

개체의 배열 또는 개체에 대 한 메모리를 할당 *형식 이름을* 무료에서 저장 하 고 개체에는 적절 한 형식의 0이 아닌 포인터를 반환 합니다.

> [!NOTE]
>  Microsoft C++ 구성 요소 확장에 대 한 지원을 제공 합니다 **새** vtable 슬롯 항목을 추가 하는 키워드입니다. 자세한 내용은 참조 하세요. [new (의 new 슬롯 vtable)](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)

## <a name="syntax"></a>구문

```
[::] new [placement] new-type-name [new-initializer]
[::] new [placement] ( type-name ) [new-initializer]
```

## <a name="remarks"></a>설명

실패 하면 **새** 0을 반환 하거나 예외를 throw를 참조 하세요 [새 및 delete 연산자](../cpp/new-and-delete-operators.md) 자세한 내용은 합니다. 사용자 지정 예외 처리 루틴을 작성 하 고 호출 하 여이 기본 동작을 변경할 수는 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) 런타임 라이브러리 함수를 인수로 서 함수 이름과 함께 합니다.

관리 되는 힙에서 개체를 만드는 방법에 대 한 자세한 내용은 [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md)합니다.

때 **새** 에 대 한 메모리를 할당 하는 데 사용 되는 C++ 클래스 개체를 개체의 생성자는 메모리가 할당 된 후에 호출 됩니다.

사용 합니다 [삭제](../cpp/delete-operator-cpp.md) 연산자를 사용 하 여 할당 된 메모리 할당을 취소 합니다 **새** 연산자입니다.

다음 예제에서는 크기가 `dim`의 10배인 2차원 문자 배열을 할당한 다음 해제합니다. 다차원 배열을 할당할 때는 첫 번째를 제외한 모든 차원이 양수 값으로 계산되는 상수 식이어야 합니다. 맨 왼쪽 배열 차원은 양수 값으로 계산되는 임의의 식일 수 있습니다. 하 여 배열을 할당할 때 합니다 **새** 연산자가 첫 번째 차원에는 0 일 수 있습니다-합니다 **새** 연산자에는 고유한 포인터를 반환 합니다.

```cpp
char (*pchar)[10] = new char[dim][10];
delete [] pchar;
```

*형식 이름을* 포함할 수 없습니다 **const**를 **volatile**, 클래스 선언 또는 열거형 선언 합니다. 따라서 다음 식은 올바르지 않습니다.

```cpp
volatile char *vch = new volatile char[20];
```

합니다 **새** 개체 하지 않기 때문에 연산자 참조 형식을 할당 하지 않습니다.

합니다 **새** 함수, 연산자를 사용할 수 없지만 함수에 대 한 포인터를 할당할 수 있습니다. 다음 예제에서는 정수를 반환하는 함수에 대한 7개의 포인터 배열을 할당한 다음 해제합니다.

```cpp
int (**p) () = new (int (*[7]) ());
delete *p;
```

연산자를 사용 하는 경우 **새** 없이 모든 추가 인수를 사용 하 여 컴파일하는 [/GX](../build/reference/gx-enable-exception-handling.md)에 [/EHa](../build/reference/eh-exception-handling-model.md), 또는 [/EHs](../build/reference/eh-exception-handling-model.md) 옵션, 컴파일러는 연산자를 호출 하는 코드 생성 **삭제** 생성자에서 예외가 throw 됩니다.

다음 목록은 문법 요소의 **새**:

*placement*<br/>
오버 로드 하는 경우 추가 인수를 전달 하는 방법을 제공 **새**합니다.

*type-name*<br/>
기본 제공 또는 사용자 정의 형식 중에서 할당할 형식을 지정합니다. 형식 사양이 복잡한 경우 괄호로 묶어 바인딩 순서를 강제로 지정할 수 있습니다.

*initializer*<br/>
초기화된 개체의 값을 제공합니다. 배열에 대한 이니셜라이저는 지정할 수 없습니다. 합니다 **새** 클래스 기본 생성자가 하는 경우에 연산자는 개체 배열을 만듭니다.

## <a name="example"></a>예제

다음 코드 예제는 문자 배열 및 `CName` 클래스 개체를 할당한 다음 해제합니다.

```cpp
// expre_new_Operator.cpp
// compile with: /EHsc
#include <string.h>

class CName {
public:
   enum {
      sizeOfBuffer = 256
   };

   char m_szFirst[sizeOfBuffer];
   char m_szLast[sizeOfBuffer];

public:
   void SetName(char* pszFirst, char* pszLast) {
     strcpy_s(m_szFirst, sizeOfBuffer, pszFirst);
     strcpy_s(m_szLast, sizeOfBuffer, pszLast);
   }

};

int main() {
   // Allocate memory for the array
   char* pCharArray = new char[CName::sizeOfBuffer];
   strcpy_s(pCharArray, CName::sizeOfBuffer, "Array of characters");

   // Deallocate memory for the array
   delete [] pCharArray;
   pCharArray = NULL;

   // Allocate memory for the object
   CName* pName = new CName;
   pName->SetName("Firstname", "Lastname");

   // Deallocate memory for the object
   delete pName;
   pName = NULL;
}
```

## <a name="example"></a>예제

배치 새 형식을 사용 하는 경우는 **새** 연산자를 컴파일러가 할당 크기 이외의 인수가 사용 하 여 폼의 배치 형태를 지원 하지 않습니다는 **삭제** 연산자 경우는 생성자가 예외를 throw 합니다. 예를 들어:

```cpp
// expre_new_Operator2.cpp
// C2660 expected
class A {
public:
   A(int) { throw "Fail!"; }
};
void F(void) {
   try {
      // heap memory pointed to by pa1 will be deallocated
      // by calling ::operator delete(void*).
      A* pa1 = new A(10);
   } catch (...) {
   }
   try {
      // This will call ::operator new(size_t, char*, int).
      // When A::A(int) does a throw, we should call
      // ::operator delete(void*, char*, int) to deallocate
      // the memory pointed to by pa2.  Since
      // ::operator delete(void*, char*, int) has not been implemented,
      // memory will be leaked when the deallocation cannot occur.

      A* pa2 = new(__FILE__, __LINE__) A(20);
   } catch (...) {
   }
}

int main() {
   A a;
}
```

## <a name="initializing-object-allocated-with-new"></a>new로 할당된 개체 초기화

선택적인 *이니셜라이저* 필드에 대 한 문법에 포함 되어 합니다 **새** 연산자입니다. 사용자 정의 생성자를 사용하여 새 개체를 초기화할 수 있습니다. 초기화가 수행 하는 방법에 대 한 자세한 내용은 참조 하세요. [이니셜라이저](../cpp/initializers.md)합니다. 다음 예제를 사용 하 여 초기화 식을 사용 하는 방법을 합니다 **새** 연산자:

```cpp
// expre_Initializing_Objects_Allocated_with_new.cpp
class Acct
{
public:
    // Define default constructor and a constructor that accepts
    //  an initial balance.
    Acct() { balance = 0.0; }
    Acct( double init_balance ) { balance = init_balance; }
private:
    double balance;
};

int main()
{
    Acct *CheckingAcct = new Acct;
    Acct *SavingsAcct = new Acct ( 34.98 );
    double *HowMuch = new double ( 43.0 );
    // ...
}
```

이 예제에서는 개체 `CheckingAcct` 를 사용 하 여 할당 된 합니다 **새** 연산자 되지만 기본 초기화가 지정 됩니다. 따라서 클래스의 기본 생성자인 `Acct()`가 호출됩니다. 그런 다음 명시적으로 34.98로 초기화된다는 점을 제외하고 `SavingsAcct` 개체가 같은 식으로 할당됩니다. 34.98 형식 이므로 **이중**, 초기화를 처리 하는 형식의 인수를 사용 하는 생성자가 호출 됩니다. 마지막으로 비클래스 형식 `HowMuch`가 43.0으로 초기화됩니다.

개체를 초기화할 수 클래스 형식의 개체가 해당 클래스에는 이전 예에서 같이 생성자가 하는 경우는 **새** 이러한 조건 중 하나가 충족 될 경우에 연산자:

- 이니셜라이저에 제공된 인수는 생성자의 인수와 일치합니다.

- 클래스에 기본 생성자(인수 없이 호출할 수 있는 생성자)가 있습니다.

사용 하 여 배열을 할당할 때 요소 마다 명시적 초기화를 수행할 수 있습니다 합니다 **새** 연산자, 기본 생성자만 있는 경우 호출 됩니다. 참조 [기본 인수](../cpp/default-arguments.md) 자세한 내용은 합니다.

메모리 할당이 실패 하는 경우 (**new 연산자** 0 값을 반환), 초기화가 수행 됩니다. 존재하지 않는 데이터를 초기화하려는 시도를 막을 수 있습니다.

함수 호출과 마찬가지로 초기화된 식이 계산되는 순서가 정의되지 않습니다. 또한 메모리 할당을 수행하기 전에 완전히 계산되는 이 식에 의존하지 마십시오. 메모리 할당이 실패 하는 경우와 **새** 0을 반환 하는 연산자, 이니셜라이저의 일부 식이 완전히 계산 되지 않을 수 있습니다.

## <a name="lifetime-of-objects-allocated-with-new"></a>new로 할당된 개체 수명

로 할당 된 개체를 **새** 연산자에는 정의 된 범위가 종료 될 때 소멸 되지 않습니다. 때문에 합니다 **새** 포인터 할당 한 개체를 반환 하는 연산자, 프로그램에는 해당 개체에 액세스 하려면 알맞은 범위의 포인터를 정의 해야 합니다. 예를 들어:

```cpp
// expre_Lifetime_of_Objects_Allocated_with_new.cpp
// C2541 expected
int main()
{
    // Use new operator to allocate an array of 20 characters.
    char *AnArray = new char[20];

    for( int i = 0; i < 20; ++i )
    {
        // On the first iteration of the loop, allocate
        //  another array of 20 characters.
        if( i == 0 )
        {
            char *AnotherArray = new char[20];
        }
    }

    delete [] AnotherArray; // Error: pointer out of scope.
    delete [] AnArray;      // OK: pointer still in scope.
}
```

`AnotherArray` 포인터가 예제 범위를 벗어나면 개체를 더 이상 삭제할 수 없습니다.

## <a name="how-new-works"></a>new 작동 방식

*할당 식* -포함 하는 식을 **새** 연산자-세 가지 작업을 수행 합니다.

- 할당할 개체에 대한 스토리지를 찾고 예약합니다. 이 단계가 완료되면 올바른 양의 스토리지가 할당되지만 아직 개체는 아닙니다.

- 개체를 초기화합니다. 초기화가 완료되면 할당된 스토리지가 개체가 되는 데 충분한 정보가 있습니다.

- 포인터 형식의 개체에 대 한 포인터에서 파생 된 반환 *새 형식 이름을* 하거나 *형식-이름이*합니다. 프로그램에서는 이 포인터를 사용하여 새로 할당된 개체에 액세스합니다.

합니다 **새** 함수를 호출 하는 연산자 **new 연산자**합니다. 아닌 개체 및 모든 형식의 배열에 대 한 **클래스**, **구조체**, 또는 **union** 형식, 전역 함수인 **:: new 연산자**에 저장소를 할당 하기 위해 호출 됩니다. 클래스 형식 개체를 정의할 수는 자신의 **new 연산자** 클래스 별로에서 정적 멤버 함수입니다.

발견할 경우에 컴파일러는 **새** 형식의 개체를 할당 연산자 **유형**에 대 한 호출을 발급 하 `type` **:: 연산자 new (sizeof (** `type` **))** 또는 사용자 정의 되지 않은 경우 **new 연산자** 정의 된 **:: 연산자 new (sizeof (** `type` **))** 합니다. 따라서 합니다 **새** 연산자는 개체에 대 한 올바른 양의 메모리를 할당할 수 있습니다.

> [!NOTE]
>  인수 **new 연산자** 유형의 `size_t`합니다. 이 형식에 정의 된 \<direct.h >, \<malloc.h >, \<memory.h >, \<search.h >, \<stddef.h >, \<stdio.h >, \<b. h >를 \<string.h >, 및 \<time.h >.

문법에서 옵션에 지정할 수 있습니다 *배치* (에 대 한 문법 참조 [new 연산자](../cpp/new-operator-cpp.md)). 합니다 *배치* 매개 변수를 사용자 정의 구현에 대해서만 사용할 수 있습니다 **new 연산자**; 추가 정보를 전달할 수 있도록 **new 연산자**합니다. 식을 사용 하 여는 *배치* 와 같은 필드 `T *TObject = new ( 0x0040 ) T;` 으로 변환 됩니다 `T *TObject = T::operator new( sizeof( T ), 0x0040 );` T 클래스 멤버에 연산자가 있으면 새 그렇지 않은 경우를 `T *TObject = ::operator new( sizeof( T ), 0x0040 );`입니다.

원래 의도 *배치* 필드 사용자 지정 주소에 할당 되는 하드웨어 종속 개체를 허용 하는 것 이었습니다.

> [!NOTE]
>  앞의 예제에서 인수를 하나만 보여 주지만 합니다 *배치* 필드에 얼마나 많은 추가 인수를 전달할 수에 제한이 **new 연산자** 이 이렇게 합니다.

경우에 **new 연산자** 정의한 클래스 형식, 전역 연산자 다음이 예제의 형태를 사용 하 여 사용할 수 있습니다.

```cpp
T *TObject =::new TObject;
```

범위 결정 연산자 (`::`)를 사용 하면 사용의 전역 **새** 연산자입니다.

## <a name="see-also"></a>참고자료

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[새 및 delete 연산자](../cpp/new-and-delete-operators.md)