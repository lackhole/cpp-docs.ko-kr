---
title: shared_ptr 클래스
ms.date: 11/04/2016
f1_keywords:
- memory/std::shared_ptr
- memory/std::shared_ptr::element_type
- memory/std::shared_ptr::get
- memory/std::shared_ptr::owner_before
- memory/std::shared_ptr::reset
- memory/std::shared_ptr::swap
- memory/std::shared_ptr::unique
- memory/std::shared_ptr::use_count
- memory/std::shared_ptr::operator boolean-type
- memory/std::shared_ptr::operator*
- memory/std::shared_ptr::operator=
- memory/std::shared_ptr::operator->
helpviewer_keywords:
- std::shared_ptr [C++]
- std::shared_ptr [C++], element_type
- std::shared_ptr [C++], get
- std::shared_ptr [C++], owner_before
- std::shared_ptr [C++], reset
- std::shared_ptr [C++], swap
- std::shared_ptr [C++], unique
- std::shared_ptr [C++], use_count
- std::shared_ptr [C++], element_type
- std::shared_ptr [C++], get
- std::shared_ptr [C++], owner_before
- std::shared_ptr [C++], reset
- std::shared_ptr [C++], swap
- std::shared_ptr [C++], unique
- std::shared_ptr [C++], use_count
ms.assetid: 1469fc51-c658-43f1-886c-f4530dd84860
ms.openlocfilehash: 791a18461b3a0ee8237dec47c87f9d441221141d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412555"
---
# <a name="sharedptr-class"></a>shared_ptr 클래스

동적으로 할당된 개체 주위에 참조 횟수가 계산되는 스마트 포인터를 래핑합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
class shared_ptr;
```

## <a name="remarks"></a>설명

shared_ptr 클래스는 참조 개수 계산을 사용하여 리소스를 관리하는 개체를 설명합니다. `shared_ptr` 개체는 null 포인터를 소유하거나 보유한 리소스에 대한 포인터를 보유합니다. 둘 이상의 `shared_ptr` 개체가 리소스를 소유할 수 있습니다. 특정 리소스를 소유하는 마지막 `shared_ptr` 개체가 삭제되면 리소스가 해제됩니다.

다시 할당되거나 다시 설정되면 `shared_ptr`에서 리소스 소유가 중지됩니다.

특정 멤버 함수에 대해 언급된 경우를 제외하고 템플릿 인수 `T`는 불완전한 형식일 수 있습니다.

`G*` 형식의 리소스 포인터 또는 `shared_ptr<G>`에서 `shared_ptr<T>` 개체가 생성된 경우 포인터 형식 `G*`를 `T*`로 변환할 수 있어야 합니다. 그렇지 않으면 코드가 컴파일되지 않습니다. 예를 들어:

```cpp
#include <memory>
using namespace std;

class F {};
class G : public F {};

