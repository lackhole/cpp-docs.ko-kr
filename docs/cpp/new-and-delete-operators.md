---
title: new 및 delete 연산자
ms.date: 11/04/2016
f1_keywords:
- delete_cpp
- new
helpviewer_keywords:
- new keyword [C++], dynamic allocation of objects
- nothrownew.obj
- delete keyword [C++], syntax
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
ms.openlocfilehash: 1ac6282ecbf45f22e7dd66b94f8bccdbc4e505ce
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345890"
---
# <a name="new-and-delete-operators"></a>new 및 delete 연산자

C++동적 할당 및 개체를 사용 하 여 할당 취소를 지원 합니다 [새](../cpp/new-operator-cpp.md) 하 고 [삭제](../cpp/delete-operator-cpp.md) 연산자입니다. 이러한 연산자는 사용 가능한 저장소라고 하는 풀에서 개체에 대한 메모리를 할당합니다. 합니다 **새** 특수 함수를 호출 하는 연산자 [new 연산자](../cpp/new-operator-cpp.md), 및 **삭제** 특수 함수를 호출 하는 연산자 [연산자 delete](../cpp/delete-operator-cpp.md).

합니다 **새** 함수를 C++ 표준 라이브러리에서 지정 된 동작을 지원 합니다 C++ 메모리 할당이 실패 하는 경우 std:: bad_alloc 예외를 throw 하는 표준입니다. Throw 되지 않는 버전을 원하는 경우 **새**, 프로그램을 nothrownew.obj와 연결 합니다. 그러나 연결 하면 기본 nothrownew.obj와 연결 **new 연산자** 에 C++ 표준 라이브러리에서 더 이상 작동 합니다.

C 런타임 라이브러리를 구성 하는 라이브러리 파일의 목록 및 C++ 표준 라이브러리를 참조 하세요 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)합니다.

##  <a id="new_operator"> </a> New 연산자

함수 호출으로 변환 하는 프로그램에서 다음과 같은 문이 발생 하면 **new 연산자**:

```cpp
char *pch = new char[BUFFER_SIZE];
```

저장소의 0 바이트가 요청 되는 경우 **new 연산자** 고유 개체에 대 한 포인터를 반환 합니다 (즉,에 대 한 호출을 반복 **new 연산자** 다른 포인터를 반환). 할당 요청에 대 한 메모리가 부족 한 경우 **new 연산자** std:: bad_alloc 예외를 throw 하거나 반환 **nullptr** throw 되지 않는에 연결한 경우 **new 연산자** 지원 합니다.

메모리를 확보 하 고 할당;을 다시 시도 하려고 하는 루틴을 작성할 수 있습니다. 참조 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) 자세한 내용은 합니다. 복구 체계에 대 한 자세한 내용은이 항목의 처리 메모리가 부족 하 여 섹션을 참조 합니다.

두 범위가 **new 연산자** 기능은 다음 표에 설명 되어 있습니다.

### <a name="scope-for-operator-new-functions"></a>operator new 함수의 범위

|연산자|범위|
|--------------|-----------|
|**::operator new**|Global|
|*class-name* **::operator new**|클래스|

첫 번째 인수 **new 연산자** 유형 이어야 `size_t` (에 정의 된 형식 \<stddef.h >), 하며 반환 형식은 항상 **void** <strong>\*</strong>.

전역 **new 연산자** 호출 될 때 합니다 **새** 연산자를 사용 하 여를 기본 제공 형식의 개체를 할당, 포함 하지 않는 클래스 형식의 개체가 사용자 정의 **new 연산자** 함수 및 모든 형식의 배열입니다. 때를 **새** 연산자 클래스 형식의 개체를 할당 하는 위치를 **new 연산자** 정의 된 해당 클래스의 **new 연산자** 라고 합니다.

**new 연산자** 클래스는 전역 숨기는 정적 멤버 함수 (이 없습니다, 따라서 가상)에 대해 정의 된 함수 **new 연산자** 해당 클래스 형식의 개체에 대 한 함수입니다. 경우를 생각해 보겠습니다 위치 **새** 할당 하 고 지정 된 값으로 메모리를 설정 하는 데 사용 됩니다.

```cpp
// spec1_the_operator_new_function1.cpp
#include <malloc.h>
#include <memory.h>

class Blanks
{
public:
    Blanks(){}
    void *operator new( size_t stAllocateBlock, char chInit );
};
void *Blanks::operator new( size_t stAllocateBlock, char chInit )
{
    void *pvTemp = malloc( stAllocateBlock );
    if( pvTemp != 0 )
        memset( pvTemp, chInit, stAllocateBlock );
    return pvTemp;
}
// For discrete objects of type Blanks, the global operator new function
// is hidden. Therefore, the following code allocates an object of type
// Blanks and initializes it to 0xa5
int main()
{
   Blanks *a5 = new(0xa5) Blanks;
   return a5 != 0;
}
```

괄호로 제공 된 인수가 **새** 에 전달 됩니다 `Blanks::operator new` 로 `chInit` 인수입니다. 그러나 전역 **new 연산자** 함수가 숨겨져 오류를 생성 하려면 다음과 같은 코드를 발생 합니다.

```cpp
Blanks *SomeBlanks = new Blanks;
```

시각적 개체의 C++ 5.0 및 이전 버전의 경우 비 클래스 형식 및 모든 배열 (된 여부에 관계 없이 **클래스** 형식) 사용 하 여 할당 된 **새** 연산자는 항상 전역 사용 **new 연산자**  함수입니다.

시각적 개체를 사용 하 여 시작 C++ 5.0, 컴파일러는 멤버 배열을 지원 **새** 하 고 **삭제** 클래스 선언에서 연산자. 예를 들어:

