---
title: weak_ptr 클래스
ms.date: 11/04/2016
f1_keywords:
- memory/std::weak_ptr
- memory/std::weak_ptr::element_type
- memory/std::weak_ptr::expired
- memory/std::weak_ptr::lock
- memory/std::weak_ptr::owner_before
- memory/std::weak_ptr::reset
- memory/std::weak_ptr::swap
- memory/std::weak_ptr::use_count
- memory/std::weak_ptr::operator=
helpviewer_keywords:
- std::weak_ptr [C++]
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
ms.assetid: 2db4afb2-c7be-46fc-9c20-34ec2f8cc7c2
ms.openlocfilehash: e491c376f110f48b0b02a30fc39f6c6da1a5ab02
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240905"
---
# <a name="weakptr-class"></a>weak_ptr 클래스

약하게 링크된 포인터를 래핑합니다.

## <a name="syntax"></a>구문

```cpp
template<class _Ty>
   class weak_ptr {
public:
   typedef Ty element_type;
   weak_ptr();
   weak_ptr(const weak_ptr&);
   template <class Other>
      weak_ptr(const weak_ptr<Other>&);
   template <class Other>
      weak_ptr(const shared_ptr<Other>&);
   weak_ptr& operator=(const weak_ptr&);
   template <class Other>
      weak_ptr& operator=(const weak_ptr<Other>&);
   template <class Other>
      weak_ptr& operator=(shared_ptr<Other>&);
      
   void swap(weak_ptr&);
   void reset();
   long use_count() const;
   bool expired() const;
   shared_ptr<Ty> lock() const;
};
```

### <a name="parameters"></a>매개 변수

*Ty*\
약한 포인터에 의해 제어되는 형식입니다.

## <a name="remarks"></a>설명

이 템플릿 클래스는 하나 이상의 [shared_ptr Class](../standard-library/shared-ptr-class.md) 개체에 의해 관리되는 리소스를 가리키는 개체를 설명합니다. 리소스를 가리키는 `weak_ptr` 개체는 리소스의 참조 횟수에 영향을 주지 않습니다. 따라서 해당 리소스를 관리하는 마지막 `shared_ptr` 개체가 삭제되면 해당 리소스를 가리키는 `weak_ptr` 개체가 있는 경우에도 리소스가 해제됩니다. 이는 데이터 구조에서 순환을 방지하는 데 필요합니다.