shared_ptr<G> sp0(new G);   // okay, template parameter G and argument G*
shared_ptr<G> sp1(sp0);     // okay, template parameter G and argument shared_ptr<G>
shared_ptr<F> sp2(new G);   // okay, G* convertible to F*
shared_ptr<F> sp3(sp0);     // okay, template parameter F and argument shared_ptr<G>
shared_ptr<F> sp4(sp2);     // okay, template parameter F and argument shared_ptr<F>
shared_ptr<int> sp5(new G); // error, G* not convertible to int*
shared_ptr<int> sp6(sp2);   // error, template parameter int and argument shared_ptr<F>
```

`shared_ptr` 개체가 리소스를 소유합니다.

- 해당 리소스에 대한 포인터를 사용하여 생성된 경우

- 해당 리소스를 소유하는 `shared_ptr` 개체에서 생성된 경우

- 해당 리소스를 가리키는 [weak_ptr 클래스](../standard-library/weak-ptr-class.md) 개체에서 생성된 경우 또는

- 해당 리소스의 소유권이 [shared_ptr::operator=](#op_eq)를 사용하여 또는 구성원 함수 [shared_ptr::reset](#reset)을 호출하여 할당된 경우

리소스를 소유하는 `shared_ptr` 개체는 제어 블록을 공유합니다. 제어 블록은 다음을 보유합니다.

- 리소스를 소유하는 `shared_ptr` 개체 수

- 리소스를 가리키는 `weak_ptr` 개체 수

- 해당 리소스에 대한 삭제자(있는 경우)

- 제어 블록에 대한 사용자 지정 할당자(있는 경우)

null 포인터를 사용하여 초기화된 `shared_ptr` 개체에는 제어 블록이 있고 비어 있지 않습니다. `shared_ptr` 개체가 리소스를 해제한 후에는 더 이상 해당 리소스를 소유하지 않습니다. `weak_ptr` 개체가 리소스를 해제한 후에는 더 이상 해당 리소스를 가리키지 않습니다.

리소스를 소유하는 `shared_ptr` 개체 수가 0이 되면 리소스의 소유권이 원래 생성된 방식에 따라 개체를 삭제하거나 개체 주소를 삭제자에 전달하여 리소스가 해제됩니다. 리소스를 소유하는 `shared_ptr` 개체 수가 0이고 해당 리소스를 가리키는 `weak_ptr` 개체 수가 0이면 제어 블록에 대한 사용자 지정 할당자를 사용하여(있는 경우) 제어 블록이 해제됩니다.

빈 `shared_ptr` 개체는 리소스를 소유하지 않으며 제어 블록이 없습니다.

삭제자는 멤버 함수 `operator()`가 있는 함수 개체입니다. 복사를 통해 해당 형식을 생성할 수 있어야 하며, 복사 생성자와 소멸자에서 예외가 발생하지 않아야 합니다. 삭제할 개체를 나타내는 매개 변수 하나를 사용합니다.

일부 함수는 결과 `shared_ptr<T>` 또는 `weak_ptr<T>` 개체의 속성을 정의하는 인수 목록을 사용합니다. 여러 가지 방법으로 이러한 인수 목록을 지정할 수 있습니다.

인수 없이 - 결과 개체는 빈 `shared_ptr` 개체 또는 빈 `weak_ptr` 개체입니다.

`ptr` - 관리할 리소스에 대한 `Other*` 형식의 포인터입니다. `T`는 완전한 형식이어야 합니다. 제어 블록을 할당할 수 없어 함수가 실패하면 `delete ptr` 식을 계산합니다.

`ptr, dtor` - 관리할 리소스에 대한 `Other*` 형식의 포인터 및 해당 리소스에 대한 삭제자입니다. 제어 블록을 할당할 수 없어 함수가 실패하면 `dtor(ptr)`을 호출하므로 잘 정의해야 합니다.

`ptr, dtor, alloc` -- 관리할 리소스에 대한 `Other*` 형식의 포인터, 해당 리소스에 대한 삭제자 및 할당하고 해제해야 하는 스토리지를 관리할 할당자입니다. 제어 블록을 할당할 수 없어 함수가 실패하면 `dtor(ptr)`을 호출하므로 잘 정의해야 합니다.

`sp` - 관리할 리소스를 소유하는 `shared_ptr<Other>` 개체입니다.

`wp` - 관리할 리소스를 가리키는 `weak_ptr<Other>` 개체입니다.

`ap` - 관리할 리소스에 대한 포인터를 보유하는 `auto_ptr<Other>` 개체입니다. 함수가 성공하면 `ap.release()`를 호출하고, 그렇지 않으면 `ap`를 변경하지 않고 그대로 둡니다.

모든 경우에서 포인터 형식 `Other*`를 `T*`로 변환할 수 있어야 합니다.

## <a name="thread-safety"></a>스레드로부터의 안전성

개체가 소유권을 공유하는 복사본이더라도 다중 스레드가 여러 `shared_ptr` 개체를 동시에 읽고 쓸 수 있습니다.

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[shared_ptr](#shared_ptr)|`shared_ptr`를 생성합니다.|
|[shared_ptr::~shared_ptr](#dtorshared_ptr)|`shared_ptr`을 삭제합니다.|

### <a name="types"></a>유형

|형식 이름|설명|
|-|-|
|[element_type](#element_type)|요소의 형식입니다.|

### <a name="functions"></a>함수

|기능|설명|
|-|-|
|[get](#get)|소유하는 리소스의 주소를 가져옵니다.|
|[owner_before](#owner_before)|`shared_ptr`이 제공된 포인터 앞에 정렬되는(또는 보다 작은) 경우 true를 반환합니다.|
|[reset](#reset)|소유하는 리소스를 대체합니다.|
|[swap](#swap)|두 `shared_ptr` 개체를 교환합니다.|
|[unique](#unique)|소유하는 리소스가 고유한지 테스트합니다.|
|[use_count](#use_count)|리소스 소유자 수를 계산합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[shared_ptr::operator bool](#op_bool)|소유하는 리소스가 있는지 테스트합니다.|
|[shared_ptr::operator*](#op_star)|지정된 값을 가져옵니다.|
|[shared_ptr::operator=](#op_eq)|소유하는 리소스를 대체합니다.|
|[shared_ptr::operator-&gt;](#op_arrow)|지정된 값으로 포인터를 가져옵니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<memory>

**네임스페이스:** std

## <a name="element_type"></a>  shared_ptr::element_type

요소의 형식입니다.

```cpp
typedef T element_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `T`의 동의어입니다.