```cpp
// spec1_the_operator_new_function2.cpp
class MyClass
{
public:
   void * operator new[] (size_t)
   {
      return 0;
   }
   void   operator delete[] (void*)
   {
   }
};

int main()
{
   MyClass *pMyClass = new MyClass[5];
   delete [] pMyClass;
}
```

### <a name="handling-insufficient-memory"></a>메모리 부족 처리

다음과 같이 실패한 메모리 할당에 대한 테스트를 수행할 수 있습니다.

```cpp
// insufficient_memory_conditions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
#define BIG_NUMBER 100000000
int main() {
   int *pI = new int[BIG_NUMBER];
   if( pI == 0x0 ) {
      cout << "Insufficient memory" << endl;
      return -1;
   }
}
```

실패 한 메모리 할당 요청을 처리 하는 다른 방법: 이러한 오류를 처리 하는 사용자 지정 복구 루틴을 작성 한 다음 호출 하 여 함수를 등록 합니다 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) 런타임 함수입니다.

##  <a id="delete_operator"> </a> Delete 연산자

사용 하 여 동적으로 할당 된 메모리를 **새** 연산자를 사용 하 여 해제할 수는 **삭제** 연산자입니다. Delete 연산자 호출을 **delete 연산자** 함수를 사용할 수 있는 풀으로 메모리를 해제 합니다. 사용 하는 **삭제** 연산자 또한를 사용 하면 클래스 소멸자 (있는 경우)를 호출할 수 있습니다.

전역 및 클래스 범위의 **delete 연산자** 함수입니다. 하나만 **delete 연산자** 숨깁니다 전역 정의 하는 경우; 지정된 된 클래스에 대 한 함수를 정의할 수 있습니다 **delete 연산자** 함수입니다. 전역 **delete 연산자** 함수는 항상 모든 형식의 배열에 대해 호출 됩니다.

전역 **delete 연산자** 함수입니다. 두 가지 형태가 있습니다 전역 **delete 연산자** 및 클래스 멤버 **delete 연산자** 함수:

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

위의 두 가지 형태 중 하나만 지정된 된 클래스에 있을 수 있습니다. 첫 번째 폼 형식의 단일 인수 `void *`, 할당을 취소 하는 개체에 대 한 포인터를 포함 하는 합니다. 두 번째 형태-할당 취소를 크기 조정-2 개 인수에는 첫 번째 할당을 취소 된 메모리 블록에 대 한 포인터 이며 두 번째는 할당 해제할 바이트 수입니다. 두 형태 모두의 반환 형식은 **void** (**delete 연산자** 값을 반환할 수 없습니다).

두 번째 폼의 의도가 속도 삭제할 개체의 올바른 크기 범주를 검색할 수 없는 경우가 많습니다 자체 할당을 가깝게 저장 되 고 캐시 되지 않은 것입니다. 두 번째 형태는 특히 유용 프로그램 **delete 연산자** 함수 기본 클래스에서 파생된 된 클래스의 개체를 삭제 하는 합니다.

합니다 **delete 연산자** 함수는 정적; 따라서 가상 일 수 없습니다. 합니다 **delete 연산자** 함수에 설명 된 대로 access control을 따릅니다 [멤버 Access Control](../cpp/member-access-control-cpp.md)합니다.

다음 예제에서는 사용자 정의 **new 연산자** 하 고 **delete 연산자** 할당 및 메모리 할당 취소를 기록 하도록 디자인 된 함수:

```cpp
// spec1_the_operator_delete_function1.cpp
// compile with: /EHsc
// arguments: 3
#include <iostream>
using namespace std;

int fLogMemory = 0;      // Perform logging (0=no; nonzero=yes)?
int cBlocksAllocated = 0;  // Count of blocks allocated.

// User-defined operator new.
void *operator new( size_t stAllocateBlock ) {
   static int fInOpNew = 0;   // Guard flag.

   if ( fLogMemory && !fInOpNew ) {
      fInOpNew = 1;
      clog << "Memory block " << ++cBlocksAllocated
          << " allocated for " << stAllocateBlock
          << " bytes\n";
      fInOpNew = 0;
   }
   return malloc( stAllocateBlock );
}

// User-defined operator delete.
void operator delete( void *pvMem ) {
   static int fInOpDelete = 0;   // Guard flag.
   if ( fLogMemory && !fInOpDelete ) {
      fInOpDelete = 1;
      clog << "Memory block " << cBlocksAllocated--
          << " deallocated\n";
      fInOpDelete = 0;
   }

   free( pvMem );
}

int main( int argc, char *argv[] ) {
   fLogMemory = 1;   // Turn logging on
   if( argc > 1 )
      for( int i = 0; i < atoi( argv[1] ); ++i ) {
         char *pMem = new char[10];
         delete[] pMem;
      }
   fLogMemory = 0;  // Turn logging off.
   return cBlocksAllocated;
}
```

앞의 코드를 사용하여 "메모리 누수"를 검색할 수 있습니다. 메모리 누수는 사용 가능한 저장소에 할당되었지만 비워지지 않은 메모리를 의미합니다. 전역이 검색을 수행 하도록 **새** 하 고 **삭제** 연산자 수 할당 및 메모리 할당 취소 하도록 다시 정의 됩니다.

시각적 개체를 사용 하 여 시작 C++ 5.0, 컴파일러는 멤버 배열을 지원 **새** 하 고 **삭제** 클래스 선언에서 연산자. 예를 들어:

```cpp
// spec1_the_operator_delete_function2.cpp
// compile with: /c
class X  {
public:
   void * operator new[] (size_t) {
      return 0;
   }
   void operator delete[] (void*) {}
};

void f() {
   X *pX = new X[5];
   delete [] pX;
}
```