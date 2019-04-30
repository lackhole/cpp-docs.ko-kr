---
title: 소멸자 (C++)
ms.date: 11/19/2018
helpviewer_keywords:
- objects [C++], destroying
- Visual C++, destructors
- destroying objects, destructors
- ~ operator [C++], specifying destructors
- destructors, about destructors
- destructors, C++
ms.assetid: afa859b0-f3bc-4c4d-b250-c68b335b6004
ms.openlocfilehash: f26f797da75f0d7d7aa6f6849c9484cea35fb125
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398997"
---
# <a name="destructors-c"></a>소멸자 (C++)

소멸자는 개체 범위를 벗어날 또는 명시적으로 호출 하 여 소멸 될 때 자동으로 호출 되는 멤버 함수 **삭제**합니다. 소멸자 이름이 같은 클래스로 앞에 물결표 (`~`). 예를 들어 클래스 `String`의 소멸자는 `~String()`으로 선언됩니다.

컴파일러는 기본; 하면 소멸자를 정의 하지 않는 경우 많은 클래스 이것으로 충분 합니다. 클래스를 해제 해야 하는 시스템 리소스에 대 한 핸들을 저장 하는 경우 사용자 지정 소멸자를 정의 해야 하거나 메모리를 소유 하는 포인터를 가리키도록 합니다.

다음 `String` 클래스 선언을 참조하십시오.

```cpp
// spec1_destructors.cpp
#include <string.h>

class String {
public:
   String( char *ch );  // Declare constructor
   ~String();           //  and destructor.
private:
   char    *_text;
   size_t  sizeOfText;
};

// Define the constructor.
String::String( char *ch ) {
   sizeOfText = strlen( ch ) + 1;

   // Dynamically allocate the correct amount of memory.
   _text = new char[ sizeOfText ];

   // If the allocation succeeds, copy the initialization string.
   if( _text )
      strcpy_s( _text, sizeOfText, ch );
}

// Define the destructor.
String::~String() {
   // Deallocate the memory that was previously reserved
   //  for this string.
   if (_text)
      delete[] _text;
}

int main() {
   String str("The piper in the glen...");
}
```

앞의 예제에서 소멸자에 `String::~String` 사용 하는 **삭제** 텍스트 저장소에 대 한 동적으로 할당 된 공간 할당을 취소 하는 연산자입니다.

## <a name="declaring-destructors"></a>소멸자 선언

소멸자는 클래스와 이름이 같지만 물결표(`~`)가 앞에 붙어 있는 함수입니다.

몇 가지 규칙이 소멸자의 선언에 적용됩니다. 소멸자는 다음과 같습니다.

- 인수를 받아들이지 않습니다.

- 값을 반환 하지 않습니다 (또는 **void**).

- 로 선언할 수 없습니다 **상수**, **volatile**, 또는 **정적**합니다. 그러나 호출할 수 있습니다으로 선언 된 개체의 소멸 **const**를 **volatile**, 또는 **정적**합니다.

- 로 선언할 수 있습니다 **가상**합니다. 가상 소멸자를 사용하면 개체의 형식을 모르는 상태에서 개체를 제거할 수 있습니다. 가상 함수 메커니즘을 사용하여 개체에 대한 올바른 소멸자가 호출됩니다. 소멸자는 추상 클래스의 순수 가상 함수로 선언될 수도 있습니다.

## <a name="using-destructors"></a>소멸자 사용

다음 이벤트 중 하나가 발생하면 소멸자가 호출됩니다.

- 블록 범위가 있는 로컬(자동) 개체는 범위를 벗어납니다.

- 사용 하 여 할당 된 개체를 **새** 연산자를 사용 하 여 명시적으로 할당 됩니다 **삭제**합니다.

- 임시 개체의 수명이 종료됩니다.

- 프로그램이 종료되고 전역 또는 정적 개체가 존재합니다.

- 소멸자는 소멸자 함수의 정규화된 이름을 사용하여 명시적으로 호출됩니다.

소멸자는 클래스 멤버 함수를 자유롭게 호출하고 클래스 멤버 데이터에 액세스할 수 있습니다.

소멸자 사용에 두 가지 제한 사항이 있습니다.

- 해당 주소를 가져올 수 없습니다.

- 파생된 클래스는 기본 클래스의 소멸자를 상속 하지 않습니다.

## <a name="order-of-destruction"></a>소멸 순서

개체가 범위에서 벗어나거나 삭제될 때 완전한 소멸에서 발생하는 이벤트 시퀀스는 다음과 같습니다.

1. 클래스의 소멸자가 호출되고 소멸자 함수의 본문이 실행됩니다.

1. 비정적 멤버 개체의 소멸자가 클래스 선언에 나타나는 순서와 반대로 호출됩니다. 이러한 멤버의 생성에 사용 되는 선택적 멤버 초기화 목록은 생성 또는 소멸의 순서는 영향을 주지 않습니다.

1. 비가상 기본 클래스의 소멸자는 선언의 역순으로 호출 됩니다.

1. 가상 기본 클래스의 소멸자가 선언과 반대 순서로 호출됩니다.

```cpp
// order_of_destruction.cpp
#include <stdio.h>

struct A1      { virtual ~A1() { printf("A1 dtor\n"); } };
struct A2 : A1 { virtual ~A2() { printf("A2 dtor\n"); } };
struct A3 : A2 { virtual ~A3() { printf("A3 dtor\n"); } };

struct B1      { ~B1() { printf("B1 dtor\n"); } };
struct B2 : B1 { ~B2() { printf("B2 dtor\n"); } };
struct B3 : B2 { ~B3() { printf("B3 dtor\n"); } };

int main() {
   A1 * a = new A3;
   delete a;
   printf("\n");

   B1 * b = new B3;
   delete b;
   printf("\n");

   B3 * b2 = new B3;
   delete b2;
}

Output: A3 dtor
A2 dtor
A1 dtor

B1 dtor

B3 dtor
B2 dtor
B1 dtor
```