### <a name="example"></a>예제

```cpp
// std__memory__shared_ptr_element_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::shared_ptr<int>::element_type val = *sp0;

    std::cout << "*sp0 == " << val << std::endl;

    return (0);
}
```

```Output
*sp0 == 5
```

## <a name="get"></a>  shared_ptr::get

소유하는 리소스의 주소를 가져옵니다.

```cpp
T *get() const;
```

### <a name="remarks"></a>설명

구성원 함수는 소유하는 리소스의 주소를 반환합니다. 개체가 리소스를 소유하지 않는 경우에는 0을 반환합니다.

### <a name="example"></a>예제

```cpp
// std__memory__shared_ptr_get.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0;
    std::shared_ptr<int> sp1(new int(5));

    std::cout << "sp0.get() == 0 == " << std::boolalpha
        << (sp0.get() == 0) << std::endl;
    std::cout << "*sp1.get() == " << *sp1.get() << std::endl;

    return (0);
}
```

```Output
sp0.get() == 0 == true
*sp1.get() == 5
```

## <a name="op_bool"></a>  shared_ptr::operator bool

소유하는 리소스가 있는지 테스트합니다.

```cpp
explicit operator bool() const noexcept;
```

### <a name="remarks"></a>설명

연산자의 값 반환 **true** 때 `get() != nullptr`고, 그렇지 않으면 **false**합니다.

### <a name="example"></a>예제

```cpp
// std__memory__shared_ptr_operator_bool.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0;
    std::shared_ptr<int> sp1(new int(5));

    std::cout << "(bool)sp0 == " << std::boolalpha
        << (bool)sp0 << std::endl;
    std::cout << "(bool)sp1 == " << std::boolalpha
        << (bool)sp1 << std::endl;

    return (0);
}
```

```Output
(bool)sp0 == false
(bool)sp1 == true
```

## <a name="op_star"></a>  shared_ptr::operator*

지정된 값을 가져옵니다.

```cpp
T& operator*() const;
```

### <a name="remarks"></a>설명

간접 연산자는 `*get()`을 반환합니다. 따라서 저장된 포인터는 null이 아니어야 합니다.

### <a name="example"></a>예제

