---
title: queue(STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::queue
- cliext::operator!=
- cliext::operator<
- cliext::operator<=
- cliext::operator==
- cliext::operator>
- cliext::operator>=
- cliext::queue::assign
- cliext::queue::back
- cliext::queue::back_item
- cliext::queue::const_reference
- cliext::queue::container_type
- cliext::queue::difference_type
- cliext::queue::empty
- cliext::queue::front
- cliext::queue::front_item
- cliext::queue::generic_container
- cliext::queue::generic_value
- cliext::queue::get_container
- cliext::queue::operator=
- cliext::queue::pop
- cliext::queue::push
- cliext::queue::queue
- cliext::queue::reference
- cliext::queue::size
- cliext::queue::size_type
- cliext::queue::to_array
- cliext::queue::value_type
helpviewer_keywords:
- <queue> header [STL/CLR]
- queue class [STL/CLR]
- <cliext/queue> header [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
- assign member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- const_reference member [STL/CLR]
- container_type member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_value member [STL/CLR]
- get_container member [STL/CLR]
- operator= member [STL/CLR]
- pop member [STL/CLR]
- push member [STL/CLR]
- queue member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 9ea7dec3-ea98-48ff-87d0-a5afc924aaf2
ms.openlocfilehash: 2cf0467c2b4799c2009f866b7aa22be5e421f762
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384727"
---
# <a name="queue-stlclr"></a>queue(STL/CLR)

이 템플릿 클래스는 선입 선출 액세스 권한이 있는 요소의 다양 한 길이의 시퀀스를 제어 하는 개체를 설명 합니다. 컨테이너 어댑터를 사용 하 여 `queue` 큐로 기본 컨테이너를 관리할 수 있습니다.

아래 설명에서 `GValue` 같습니다 *값* 후자는 참조 형식, 하지 않는 한이 경우에서는 `Value^`합니다. 마찬가지로 `GContainer` 같습니다 *컨테이너* 후자는 참조 형식, 하지 않는 한이 경우에서는 `Container^`합니다.

## <a name="syntax"></a>구문

```cpp
template<typename Value,
    typename Container>
    ref class queue
        :   public
        System::ICloneable,
        Microsoft::VisualC::StlClr::IQueue<GValue, GContainer>
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
|[queue::const_reference(STL/CLR)](#const_reference)|요소에 대한 상수 참조의 형식입니다.|
|[queue::container_type(STL/CLR)](#container_type)|기본 컨테이너의 형식입니다.|
|[queue::difference_type(STL/CLR)](#difference_type)|두 요소 사이의 부호가 있는 거리의 형식입니다.|
|[queue::generic_container(STL/CLR)](#generic_container)|컨테이너 어댑터에 대 한 제네릭 인터페이스의 형식입니다.|
|[queue::generic_value(STL/CLR)](#generic_value)|컨테이너 어댑터에 대 한 제네릭 인터페이스에 대 한 요소의 형식입니다.|
|[queue::reference(STL/CLR)](#reference)|요소에 대한 참조의 형식입니다.|
|[queue::size_type(STL/CLR)](#size_type)|두 요소 사이의 부호가 있는 거리의 형식입니다.|
|[queue::value_type(STL/CLR)](#value_type)|요소의 형식입니다.|

|멤버 함수|설명|
|---------------------|-----------------|
|[queue::assign(STL/CLR)](#assign)|모든 요소를 바꿉니다.|
|[queue::back(STL/CLR)](#back)|마지막 요소에 액세스합니다.|
|[queue::empty(STL/CLR)](#empty)|요소가 있는지 여부를 테스트합니다.|
|[queue::front(STL/CLR)](#front)|첫 번째 요소에 액세스합니다.|
|[queue::get_container(STL/CLR)](#get_container)|기본 컨테이너에 액세스합니다.|
|[queue::pop(STL/CLR)](#pop)|첫 번째 요소를 제거합니다.|
|[queue::push(STL/CLR)](#push)|새 마지막 요소를 추가합니다.|
|[queue::queue(STL/CLR)](#queue)|컨테이너 개체를 만듭니다.|
|[queue::size(STL/CLR)](#size)|요소 수를 계산합니다.|
|[queue::to_array(STL/CLR)](#to_array)|제어 되는 시퀀스를 새 배열에 복사합니다.|

|속성|설명|
|--------------|-----------------|
|[queue::back_item(STL/CLR)](#back_item)|마지막 요소에 액세스합니다.|
|[queue::front_item(STL/CLR)](#front_item)|첫 번째 요소에 액세스합니다.|

|연산자|설명|
|--------------|-----------------|
|[queue::operator=(STL/CLR)](#op_as)|제어되는 시퀀스를 바꿉니다.|
|[operator!= (queue)(STL/CLR)](#op_neq)|확인을 `queue` 다른 개체가 같지 `queue` 개체입니다.|
|[operator< (queue)(STL/CLR)](#op_lt)|확인을 `queue` 개체를 사용 하면 다른 노드보다 작은지 `queue` 개체입니다.|
|[operator<= (queue)(STL/CLR)](#op_lteq)|확인을 `queue` 개체 보다 작거나 같으면 다른 `queue` 개체입니다.|
|[operator== (queue)(STL/CLR)](#op_eq)|확인을 `queue` 다른 개체가 같은지 `queue` 개체입니다.|
|[operator> (queue)(STL/CLR)](#op_gt)|확인을 `queue` 개체가 다른 인스턴스보다 큰지를 `queue` 개체입니다.|
|[operator>= (queue)(STL/CLR)](#op_gteq)|있는지 여부를 확인 한 `queue` 보다 크거나 같은 다른 개체가 `queue` 개체입니다.|

## <a name="interfaces"></a>인터페이스

|인터페이스|설명|
|---------------|-----------------|
|<xref:System.ICloneable>|개체를 복제 합니다.|
|IQueue\<값이 고, 컨테이너 >|제네릭 컨테이너 어댑터를 유지 합니다.|

## <a name="remarks"></a>설명

개체를 할당 하 고 형식의 기본 컨테이너를 통해 제어 하는 시퀀스에 대 한 저장소를 해제 `Container`를 저장 하는 `Value` 요소 및 필요에 따라 증가 합니다. 방금 첫 번째 요소를 액세스를 제한 하는 개체 및 (라고도: FIFO 큐 또는 단순히 큐) 큐는 선입 선출 구현 마지막 요소를 팝 합니다.

## <a name="members"></a>멤버

## <a name="assign"></a> queue:: assign (STL/CLR)

모든 요소를 바꿉니다.

### <a name="syntax"></a>구문

```cpp
void assign(queue<Value, Container>% right);
```

#### <a name="parameters"></a>매개 변수

*right*<br/>
삽입할 컨테이너 어댑터입니다.

### <a name="remarks"></a>설명

멤버 함수는 할당 `right.get_container()` 기본 컨테이너에 있습니다. 큐의 전체 내용을 변경 하려면 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_assign.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign a repetition of values
    Myqueue c2;
    c2.assign(c1);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="back"></a> queue:: back (STL/CLR)

마지막 요소에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
reference back();
```

### <a name="remarks"></a>설명

멤버 함수는 비어 있지 않아야 하는 제어 된 시퀀스의 마지막 요소에 대 한 참조를 반환 합니다. 있는 경우 마지막 요소를 액세스 하려면 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_back.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("back() = {0}", c1.back());

// alter last item and reinspect
    c1.back() = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
back() = c
a b x
```

## <a name="back_item"></a> queue:: back_item (STL/CLR)

마지막 요소에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
property value_type back_item;
```

### <a name="remarks"></a>설명

비어 있지 않아야 하는 제어 된 시퀀스의 마지막 요소를 액세스 하는 속성입니다. 읽거나 존재를 알고 있는 경우 마지막 요소를 작성 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_back_item.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("back_item = {0}", c1.back_item);

// alter last item and reinspect
    c1.back_item = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
back_item = c
a b x
```

## <a name="const_reference"></a> queue:: const_reference (STL/CLR)

요소에 대한 상수 참조의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>설명

형식 요소에 대 한 상수 참조를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_const_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for (; !c1.empty(); c1.pop())
        {   // get a const reference to an element
        Myqueue::const_reference cref = c1.front();
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="container_type"></a> queue:: container_type (STL/CLR)

기본 컨테이너의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Container value_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `Container`의 동의어입니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_container_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c" using container_type
    Myqueue::container_type wc1 = c1.get_container();
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="difference_type"></a> queue:: difference_type (STL/CLR)

두 요소 사이의 부호가 있는 거리의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>설명

형식 음수 수 있는 요소 수를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_difference_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute negative difference
    Myqueue::difference_type diff = c1.size();
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
a b c
pushing 2 = -2
popping 3 = 3
```

## <a name="empty"></a> queue:: empty (STL/CLR)

요소가 있는지 여부를 테스트합니다.

### <a name="syntax"></a>구문

```cpp
bool empty();
```

### <a name="remarks"></a>설명

멤버 함수는 빈 제어되는 시퀀스에 대해 true를 반환합니다. 에 해당 하는 것 [queue:: size (STL/CLR)](../dotnet/queue-size-stl-clr.md)`() == 0`합니다. 큐가 비어 있는지 여부를 테스트 하려면 사용 합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_empty.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
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
a b c
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="front"></a> queue:: front (STL/CLR)

첫 번째 요소에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
reference front();
```

### <a name="remarks"></a>설명

멤버 함수는 비어 있지 않아야 하는 제어 된 시퀀스의 첫 번째 요소에 대 한 참조를 반환 합니다. 있는 경우 첫 번째 요소에 액세스를 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_front.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first item
    System::Console::WriteLine("front() = {0}", c1.front());

// alter first item and reinspect
    c1.front() = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
front() = a
x b c
```

## <a name="front_item"></a> queue:: front_item (STL/CLR)

첫 번째 요소에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
property value_type front_item;
```

### <a name="remarks"></a>설명

비어 있지 않아야 하는 제어 된 시퀀스의 첫 번째 요소를 액세스 하는 속성입니다. 읽거나 존재를 알고 있는 경우 첫 번째 요소를 작성 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_front_item.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("front_item = {0}", c1.front_item);

// alter last item and reinspect
    c1.front_item = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
front_item = a
x b c
```

## <a name="generic_container"></a> queue:: generic_container (STL/CLR)

컨테이너 어댑터에 대 한 제네릭 인터페이스의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Microsoft::VisualC::StlClr::IQueue<Value>
    generic_container;
```

### <a name="remarks"></a>설명

형식은이 템플릿 컨테이너 어댑터 클래스에 대 한 제네릭 인터페이스를 설명 합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_generic_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myqueue::generic_container^ gc1 = %c1;
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
a b c
a b c
a b c d
a b c d e
```

## <a name="generic_value"></a> queue:: generic_value (STL/CLR)

컨테이너에 대 한 제네릭 인터페이스를 사용 하 여 사용에 대 한 요소의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>설명

이 형식은 형식의 개체를 설명 `GValue` 는이 템플릿 컨테이너 클래스에 대 한 제네릭 인터페이스를 사용 하 여 사용 하 여 저장 된 요소 값에 설명 합니다. (`GValue` 중 하나는 `value_type` 또는 `value_type^` 경우 `value_type` ref 형식입니다.)

### <a name="example"></a>예제

```cpp
// cliext_queue_generic_value.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get interface to container
    Myqueue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// display in order using generic_value
    for (; !gc1->empty(); gc1->pop())
        {
        Myqueue::generic_value elem = gc1->front();

        System::Console::Write("{0} ", elem);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a b c
```

## <a name="get_container"></a> queue:: get_container (STL/CLR)

기본 컨테이너에 액세스합니다.

### <a name="syntax"></a>구문

```cpp
container_type^ get_container();
```

### <a name="remarks"></a>설명

멤버 함수는 기본 컨테이너를 반환합니다. 컨테이너 래퍼에서 지정한 제한을 무시할 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_get_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
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
a b c
```

## <a name="op_as"></a> queue:: operator = (STL/CLR)

제어되는 시퀀스를 바꿉니다.

### <a name="syntax"></a>구문

```cpp
queue <Value, Container>% operator=(queue <Value, Container>% right);
```

#### <a name="parameters"></a>매개 변수

*right*<br/>
복사할 컨테이너 어댑터입니다.

### <a name="remarks"></a>설명

멤버 연산자 복사본 *오른쪽* 개체를 반환 `*this`합니다. 제어 되는 시퀀스에서 제어 된 시퀀스의 복사본으로 대체 하는 데 사용할 있습니다 *오른쪽*합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_operator_as.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2 = c1;
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="pop"></a> queue:: pop (STL/CLR)

마지막 요소를 제거합니다.

### <a name="syntax"></a>구문

```cpp
void pop();
```

### <a name="remarks"></a>설명

멤버 함수는 비어 있지 않아야 하는 제어 된 시퀀스의 마지막 요소를 제거 합니다. 한 요소 뒤에 큐를 단축 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_pop.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
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
a b c
b c
```

## <a name="push"></a> queue:: push (STL/CLR)

새 마지막 요소를 추가합니다.

### <a name="syntax"></a>구문

```cpp
void push(value_type val);
```

### <a name="remarks"></a>설명

값을 사용 하 여 요소를 추가 하는 멤버 함수 `val` 큐의 끝입니다. 큐에 요소를 추가 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_push.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
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
a b c
```

## <a name="queue"></a> queue:: queue (STL/CLR)

컨테이너 어댑터 개체를 생성합니다.

### <a name="syntax"></a>구문

```cpp
queue();
queue(queue<Value, Container>% right);
queue(queue<Value, Container>^ right);
explicit queue(container_type% wrapped);
```

#### <a name="parameters"></a>매개 변수

*right*<br/>
복사할 개체입니다.

*wrapped*<br/>
사용 하 여 래핑된 컨테이너입니다.

### <a name="remarks"></a>설명

생성자:

`queue();`

빈 래핑된 컨테이너를 만듭니다. 빈 초기 제어 되는 시퀀스를 지정 하는 데 사용할 수 있습니다.

생성자:

`queue(queue<Value, Container>% right);`

복사본 인 래핑된 컨테이너를 만듭니다. `right.get_container()`합니다. 큐 개체에 의해 제어 되는 시퀀스의 복사본 인 초기 제어 된 시퀀스를 지정 하려면 사용할 *오른쪽*합니다.

생성자:

`queue(queue<Value, Container>^ right);`

복사본 인 래핑된 컨테이너를 만듭니다. `right->get_container()`합니다. 큐 개체에 의해 제어 되는 시퀀스의 복사본 인 초기 제어 된 시퀀스를 지정 하려면 사용할 `*right`합니다.

생성자:

`explicit queue(container_type wrapped);`

기존 컨테이너를 사용 하 여 *래핑된* 래핑된 컨테이너입니다. 기존 컨테이너에서 큐를 생성 하는 데 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_construct.cpp
// compile with: /clr
#include <cliext/queue>
#include <cliext/list>

typedef cliext::queue<wchar_t> Myqueue;
typedef cliext::list<wchar_t> Mylist;
typedef cliext::queue<wchar_t, Mylist> Myqueue_list;
int main()
    {
// construct an empty container
    Myqueue c1;
    System::Console::WriteLine("size() = {0}", c1.size());

// construct from an underlying container
    Mylist v2(5, L'x');
    Myqueue_list c2(v2);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    Myqueue_list c3(c2);
    for each (wchar_t elem in c3.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container through handle
    Myqueue_list c4(%c2);
    for each (wchar_t elem in c4.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
x x x x x
x x x x x
x x x x x
```

## <a name="reference"></a> queue:: reference (STL/CLR)

요소에 대한 참조의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>설명

형식 요소에 대 한 참조를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify back of queue and redisplay
    Myqueue::reference ref = c1.back();
    ref = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b x
```

## <a name="size"></a> queue:: size (STL/CLR)

요소 수를 계산합니다.

### <a name="syntax"></a>구문

```cpp
size_type size();
```

### <a name="remarks"></a>설명

멤버 함수는 제어되는 시퀀스의 길이를 반환합니다. 현재 제어 되는 시퀀스의에서 요소 수를 확인 하려면 사용 합니다. 모든 경우에 중요 한 여부 시퀀스 크기가 0이 아닌 참조 [queue:: empty (STL/CLR)](../dotnet/queue-empty-stl-clr.md)`()`합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_size.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
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
a b c
size() = 3 starting with 3
size() = 2 after popping
size() = 4 after adding 2
```

## <a name="size_type"></a> queue:: size_type (STL/CLR)

두 요소 사이의 부호가 있는 거리의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef int size_type;
```

### <a name="remarks"></a>설명

형식에는 음수가 아닌 요소 수를 설명합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_size_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myqueue::size_type diff = c1.size();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("size difference = {0}", diff);
    return (0);
    }
```

```Output
a b c
size difference = 2
```

## <a name="to_array"></a> queue:: to_array (STL/CLR)

제어 되는 시퀀스를 새 배열에 복사합니다.

### <a name="syntax"></a>구문

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>설명

멤버 함수는 제어 되는 시퀀스를 포함 하는 배열을 반환 합니다. 배열 형식에서 제어 된 시퀀스의 복사본을 가져와야 사용할 수 있습니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_to_array.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
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
a b c d
a b c
```

## <a name="value_type"></a> queue:: value_type (STL/CLR)

요소의 형식입니다.

### <a name="syntax"></a>구문

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>설명

형식은 템플릿 매개 변수에 대 한 동의어 *값*합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_value_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display reversed contents " a b c" using value_type
    for (; !c1.empty(); c1.pop())
        {   // store element in value_type object
        Myqueue::value_type val = c1.front();

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="op_neq"></a> 연산자! = (queue) (STL/CLR)

큐 같지 않은지 비교 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value,
    typename Container>
    bool operator!=(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 왼쪽 컨테이너입니다.

*right*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수 반환 `!(left == right)`합니다. 테스트에 사용할 여부를 *왼쪽* 동일 정렬 되지 않은 *오른쪽* 두 큐 때 요소 별로 비교 합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_operator_ne.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] != [a b c] is {0}",
        c1 != c1);
    System::Console::WriteLine("[a b c] != [a b d] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] != [a b c] is False
[a b c] != [a b d] is True
```

## <a name="op_lt"></a> 연산자&lt; (queue) (STL/CLR)

큐 비교 보다 작습니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value,
    typename Container>
    bool operator<(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 왼쪽 컨테이너입니다.

*right*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수 경우 true를 반환, 가장 낮은 위치에 대 한 `i` 는 `!(right[i] < left[i])` 수도 있는 true는 `left[i] < right[i]`합니다. 그렇지 `left->` [queue:: size (STL/CLR)](../dotnet/queue-size-stl-clr.md) `() <` `right->size()` 테스트를 사용 하는지 여부를 *왼쪽* 앞에 정렬 되 *오른쪽* 두 개의 큐 때 요소 별로 비교 합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_operator_lt.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] < [a b c] is {0}",
        c1 < c1);
    System::Console::WriteLine("[a b c] < [a b d] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] < [a b c] is False
[a b c] < [a b d] is True
```

## <a name="op_lteq"></a> 연산자&lt;= (queue) (STL/CLR)

큐 보다 작거나 같은지 비교 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value,
    typename Container>
    bool operator<=(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 왼쪽 컨테이너입니다.

*right*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수 반환 `!(right < left)`합니다. 테스트에 사용할 여부를 *왼쪽* 후 정렬 되지 않은 *오른쪽* 두 큐 때 요소 별로 비교 합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_operator_le.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] <= [a b c] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] <= [a b c] is True
[a b d] <= [a b c] is False
```

## <a name="op_eq"></a> 연산자 = = (queue) (STL/CLR)

큐 같은지 비교 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value,
    typename Container>
    bool operator==(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 왼쪽 컨테이너입니다.

*right*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수는 시퀀스에 의해 제어 하는 경우에 true를 반환 *왼쪽* 하 고 *오른쪽* 동일한 길이 및 각 위치에 대 한 `i`, `left[i] ==` `right[i]`합니다. 테스트에 사용할 여부를 *왼쪽* 와 동일 하 게 정렬 됩니다 *오른쪽* 두 큐 때 요소 별로 비교 합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_operator_eq.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] == [a b c] is {0}",
        c1 == c1);
    System::Console::WriteLine("[a b c] == [a b d] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] == [a b c] is True
[a b c] == [a b d] is False
```

## <a name="op_gt"></a> 연산자&gt; (queue) (STL/CLR)

큐 보다 큰지 비교 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value,
    typename Container>
    bool operator>(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 왼쪽 컨테이너입니다.

*right*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수 반환 `right` `<` `left`합니다. 테스트에 사용할 여부를 *왼쪽* 후에 정렬 되 *오른쪽* 경우 두 개의 큐는 요소 별로 비교 합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_operator_gt.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] > [a b c] is {0}",
        c1 > c1);
    System::Console::WriteLine("[a b d] > [a b c] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] > [a b c] is False
[a b d] > [a b c] is True
```

## <a name="op_gteq"></a> 연산자&gt;= (queue) (STL/CLR)

보다 큰 큐 또는 같은지 비교 합니다.

### <a name="syntax"></a>구문

```cpp
template<typename Value,
    typename Container>
    bool operator>=(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 왼쪽 컨테이너입니다.

*right*<br/>
비교할 오른쪽 컨테이너입니다.

### <a name="remarks"></a>설명

연산자 함수 반환 `!(left < right)`합니다. 테스트에 사용할 여부를 *왼쪽* 하기 전에 정렬 되지 않은 *오른쪽* 두 큐 때 요소 별로 비교 합니다.

### <a name="example"></a>예제

```cpp
// cliext_queue_operator_ge.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] >= [a b c] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] >= [a b c] is True
[a b c] >= [a b d] is False
```