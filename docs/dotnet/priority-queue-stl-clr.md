---
title: priority_queue(STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::priority_queue
- cliext::priority_queue::assign
- cliext::priority_queue::const_reference
- cliext::priority_queue::container_type
- cliext::priority_queue::difference_type
- cliext::priority_queue::empty
- cliext::priority_queue::generic_container
- cliext::priority_queue::generic_value
- cliext::priority_queue::get_container
- cliext::priority_queue::operator=
- cliext::priority_queue::pop
- cliext::priority_queue::priority_queue
- cliext::priority_queue::push
- cliext::priority_queue::reference
- cliext::priority_queue::size
- cliext::priority_queue::size_type
- cliext::priority_queue::to_array
- cliext::priority_queue::top
- cliext::priority_queue::top_item
- cliext::priority_queue::value_comp
- cliext::priority_queue::value_compare
- cliext::priority_queue::value_type
helpviewer_keywords:
- priority_queue class [STL/CLR]
- <queue> header [STL/CLR]
- <cliext/queue> header [STL/CLR]
- assign member [STL/CLR]
- const_reference member [STL/CLR]
- container_type member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- generic_container member [STL/CLR]
- generic_value member [STL/CLR]
- get_container member [STL/CLR]
- operator= member [STL/CLR]
- pop member [STL/CLR]
- priority_queue member [STL/CLR]
- push member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- to_array member [STL/CLR]
- top member [STL/CLR]
- top_item member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
ms.openlocfilehash: ed5e190f0c64aca3876d1cd1f05c9d75224355cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384766"
---
# <a name="priorityqueue-stlclr"></a>priority_queue(STL/CLR)

템플릿 클래스는 다양 한 길이의 액세스가 제한 된 요소의 시퀀스를 정렬 된 제어 하는 개체를 설명 합니다. 컨테이너 어댑터를 사용 하 여 `priority_queue` 우선 순위 큐로 기본 컨테이너를 관리할 수 있습니다.

아래 설명에서 `GValue` 같습니다 *값* 후자는 참조 형식, 하지 않는 한이 경우에서는 `Value^`합니다. 마찬가지로 `GContainer` 같습니다 *컨테이너* 후자는 참조 형식, 하지 않는 한이 경우에서는 `Container^`합니다.

## <a name="syntax"></a>구문

```cpp
template<typename Value,
    typename Container>
    ref class priority_queue
        System::ICloneable,
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>
    { ..... };
```

### <a name="parameters"></a>매개 변수

*값*<br/>
제어되는 시퀀스의 요소 형식입니다.

*컨테이너*<br/>
기본 컨테이너의 형식입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<cliext/큐 >

**Namespace:** cliext

## <a name="declarations"></a>선언

|형식 정의|설명|
|---------------------|-----------------|
|[priority_queue::const_reference(STL/CLR)](#const_reference)|요소에 대한 상수 참조의 형식입니다.|
|[priority_queue::container_type(STL/CLR)](#container_type)|기본 컨테이너의 형식입니다.|
|[priority_queue::difference_type(STL/CLR)](#difference_type)|두 요소 사이의 부호가 있는 거리의 형식입니다.|
|[priority_queue::generic_container(STL/CLR)](#generic_container)|컨테이너 어댑터에 대 한 제네릭 인터페이스의 형식입니다.|
|[priority_queue::generic_value(STL/CLR)](#generic_value)|컨테이너 어댑터에 대 한 제네릭 인터페이스에 대 한 요소의 형식입니다.|
|[priority_queue::reference(STL/CLR)](#reference)|요소에 대한 참조의 형식입니다.|
|[priority_queue::size_type(STL/CLR)](#size_type)|두 요소 사이의 부호가 있는 거리의 형식입니다.|
|[priority_queue::value_compare(STL/CLR)](#value_compare)|두 요소에 대 한 순서 지정 대리자입니다.|
|[priority_queue::value_type(STL/CLR)](#value_type)|요소의 형식입니다.|

|멤버 함수|설명|
|---------------------|-----------------|
|[priority_queue::assign(STL/CLR)](#assign)|모든 요소를 바꿉니다.|
|[priority_queue::empty(STL/CLR)](#empty)|요소가 있는지 여부를 테스트합니다.|
|[priority_queue::get_container(STL/CLR)](#get_container)|기본 컨테이너에 액세스합니다.|
|[priority_queue::pop(STL/CLR)](#pop)|Hghest 우선 순위 요소를 제거합니다.|
|[priority_queue::priority_queue(STL/CLR)](#priority_queue)|컨테이너 개체를 만듭니다.|
|[priority_queue::push(STL/CLR)](#push)|새 요소를 추가합니다.|
|[priority_queue::size(STL/CLR)](#size)|요소 수를 계산합니다.|
|[priority_queue::top(STL/CLR)](#top)|우선 순위가 가장 높은 요소에 액세스합니다.|
|[priority_queue::to_array(STL/CLR)](#to_array)|제어 되는 시퀀스를 새 배열에 복사합니다.|
|[priority_queue::value_comp(STL/CLR)](#value_comp)|두 요소에 대 한 순서 지정 대리자를 복사합니다.|

|속성|설명|
|--------------|-----------------|
|[priority_queue::top_item(STL/CLR)](#top_item)|우선 순위가 가장 높은 요소에 액세스합니다.|

|연산자|설명|
|--------------|-----------------|
|[priority_queue::operator=(STL/CLR)](#op_as)|제어되는 시퀀스를 바꿉니다.|

## <a name="interfaces"></a>인터페이스

|인터페이스|설명|
|---------------|-----------------|
|<xref:System.ICloneable>|개체를 복제 합니다.|
|IPriorityQueue\<값이 고, 컨테이너 >|제네릭 컨테이너 어댑터를 유지 합니다.|

## <a name="remarks"></a>설명

개체를 할당 하 고 형식의 기본 컨테이너를 통해 제어 하는 시퀀스에 대 한 저장소를 해제 `Container`를 저장 하는 `Value` 요소 및 필요에 따라 증가 합니다. 쉽게 액세스할 수 있고 이동식 우선 순위가 가장 높은 요소 (맨 위에 있는 요소)를 사용 하 여 힙으로 정렬 순서를 유지 합니다. 개체는 새 요소를 푸시 및 팝만 우선 순위가 가장 높은 요소에는 우선 순위 큐 구현에 액세스를 제한 합니다.

개체 형식의 저장 된 대리자 개체를 호출 하 여 제어 하는 시퀀스를 정렬 [priority_queue:: value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md)합니다. Priority_queue를 생성 하는 경우 저장 된 대리자 개체를 지정할 수 있습니다. 기본값은 비교 없는 대리자 개체를 지정 하면 `operator<(value_type, value_type)`합니다. 멤버 함수를 호출 하 여이 저장 된 개체를 액세스할 [priority_queue:: value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)`()`합니다.

이러한 대리자 개체 형식의 값에 엄밀히 약한 정렬을 적용 해야 합니다 [priority_queue:: value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)합니다. 즉, 두 개의 키에 대 한 `X` 고 `Y`:

`value_comp()(X, Y)` 호출할 때마다 동일한 부울 결과 반환.

하는 경우 `value_comp()(X, Y)` 가 true 이면 `value_comp()(Y, X)` false 여야 합니다.

하는 경우 `value_comp()(X, Y)` 가 true 이면 `X` 앞에 정렬 되어 있다고는 `Y`합니다.

하는 경우 `!value_comp()(X, Y) && !value_comp()(Y, X)` 가 true 이면 `X` 및 `Y` 동일 하 게 정렬 하 라고 합니다.

모든 요소에 대 한 `X` 앞에 오는 `Y` 제어 된 시퀀스에서 `key_comp()(Y, X)` 은 false입니다. (기본 대리자 개체에 대 한 키 결코 감소 값입니다.)

가장 높은 우선 순위 요소는 다른 요소 앞에 정렬 되지 않은 요소 중 하나 때문입니다.

힙 정렬 된 요소를 유지 하는 기본 컨테이너 하므로:

컨테이너는 임의 액세스 반복기를 지원 해야 합니다.

푸시된 보다과 순서가 동일한 요소와 다른 순서로 팝 할 수 있습니다. (순서 안정화 되지 않았습니다.)

따라서 기본 컨테이너에 대 한 후보 포함 [deque (STL/CLR)](../dotnet/deque-stl-clr.md) 하 고 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)합니다.

## <a name="members"></a>멤버

## <a name="assign"></a> priority_queue:: assign (STL/CLR)

모든 요소를 바꿉니다.

### <a name="syntax"></a>구문

```cpp
void assign(priority_queue<Value, Container>% right);
```

#### <a name="parameters"></a>매개 변수

*right*<br/>
삽입할 컨테이너 어댑터입니다.

### <a name="remarks"></a>설명

멤버 함수는 할당 `right.get_container()` 기본 컨테이너에 있습니다. 큐의 전체 내용을 변경 하려면 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_assign.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign a repetition of values
    Mypriority_queue c2;
    c2.assign(c1);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
```

## <a name="const_reference"></a> priority_queue:: const_reference (STL/CLR)

요소에 대한 상수 참조의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>설명

형식 요소에 대 한 상수 참조를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_const_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display reversed contents " c b a"
    for (; !c1.empty(); c1.pop())
        {   // get a const reference to an element
        Mypriority_queue::const_reference cref = c1.top();
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="container_type"></a> priority_queue:: container_type (STL/CLR)

기본 컨테이너의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Container value_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `Container`의 동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_container_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c" using container_type
    Mypriority_queue::container_type wc1 = c1.get_container();
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="difference_type"></a> priority_queue:: difference_type (STL/CLR)

두 요소 사이의 부호가 있는 거리의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>설명

형식 음수 수 있는 요소 수를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_difference_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute negative difference
    Mypriority_queue::difference_type diff = c1.size();
    c1.push(L'd');
    c1.push(L'e');
    diff -= c1.size();
    System::Console::WriteLine("pushing 2 = {0}", diff);

    // compute positive difference
    diff = c1.size();
    c1.pop();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("popping 3 = {0}", diff);
    return (0);
    }
```

```Output
c a b
pushing 2 = -2
popping 3 = 3
```

## <a name="empty"></a> priority_queue:: empty (STL/CLR)

요소가 있는지 여부를 테스트합니다.

### <a name="syntax"></a>구문

```cpp
bool empty();
```

### <a name="remarks"></a>설명

멤버 함수는 빈 제어되는 시퀀스에 대해 true를 반환합니다. 에 해당 하는 것 [priority_queue:: size (STL/CLR)](../dotnet/priority-queue-size-stl-clr.md)`() == 0`합니다. Priority_queue가 비어 있는지 여부를 테스트 하려면 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_empty.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

    // clear the container and reinspect
    c1.pop();
    c1.pop();
    c1.pop();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
c a b
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="generic_container"></a> priority_queue:: generic_container (STL/CLR)

컨테이너에 대 한 제네릭 인터페이스의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Microsoft::VisualC::StlClr::IPriorityQueue<Value>
    generic_container;
```

### <a name="remarks"></a>설명

형식은이 템플릿 컨테이너 어댑터 클래스에 대 한 제네릭 인터페이스를 설명 합니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_generic_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mypriority_queue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->push(L'd');
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.push(L'e');
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
d c b a
e d b a c
```

## <a name="generic_value"></a> priority_queue:: generic_value (STL/CLR)

컨테이너에 대 한 제네릭 인터페이스를 사용 하 여 사용에 대 한 요소의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>설명

이 형식은 형식의 개체를 설명 `GValue` 는이 템플릿 컨테이너 클래스에 대 한 제네릭 인터페이스를 사용 하 여 사용 하 여 저장 된 요소 값에 설명 합니다. (`GValue` 중 하나는 `value_type` 또는 `value_type^` 경우 `value_type` ref 형식입니다.)

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_generic_value.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get interface to container
    Mypriority_queue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display in priority order using generic_value
    for (; !gc1->empty(); gc1->pop())
        {
        Mypriority_queue::generic_value elem = gc1->top();

        System::Console::Write("{0} ", elem);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
c b a
```

## <a name="get_container"></a> priority_queue:: get_container (STL/CLR)

기본 컨테이너에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
container_type get_container();
```

### <a name="remarks"></a>설명

멤버 함수는 기본 컨테이너를 반환합니다. 컨테이너 래퍼에서 지정한 제한을 무시할 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_get_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="op_as"></a> priority_queue:: operator = (STL/CLR)

제어되는 시퀀스를 바꿉니다.

### <a name="syntax"></a>구문

```cpp
priority_queue <Value, Container>% operator=(priority_queue <Value, Container>% right);
```

#### <a name="parameters"></a>매개 변수

*right*<br/>
복사할 컨테이너 어댑터입니다.

### <a name="remarks"></a>설명

멤버 연산자 복사본 *오른쪽* 개체를 반환 `*this`합니다. 제어 되는 시퀀스에서 제어 된 시퀀스의 복사본으로 대체 하는 데 사용할 있습니다 *오른쪽*합니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_operator_as.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mypriority_queue c2;
    c2 = c1;
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
```

## <a name="pop"></a> priority_queue:: pop (STL/CLR)

Proirity 가장 높은 요소를 제거 합니다.

### <a name="syntax"></a>구문

```cpp
void pop();
```

### <a name="remarks"></a>설명

멤버 함수는 비어 있지 않아야 하는 제어 된 시퀀스의 우선 순위가 가장 높은 요소를 제거 합니다. 한 요소 뒤에 큐를 단축 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_pop.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // pop an element and redisplay
    c1.pop();
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
b a
```

## <a name="priority_queue"></a> priority_queue:: priority_queue (STL/CLR)

컨테이너 어댑터 개체를 생성합니다.

### <a name="syntax"></a>구문

```cpp
priority_queue();
priority_queue(priority_queue<Value, Container> right);
priority_queue(priority_queue<Value, Container> right);
explicit priority_queue(value_compare^ pred);
priority_queue(value_compare^ pred, container_type% cont);
template<typename InIt>
    priority_queue(InIt first, InIt last);
template<typename InIt>
    priority_queue(InIt first, InIt last,
        value_compare^ pred);
template<typename InIt>
    priority_queue(InIt first, InIt last,
        value_compare^ pred, container_type% cont);
```

#### <a name="parameters"></a>매개 변수

*cont*<br/>
복사할 컨테이너입니다.

*first*<br/>
삽입할 범위의 시작입니다.

*last*<br/>
삽입할 범위의 끝입니다.

*pred*<br/>
제어 되는 시퀀스에 대 한 조건자를 정렬 합니다.

*right*<br/>
삽입할 개체 또는 범위입니다.

### <a name="remarks"></a>설명

생성자:

`priority_queue();`

조건자 정렬 기본값을 사용 하 여 빈 래핑된 컨테이너를 만듭니다. 기본값은 조건자를 순서는 빈 초기 제어 되는 시퀀스를 지정 하려면 사용할 수 있습니다.

생성자:

`priority_queue(priority_queue<Value, Container>% right);`

복사본 인 래핑된 컨테이너를 만듭니다 `right.get_container()`, 순서 지정 조건자를 사용 하 여 `right.value_comp()`입니다. 큐 개체에 의해 제어 되는 시퀀스의 복사본 인 초기 제어 된 시퀀스를 지정 하려면 사용할 *오른쪽*를 동일한 순서 지정 조건자를 사용 하 여 합니다.

생성자:

`priority_queue(priority_queue<Value, Container>^ right);`

복사본 인 래핑된 컨테이너를 만듭니다 `right->get_container()`, 순서 지정 조건자를 사용 하 여 `right->value_comp()`입니다. 큐 개체에 의해 제어 되는 시퀀스의 복사본 인 초기 제어 된 시퀀스를 지정 하려면 사용할 `*right`를 동일한 순서 지정 조건자를 사용 하 여 합니다.

생성자:

`explicit priority_queue(value_compare^ pred);`

순서 지정 조건자를 사용 하 여 빈 래핑된 컨테이너를 만듭니다 *pred*합니다. 지정된 된 순서 지정 조건자를 사용 하 여 빈 초기 제어 된 시퀀스를 지정 하는 데 사용할 수 있습니다.

생성자:

`priority_queue(value_compare^ pred, container_type cont);`

순서 지정 조건자를 사용 하 여 빈 래핑된 컨테이너를 만듭니다 *pred*, 다음의 모든 요소를 푸시 *cont* 사용 하 여 기존 컨테이너에서는 초기 제어 되는 시퀀스를 지정 하는 데 사용할 있습니다 합니다 순서 지정 조건자를 지정 합니다.

생성자:

`template<typename InIt> priority_queue(InIt first, InIt last);`

기본 순서 지정 조건자를 사용 하 여 빈 래핑된 컨테이너를 만든 다음 시퀀스를 푸시 [`first`, `last`). 지정된 된 순서 지정 조건자를 사용 하 여 지정한 eqeuence에서 초기 제어 된 시퀀스를 지정 하려면 사용할 수 있습니다.

생성자:

`template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred);`

순서 지정 조건자를 사용 하 여 빈 래핑된 컨테이너를 만듭니다 *pred*, 한 다음 시퀀스를 푸시 [`first`, `last`). 지정된 된 순서 지정 조건자를 사용 하 여 지정한 seqeuence에서 초기 제어 된 시퀀스를 지정 하려면 사용할 수 있습니다.

생성자:

`template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred, container_type% cont);`

순서 지정 조건자를 사용 하 여 빈 래핑된 컨테이너를 만듭니다 *pred*, 다음의 모든 요소를 푸시 *cont* 시퀀스와 [`first`, `last`). 지정된 된 순서 지정 조건자를 사용 하 여 기존 컨테이너에서 지정 된 seqeuence, 초기 제어 된 시퀀스를 지정 하려면 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_construct.cpp
// compile with: /clr
#include <cliext/queue>
#include <cliext/deque>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
typedef cliext::deque<wchar_t> Mydeque;
int main()
    {
// construct an empty container
    Mypriority_queue c1;
    Mypriority_queue::container_type^ wc1 = c1.get_container();
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    for each (wchar_t elem in wc1)
        c2.push(elem);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule by copying an underlying container
    Mypriority_queue c2x =
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);
   for each (wchar_t elem in c2x.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range
    Mypriority_queue c3(wc1->begin(), wc1->end());
    for each (wchar_t elem in c3.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Mypriority_queue c4(wc1->begin(), wc1->end(),
        cliext::greater<wchar_t>());
    for each (wchar_t elem in c4.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range, another container, and an ordering rule
    Mypriority_queue c5(wc1->begin(), wc1->end(),
        cliext::greater<wchar_t>(), *wc1);
    for each (wchar_t elem in c5.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct from a generic container
    Mypriority_queue c6(c3);
    for each (wchar_t elem in c6.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Mypriority_queue c7(%c3);
    for each (wchar_t elem in c7.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule, by copying an underlying container
    Mypriority_queue c8 =
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);
    for each (wchar_t elem in c8.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
size() = 0
c a b
size() = 0
a c b
a c b
c a b
a c b
a a b c c b
c a b
c a b
a c b
```

## <a name="push"></a> priority_queue:: push (STL/CLR)

새 요소를 추가합니다.

### <a name="syntax"></a>구문

```cpp
void push(value_type val);
```

### <a name="remarks"></a>설명

멤버 함수는 값을 사용 하 여 요소를 삽입 `val` 제어 된 시퀀스에 힙 분야를 유지 하기 위해 제어 되는 시퀀스를 다시 정렬 하 고 있습니다. 큐에 다른 요소를 추가 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_push.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="reference"></a> priority_queue:: reference (STL/CLR)

요소에 대한 참조의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>설명

형식 요소에 대 한 참조를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify top of priority_queue and redisplay
    Mypriority_queue::reference ref = c1.top();
    ref = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
x a b
```

## <a name="size"></a> priority_queue:: size (STL/CLR)

요소 수를 계산합니다.

### <a name="syntax"></a>구문

```cpp
size_type size();
```

### <a name="remarks"></a>설명

멤버 함수는 제어되는 시퀀스의 길이를 반환합니다. 현재 제어 되는 시퀀스의에서 요소 수를 확인 하려면 사용 합니다. 모든 경우에 중요 한 여부 시퀀스 크기가 0이 아닌 참조 [priority_queue:: empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)`()`합니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_size.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // pop an item and reinspect
    c1.pop();
    System::Console::WriteLine("size() = {0} after popping", c1.size());

    // add two elements and reinspect
    c1.push(L'a');
    c1.push(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
c a b
size() = 3 starting with 3
size() = 2 after popping
size() = 4 after adding 2
```

## <a name="size_type"></a> priority_queue:: size_type (STL/CLR)

두 요소 사이의 부호가 있는 거리의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef int size_type;
```

### <a name="remarks"></a>설명

형식에는 음수가 아닌 요소 수를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_size_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Mypriority_queue::size_type diff = c1.size();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("size difference = {0}", diff);
    return (0);
    }
```

```Output
c a b
size difference = 2
```

## <a name="to_array"></a> priority_queue:: to_array (STL/CLR)

제어 되는 시퀀스를 새 배열에 복사합니다.

### <a name="syntax"></a>구문

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 되는 시퀀스를 포함 하는 배열을 반환 합니다. 배열 형식에서 제어 된 시퀀스의 복사본을 가져와야 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_to_array.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.push(L'd');
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
d c b a
c a b
```

## <a name="top"></a> priority_queue:: top (STL/CLR)

우선 순위가 가장 높은 요소에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
reference top();
```

### <a name="remarks"></a>설명

멤버 함수는 비어 있지 않아야 하는 제어 된 시퀀스의 최상위 (가장 높은 우선 순위) 요소에 대 한 참조를 반환 합니다. 존재를 알고 있는 경우 우선 순위가 가장 높은 요소를 액세스 하려면 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_top.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("top() = {0}", c1.top());

    // alter last item and reinspect
    c1.top() = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

## <a name="top_item"></a> priority_queue:: top_item (STL/CLR)

우선 순위가 가장 높은 요소에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
property value_type back_item;
```

### <a name="remarks"></a>설명

비어 있지 않아야 하는 제어 된 시퀀스의 최상위 (가장 높은 우선 순위) 요소를 액세스 하는 속성입니다. 읽거나 존재를 알고 있는 경우 우선 순위가 가장 높은 요소를 작성 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_top_item.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("top_item = {0}", c1.top_item);

    // alter last item and reinspect
    c1.top_item = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
top_item = c
x a b
```

## <a name="value_comp"></a> priority_queue:: value_comp (STL/CLR)

두 요소에 대 한 순서 지정 대리자를 복사합니다.

### <a name="syntax"></a>구문

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 되는 시퀀스를 정렬 하는 데 사용 하는 순서 지정 대리자를 반환 합니다. 두 값을 비교 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_value_comp.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    vcomp = c2.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="value_compare"></a> priority_queue:: value_compare (STL/CLR)

두 값의 순서 지정 대리자입니다.

### <a name="syntax"></a>구문

```cpp
binary_delegate<value_type, value_type, int> value_compare;
```

### <a name="remarks"></a>설명

형식에는 첫 번째 인수는 두 번째 정렬 되는지 여부를 결정 하는 대리자에 대 한 동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_value_compare.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    vcomp = c2.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="value_type"></a> priority_queue:: value_type (STL/CLR)

요소의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>설명

형식은 템플릿 매개 변수에 대 한 동의어 *값*합니다.

### <a name="example"></a>예제

```cpp
// cliext_priority_queue_value_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display reversed contents " a b c" using value_type
    for (; !c1.empty(); c1.pop())
        {   // store element in value_type object
        Mypriority_queue::value_type val = c1.top();

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```