```cpp
// std__memory__shared_ptr_operator_st.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));

    std::cout << "*sp0 == " << *sp0 << std::endl;

    return (0);
}
```

```Output
*sp0 == 5
```

## <a name="op_eq"></a>  shared_ptr::operator=

소유하는 리소스를 대체합니다.

```cpp
shared_ptr& operator=(const shared_ptr& sp);

template <class Other>
shared_ptr& operator=(const shared_ptr<Other>& sp);

template <class Other>
shared_ptr& operator=(auto_ptr<Other>& ap);

template <class Other>
shared_ptr& operator=(auto_ptr<Other>& ap);

template <class Other>
shared_ptr& operator=(auto_ptr<Other>&& ap);

template <class Other, class Deletor>
shared_ptr& operator=(unique_ptr<Other, Deletor>&& ap);
```

### <a name="parameters"></a>매개 변수

*sp*<br/>
복사할 공유 포인터입니다.

*ap*<br/>
복사할 자동 포인터입니다.

### <a name="remarks"></a>설명

모든 연산자는 현재 `*this`가 소유한 리소스의 참조 수를 줄이고 피연산자 시퀀스로 이름이 지정된 리소스의 소유권을 `*this`에 할당합니다. 참조 수가 0으로 감소하면 리소스가 해제됩니다. 연산자 실행이 실패하면 `*this`는 변경되지 않습니다.

### <a name="example"></a>예제

```cpp
// std__memory__shared_ptr_operator_as.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0;
    std::shared_ptr<int> sp1(new int(5));
    std::auto_ptr<int> ap(new int(10));

    sp0 = sp1;
    std::cout << "*sp0 == " << *sp0 << std::endl;

    sp0 = ap;
    std::cout << "*sp0 == " << *sp0 << std::endl;

    return (0);
}
```

```Output
*sp0 == 5
*sp0 == 10
```

## <a name="op_arrow"></a>  shared_ptr::operator-&gt;

지정된 값으로 포인터를 가져옵니다.

```cpp
T * operator->() const;
```

### <a name="remarks"></a>설명

선택 연산자는 `get()`을 반환합니다. 따라서 `sp->member` 식은 `(sp.get())->member`와 동일하게 동작하며, 여기서 `sp`는 클래스 `shared_ptr<T>`의 개체입니다. 따라서 저장된 포인터는 null이 아니어야 하며, `T`는 클래스, 구조체 또는 `member` 구성원이 있는 공용 구조체 형식이어야 합니다.

### <a name="example"></a>예제

```cpp
// std__memory__shared_ptr_operator_ar.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

typedef std::pair<int, int> Mypair;
int main()
{
    std::shared_ptr<Mypair> sp0(new Mypair(1, 2));

    std::cout << "sp0->first == " << sp0->first << std::endl;
    std::cout << "sp0->second == " << sp0->second << std::endl;

    return (0);
}
```

```Output
sp0->first == 1
sp0->second == 2
```

## <a name="owner_before"></a>  shared_ptr::owner_before

`shared_ptr`이 제공된 포인터 앞에 정렬되는(또는 보다 작은) 경우 true를 반환합니다.

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr);

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr);
```

### <a name="parameters"></a>매개 변수

*ptr*<br/>
`shared_ptr` 또는 `weak_ptr`에 대한 `lvalue` 참조입니다.

### <a name="remarks"></a>설명

템플릿 멤버 함수의 경우 true를 반환 `*this` 됩니다 `ordered before` `ptr`합니다.

## <a name="reset"></a>  shared_ptr::reset

소유하는 리소스를 대체합니다.

```cpp
void reset();

template <class Other>
void reset(Other *ptr;);

template <class Other, class D>
void reset(Other *ptr, D dtor);