### <a name="virtual-base-classes"></a>가상 기본 클래스

가상 기본 클래스의 소멸자는 방향이 있는 비순환 그래프(깊이 우선, 왼쪽에서 오른쪽으로, 후위 운행법)에서 표시되는 역순으로 호출됩니다. 다음 그림은 상속 그래프를 보여 줍니다.

![가상 기본 클래스를 보여 주는 상속 그래프](../cpp/media/vc392j1.gif "가상 기본 클래스를 보여 주는 상속 그래프") <br/>
가상 기본 클래스를 보여 주는 상속 그래프

다음은 그림에 표시된 클래스의 클래스 헤드를 나열합니다.

```cpp
class A
class B
class C : virtual public A, virtual public B
class D : virtual public A, virtual public B
class E : public C, public D, virtual public B
```

`E` 형식 개체의 가상 기본 클래스를 파괴하는 순서를 결정하기 위해 컴파일러는 다음 알고리즘을 적용하여 목록을 빌드합니다.

1. 그래프에서 가장 깊은 지점에서 시작하여 왼쪽으로 그래프를 이동합니다(이 경우 `E`).

1. 모든 노드를 방문할 때까지 왼쪽으로 이동을 수행합니다. 현재 노드의 이름입니다.

1. 이전 노드(아래 및 오른쪽으로)를 다시 방문하여 기억된 노드가 가상 기본 클래스인지 확인합니다.

1. 기억된 노드가 가상 기본 클래스인 경우 목록을 검색하여 이미 입력되었는지를 확인합니다. 가상 기본 클래스가 아닌 경우 무시합니다.

1. 기억된 노드가 아직 목록에 없는 경우 목록의 아래에 추가합니다.

1. 그래프를 위로 이동하고 다음 경로를 따라 오른쪽으로 이동합니다.

1. 2단계로 이동합니다.

1. 마지막 상향 경로가 모두 사용되면 현재 노드의 이름을 참고합니다.

1. 3단계로 이동합니다.

1. 아래쪽 노드가 다시 현재 노드가 될 때까지 이 프로세스를 계속합니다.

따라서 `E` 클래스의 경우 소멸의 순서는 다음과 같습니다.

1. 비가상 기본 클래스 `E`합니다.

1. 비가상 기본 클래스 `D`합니다.

1. 비가상 기본 클래스 `C`합니다.

1. 가상 기본 클래스 `B`.

1. 가상 기본 클래스 `A`.

이 프로세스는 고유 항목의 순서 지정된 목록을 만듭니다. 클래스 이름은 두 번 표시되지 않습니다. 목록이 생성되면 역순으로 나타나고 목록의 마지막에서 처음의 순으로 각 클래스에 대한 소멸자가 호출됩니다.

생성 또는 소멸의 순서는 주로 한 클래스의 생성자 또는 소멸자가 처음으로 만들어진 다른 구성 요소 또는 더 오래 지속되는 다른 구성 요소에 의존하는 경우 중요합니다. 예를 들어 `A`(위 그림에 표시됨)의 소멸자가 해당 코드 실행 중 계속 존재하는 `B`에 의존하는 경우가 해당합니다. 반대의 경우도 마찬가지입니다.

나중에 파생된 클래스가 생성과 소멸의 순서를 변경할 수 있는 가장 왼쪽 경로를 변경할 수 있기 때문에 상속 그래프에서 클래스 사이의 이러한 상호 의존성은 본질적으로 위험합니다.

### <a name="non-virtual-base-classes"></a>비가상 기본 클래스

비가상 기본 클래스의 소멸자는 기본 클래스 이름이 선언 되는 역순으로 호출 됩니다. 다음과 같은 클래스 선언을 생각해 보세요.

```cpp
class MultInherit : public Base1, public Base2
...
```

위의 예제에서 `Base2`의 소멸자가 `Base1`의 소멸자보다 먼저 호출됩니다.

## <a name="explicit-destructor-calls"></a>명시적 소멸자 호출

대부분의 경우 소멸자를 명시적으로 호출할 필요가 없지만 절대 주소에 있는 개체를 정리할 때는 도움이 됩니다. 이러한 개체는 일반적으로 할당 하 여 사용자 정의 사용 하 여 **새** 배치 인수를 사용 하는 연산자입니다. 합니다 **삭제** 가능한 저장소에서 할당 되지 않은 때문에 연산자가이 메모리를 할당 해제할 수 없습니다 (자세한 내용은 참조 하십시오 [새 및 delete 연산자](../cpp/new-and-delete-operators.md)). 그러나 소멸자를 호출하면 적절한 정리를 수행할 수 있습니다. `s` 클래스의 `String` 개체에 대해 소멸자를 명시적으로 호출하려면 다음 문 중 하나를 사용하세요.

```cpp
s.String::~String();     // non-virtual call
ps->String::~String();   // non-virtual call

s.~String();       // Virtual call
ps->~String();     // Virtual call
```

앞에 나온 대로 소멸자를 정의하는 형식에 관계없이 소멸자를 명시적으로 호출하기 위한 표기법을 사용할 수 있습니다. 그러면 형식에 대해 소멸자가 정의되었는지 여부를 몰라도 명시적인 호출이 가능합니다. 소멸자가 정의되지 않은 경우 명시적 호출은 아무 효과가 없습니다.