`weak_ptr` 개체는 리소스를 소유하는 `shared_ptr` 개체에서 생성된 경우, 리소스를 가리키는 `weak_ptr` 개체에서 생성된 경우 또는 [operator=](#op_eq)를 사용하여 리소스가 할당된 경우 해당 리소스를 가리킵니다. `weak_ptr` 개체는 가리키는 리소스에 대한 직접 액세스를 제공하지 않습니다. 리소스를 사용해야 하는 코드는 구성원 함수 [lock](#lock)을 호출하여 만든, 해당 리소스를 소유하는 `shared_ptr` 개체를 통해 사용합니다. 리소스를 소유하는 모든 `shared_ptr` 개체가 삭제되어 `weak_ptr` 개체가 가리키는 리소스가 해제된 경우 개체가 만료되었습니다. 만료된 `weak_ptr` 개체에 대해 `lock`을 호출하면 빈 shared_ptr 개체가 생성됩니다.

빈 weak_ptr 개체는 리소스를 가리키지 않으며 제어 블록이 없습니다. 멤버 함수 `lock`은 빈 shared_ptr 개체를 반환합니다.

`shared_ptr` 개체가 제어하는 둘 이상의 리소스가 상호 참조하는 `shared_ptr` 개체를 보유한 경우 순환이 발생합니다. 예를 들어 요소 세 개가 포함된 순환 연결된 목록에 헤드 노드 `N0`가 있습니다. 해당 노드는 다음 노드 `N1`을 소유하는 `shared_ptr` 개체를 보유합니다. 해당 노드는 다음 노드 `N2`를 소유하는 `shared_ptr` 개체를 보유합니다. 해당 노드는 다시 헤드 노드 `N0`을 소유하는 `shared_ptr` 개체를 보유하여 순환을 닫습니다. 이 경우 참조 횟수는 결코 0이 되지 않으며 순환의 노드가 해제되지 않습니다. 순환을 제거하려면 마지막 노드 `N2`가 `shared_ptr` 개체 대신 `N0`을 가리키는 `weak_ptr` 개체를 보유해야 합니다. `weak_ptr` 개체는 `N0`을 소유하지 않으므로 `N0`의 참조 횟수에 영향을 주지 않으며, 헤드 노드에 대한 프로그램의 마지막 참조가 삭제되면 목록의 노드도 삭제됩니다.

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|||
|-|-|
|[weak_ptr](#weak_ptr)|`weak_ptr`를 생성합니다.|

### <a name="methods"></a>메서드

|||
|-|-|
|[element_type](#element_type)|요소의 형식입니다.|
|[expired](#expired)|소유권이 만료되었는지 테스트합니다.|
|[lock](#lock)|리소스의 단독 소유권을 가져옵니다.|
|[owner_before](#owner_before)|반환 **true** 이 `weak_ptr` 앞에 정렬 됩니다 (또는 미만) 제공 된 포인터입니다.|
|[reset](#reset)|소유하는 리소스를 해제합니다.|
|[swap](#swap)|두 `weak_ptr` 개체를 교환합니다.|
|[use_count](#use_count)|지정된 `shared_ptr` 개체 수를 계산합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator=](#op_eq)|소유하는 리소스를 대체합니다.|

### <a name="element_type"></a> element_type

요소의 형식입니다.

```cpp
typedef Ty element_type;
```

#### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `Ty`의 동의어입니다.

#### <a name="example"></a>예제

```cpp
// std__memory__weak_ptr_element_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::weak_ptr<int>::element_type val = *wp0.lock();

    std::cout << "*wp0.lock() == " << val << std::endl;

    return (0);
    }
```

```Output
*wp0.lock() == 5
```

### <a name="expired"></a> 만료

소유권이 만료되었는지 테스트합니다.

```cpp
bool expired() const;
```

#### <a name="remarks"></a>설명

멤버 함수는 반환 **true** 하는 경우 `*this` 그렇지 않은 경우 만료 되었습니다 **false**합니다.

#### <a name="example"></a>예제

```cpp
// std__memory__weak_ptr_expired.cpp
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
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}
```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

### <a name="lock"></a> 잠금

리소스의 단독 소유권을 가져옵니다.

```cpp
shared_ptr<Ty> lock() const;
```

#### <a name="remarks"></a>설명

멤버 함수는 빈 shared_ptr 개체를 반환 하는 경우 `*this` 만료 되 면 그렇지 않으면 반환를 [shared_ptr 클래스](../standard-library/shared-ptr-class.md)\<Ty >는 리소스를 소유 하는 개체 `*this` 가리킵니다.

#### <a name="example"></a>예제

```cpp
// std__memory__weak_ptr_lock.cpp
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
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}
```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

### <a name="op_eq"></a> 연산자 =

소유하는 리소스를 대체합니다.

```cpp
weak_ptr& operator=(const weak_ptr& wp);

template <class Other>
    weak_ptr& operator=(const weak_ptr<Other>& wp);

template <class Other>
    weak_ptr& operator=(const shared_ptr<Other>& sp);
```

#### <a name="parameters"></a>매개 변수

*다른*\
인수 공유/취약 포인터에 의해 제어되는 형식입니다.

*wp*\
복사할 취약 포인터입니다.

*sp*\
복사할 공유 포인터입니다.

#### <a name="remarks"></a>설명

모든 연산자는 현재 `*this`가 가리키는 리소스를 해제하고 피연산자 시퀀스로 이름이 지정된 리소스의 소유권을 `*this`에 할당합니다. 연산자 실행이 실패하면 `*this`는 변경되지 않은 상태로 유지됩니다.

#### <a name="example"></a>예제

```cpp
// std__memory__weak_ptr_operator_as.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::shared_ptr<int> sp1(new int(10));
    wp0 = sp1;
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::weak_ptr<int> wp1;
    wp1 = wp0;
    std::cout << "*wp1.lock() == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*wp0.lock() == 5
*wp0.lock() == 10
*wp1.lock() == 10
```

### <a name="owner_before"></a> owner_before

반환 **true** 이 `weak_ptr` 앞에 정렬 됩니다 (또는 미만) 제공 된 포인터입니다.

```cpp
template <class Other>
    bool owner_before(const shared_ptr<Other>& ptr);

template <class Other>
    bool owner_before(const weak_ptr<Other>& ptr);
```

#### <a name="parameters"></a>매개 변수

*ptr*\
`shared_ptr` 또는 `weak_ptr`에 대한 `lvalue` 참조입니다.

#### <a name="remarks"></a>설명

템플릿 구성원 함수 반환 **true** 하는 경우 `*this` 됩니다 `ordered before` `ptr`합니다.

### <a name="reset"></a> 다시 설정

소유하는 리소스를 해제합니다.

```cpp
void reset();
```

#### <a name="remarks"></a>설명

구성원 함수는 `*this`가 가리키는 리소스를 해제하고 `*this`를 빈 weak_ptr 개체로 변환합니다.

#### <a name="example"></a>예제

```cpp
// std__memory__weak_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp(new int(5));
    std::weak_ptr<int> wp(sp);
    std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    wp.reset();
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    return (0);
}
```

```Output
*wp.lock() == 5
wp.expired() == false
wp.expired() == true
```

### <a name="swap"></a> 교환

두 `weak_ptr` 개체를 교환합니다.

```cpp
void swap(weak_ptr& wp);
```

특수화를 포함 되어 있습니다.

```cpp
template<class T>
    void swap(weak_ptr<T>& a, weak_ptr<T>& b) noexcept;
```

#### <a name="parameters"></a>매개 변수

*wp*\
교환할 취약 포인터입니다.

#### <a name="remarks"></a>설명

멤버 함수에서 원래 가리키는 리소스를 남겨 둡니다 `*this` 리 켰다가 이후에 *wp*, 및 원래에서 가리키는 리소스 *wp* 리 켰다가 이후에 `*this`. 함수는 두 리소스의 참조 개수를 변경하지 않으며 예외도 throw하지 않습니다.

#### <a name="example"></a>예제

```cpp
// std__memory__weak_ptr_swap.cpp
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

### <a name="use_count"></a> use_count

지정된 `shared_ptr` 개체 수를 계산합니다.

```cpp
long use_count() const;
```

#### <a name="remarks"></a>설명

구성원 함수는 `*this`가 가리키는 리소스를 소유한 `shared_ptr` 개체의 수를 반환합니다.

#### <a name="example"></a>예제

```cpp
// std__memory__weak_ptr_use_count.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    return (0);
}
```

```Output
wp.use_count() == 1
wp.use_count() == 2
```

### <a name="weak_ptr"></a> weak_ptr

`weak_ptr`를 생성합니다. 소멸자가 포함 됩니다.

```cpp
weak_ptr();

weak_ptr(const weak_ptr& wp);

template <class Other>
    weak_ptr(const weak_ptr<Other>& wp);

template <class Other>
    weak_ptr(const shared_ptr<Other>& sp);

~weak_ptr();
```

#### <a name="parameters"></a>매개 변수

*다른*\
인수 공유/취약 포인터에 의해 제어되는 형식입니다.

*wp*\
복사할 취약 포인터입니다.

*sp*\
복사할 공유 포인터입니다.

#### <a name="remarks"></a>설명

각 생성자는 피연산자 시퀀스에 의해 이름이 지정되는 리소스를 가리키는 개체를 생성합니다.

#### <a name="example"></a>예제

```cpp
// std__memory__weak_ptr_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp0;
    std::cout << "wp0.expired() == " << std::boolalpha
        << wp0.expired() << std::endl;

    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp1(sp1);
    std::cout << "*wp1.lock() == "
        << *wp1.lock() << std::endl;

    std::weak_ptr<int> wp2(wp1);
    std::cout << "*wp2.lock() == "
        << *wp2.lock() << std::endl;

    return (0);
}
```

```Output
wp0.expired() == true
*wp1.lock() == 5
*wp2.lock() == 5
```