template <class Other, class D, class A>
void reset(Other *ptr, D dtor, A alloc);
```

### <a name="parameters"></a>매개 변수

*기타*<br/>
인수 포인터에 의해 제어되는 형식입니다.

*D*<br/>
삭제자의 형식입니다.

*ptr*<br/>
복사할 포인터입니다.

*dtor*<br/>
복사할 deleter입니다.

*A*<br/>
할당자의 형식입니다.

*alloc*<br/>
복사할 할당자입니다.

### <a name="remarks"></a>설명

모든 연산자는 현재 `*this`가 소유한 리소스의 참조 수를 줄이고 피연산자 시퀀스로 이름이 지정된 리소스의 소유권을 `*this`에 할당합니다. 참조 수가 0으로 감소하면 리소스가 해제됩니다. 연산자 실행이 실패하면 `*this`는 변경되지 않습니다.

### <a name="example"></a>예제

```cpp
// std__memory__shared_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp(new int(5));

    std::cout << "*sp == " << std::boolalpha
        << *sp << std::endl;

    sp.reset();
    std::cout << "(bool)sp == " << std::boolalpha
        << (bool)sp << std::endl;

    sp.reset(new int(10));
    std::cout << "*sp == " << std::boolalpha
        << *sp << std::endl;

    sp.reset(new int(15), deleter());
    std::cout << "*sp == " << std::boolalpha
        << *sp << std::endl;

    return (0);
}
```

```Output
*sp == 5
(bool)sp == false
*sp == 10
*sp == 15
```

## <a name="shared_ptr"></a>  shared_ptr::shared_ptr

`shared_ptr`를 생성합니다.

```cpp
shared_ptr();

shared_ptr(nullptr_t);

shared_ptr(const shared_ptr& sp);

shared_ptr(shared_ptr&& sp);

template <class Other>
explicit shared_ptr(Other* ptr);

template <class Other, class D>
shared_ptr(Other* ptr, D dtor);

template <class D>
shared_ptr(nullptr_t ptr, D dtor);

template <class Other, class D, class A>
shared_ptr(Other* ptr, D dtor, A  alloc);

template <class D, class A>
shared_ptr(nullptr_t ptr, D dtor, A alloc);

template <class Other>
shared_ptr(const shared_ptr<Other>& sp);

template <class Other>
shared_ptr(const weak_ptr<Other>& wp);

template <class &>
shared_ptr(std::auto_ptr<Other>& ap);

template <class &>
shared_ptr(std::auto_ptr<Other>&& ap);

template <class Other, class D>
shared_ptr(unique_ptr<Other, D>&& up);

template <class Other>
shared_ptr(const shared_ptr<Other>& sp, T* ptr);

template <class Other, class D>
shared_ptr(const unique_ptr<Other, D>& up) = delete;
```

### <a name="parameters"></a>매개 변수

*기타*<br/>
인수 포인터에 의해 제어되는 형식입니다.

*ptr*<br/>
복사할 포인터입니다.

*D*<br/>
삭제자의 형식입니다.

*A*<br/>
할당자의 형식입니다.

*dtor*<br/>
삭제자입니다.

*ator*<br/>
할당자입니다.

*sp*<br/>
복사할 스마트 포인터입니다.

*wp*<br/>
취약 포인터입니다.

*ap*<br/>
복사할 자동 포인터입니다.

### <a name="remarks"></a>설명

각 생성자는 피연산자 시퀀스에 의해 이름이 지정되는 리소스를 소유하는 개체를 생성합니다. `shared_ptr(const weak_ptr<Other>& wp)` 생성자는 `wp.expired()`인 경우 [bad_weak_ptr 클래스](../standard-library/bad-weak-ptr-class.md) 형식의 예외 개체를 throw합니다.

### <a name="example"></a>예제

```cpp
// std__memory__shared_ptr_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp0;
    std::cout << "(bool)sp0 == " << std::boolalpha
        << (bool)sp0 << std::endl;

    std::shared_ptr<int> sp1(new int(5));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    std::shared_ptr<int> sp2(new int(10), deleter());
    std::cout << "*sp2 == " << *sp2 << std::endl;

    std::shared_ptr<int> sp3(sp2);
    std::cout << "*sp3 == " << *sp3 << std::endl;

    std::weak_ptr<int> wp(sp3);
    std::shared_ptr<int> sp4(wp);
    std::cout << "*sp4 == " << *sp4 << std::endl;

    std::auto_ptr<int> ap(new int(15));
    std::shared_ptr<int> sp5(ap);
    std::cout << "*sp5 == " << *sp5 << std::endl;

    return (0);
}
```

```Output
(bool)sp0 == false
*sp1 == 5
*sp2 == 10
*sp3 == 10
*sp4 == 10
*sp5 == 15
```

## <a name="dtorshared_ptr"></a>  shared_ptr::~shared_ptr

`shared_ptr`을 삭제합니다.

```cpp
~shared_ptr();
```

### <a name="remarks"></a>설명

소멸자는 현재 `*this`가 소유한 리소스의 참조 수를 줄입니다. 참조 수가 0으로 감소하면 리소스가 해제됩니다.

### <a name="example"></a>예제

```cpp
// std__memory__shared_ptr_destroy.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << "use count == " << sp1.use_count() << std::endl;

    {
        std::shared_ptr<int> sp2(sp1);
        std::cout << "*sp2 == " << *sp2 << std::endl;
        std::cout << "use count == " << sp1.use_count() << std::endl;
    }

    // check use count after sp2 is destroyed
    std::cout << "use count == " << sp1.use_count() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
use count == 1
*sp2 == 5
use count == 2
use count == 1
```

## <a name="swap"></a>  shared_ptr::swap

두 `shared_ptr` 개체를 교환합니다.

```cpp
void swap(shared_ptr& sp);
```

### <a name="parameters"></a>매개 변수

*sp*<br/>
교환할 공유 포인터입니다.

### <a name="remarks"></a>설명

멤버 함수는 원래 소유한 리소스를 남겨 둡니다 `*this` 소유 였다가 이후에 *sp*, 및 원래 소유한 리소스 *sp* 소유 였다가 이후에 `*this`합니다. 함수는 두 리소스의 참조 개수를 변경하지 않으며 예외도 throw하지 않습니다.

### <a name="example"></a>예제

```cpp
// std__memory__shared_ptr_swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
*sp1 == 10
*sp1 == 5

*wp1 == 5
*wp1 == 10
*wp1 == 5
```

## <a name="unique"></a>  shared_ptr::unique

소유하는 리소스가 고유한지 테스트합니다.

```cpp
bool unique() const;
```

### <a name="remarks"></a>설명

멤버 함수는 반환 **true** 이상 다른 `shared_ptr` 소유 하는 리소스를 소유 하는 개체 `*this`고, 그렇지 않으면 **false**합니다.

### <a name="example"></a>예제

```cpp
// std__memory__shared_ptr_unique.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::cout << "sp1.unique() == " << std::boolalpha
        << sp1.unique() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "sp1.unique() == " << std::boolalpha
        << sp1.unique() << std::endl;

    return (0);
}
```

```Output
sp1.unique() == true
sp1.unique() == false
```

## <a name="use_count"></a>  shared_ptr::use_count

리소스 소유자 수를 계산합니다.

```cpp
long use_count() const;
```

### <a name="remarks"></a>설명

구성원 함수는 `*this`의 소유인 리소스를 소유한 `shared_ptr` 개체의 수를 반환합니다.

### <a name="example"></a>예제

```cpp
// std__memory__shared_ptr_use_count.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::cout << "sp1.use_count() == "
        << sp1.use_count() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "sp1.use_count() == "
        << sp1.use_count() << std::endl;

    return (0);
}
```

```Output
sp1.use_count() == 1
sp1.use_count() == 2
```

## <a name="see-also"></a>참고자료

[weak_ptr 클래스](../standard-library/weak-ptr-class.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
