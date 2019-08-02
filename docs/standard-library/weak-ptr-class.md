---
title: weak_ptr 클래스
ms.date: 07/29/2019
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
ms.openlocfilehash: d4ba30f737bc570a4ee700b3a317b5feebe8a50a
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682418"
---
# <a name="weakptr-class"></a>weak_ptr 클래스

약하게 링크된 포인터를 래핑합니다.

## <a name="syntax"></a>구문

```cpp
template<class T> class weak_ptr;
```

### <a name="parameters"></a>매개 변수

*트*\
약한 포인터에 의해 제어되는 형식입니다.

## <a name="remarks"></a>설명

이 템플릿 클래스는 하나 이상의 [shared_ptr](shared-ptr-class.md) 개체에서 관리 하는 리소스를 가리키는 개체를 설명 합니다. 리소스를 가리키는 개체는 리소스의 참조 횟수에 영향을 주지 않습니다. `weak_ptr` 해당 리소스를 `shared_ptr` 관리 하는 마지막 개체가 삭제 되 면 해당 리소스를 가리키는 `weak_ptr` 개체가 있는 경우에도 리소스가 해제 됩니다. 이 동작은 데이터 구조에서 순환을 방지 하는 데 필수적입니다.

`weak_ptr` 개체는 리소스를 소유하는 `shared_ptr` 개체에서 생성된 경우, 리소스를 가리키는 `weak_ptr` 개체에서 생성된 경우 또는 [operator=](#op_eq)를 사용하여 리소스가 할당된 경우 해당 리소스를 가리킵니다. 개체 `weak_ptr` 는 가리키는 리소스에 대 한 직접 액세스를 제공 하지 않습니다. 리소스를 사용해야 하는 코드는 구성원 함수 [lock](#lock)을 호출하여 만든, 해당 리소스를 소유하는 `shared_ptr` 개체를 통해 사용합니다. 리소스를 소유 하는 모든 `shared_ptr` 개체가 삭제 되어 개체가가리키는리소스가해제된경우개체가만료되었습니다.`weak_ptr` 만료된 `weak_ptr` 개체에 대해 `lock`을 호출하면 빈 shared_ptr 개체가 생성됩니다.

빈 weak_ptr 개체는 리소스를 가리키지 않으며 제어 블록이 없습니다. 멤버 함수 `lock`은 빈 shared_ptr 개체를 반환합니다.

`shared_ptr` 개체가 제어하는 둘 이상의 리소스가 상호 참조하는 `shared_ptr` 개체를 보유한 경우 순환이 발생합니다. 예를 들어 요소 세 개가 포함된 순환 연결된 목록에 헤드 노드 `N0`가 있습니다. 해당 노드는 다음 노드 `N1`을 소유하는 `shared_ptr` 개체를 보유합니다. 해당 노드는 다음 노드 `N2`를 소유하는 `shared_ptr` 개체를 보유합니다. 해당 노드는 다시 헤드 노드 `N0`을 소유하는 `shared_ptr` 개체를 보유하여 순환을 닫습니다. 이 경우 참조 횟수는 0이 되지 않으며 주기의 노드가 해제 되지 않습니다. 순환을 제거하려면 마지막 노드 `N2`가 `shared_ptr` 개체 대신 `N0`을 가리키는 `weak_ptr` 개체를 보유해야 합니다. 개체는 `weak_ptr` 소유 `N0` 하지 않으므로 참조 횟수에 `N0`영향을 주지 않으며, 헤드 노드에 대 한 프로그램의 마지막 참조가 제거 되 면 목록의 노드도 제거 됩니다.

## <a name="members"></a>멤버

|||
|-|-|
| **생성자** | |
|[weak_ptr](#weak_ptr)|`weak_ptr`를 생성합니다.|
| **소멸자** | |
|[~ weak_ptr](#tilde-weak_ptr)|`weak_ptr`를 생성합니다.|
| **Typedefs** | |
|[element_type](#element_type)|요소의 형식입니다.|
| **멤버 함수** | |
|[expired](#expired)|소유권이 만료되었는지 테스트합니다.|
|[lock](#lock)|리소스의 단독 소유권을 가져옵니다.|
|[owner_before](#owner_before)|이 이 `weak_ptr` 제공 된 포인터 앞에 정렬 (또는 보다 작음) 되는 경우 true를 반환 합니다.|
|[reset](#reset)|소유하는 리소스를 해제합니다.|
|[swap](#swap)|두 `weak_ptr` 개체를 교환합니다.|
|[use_count](#use_count)|`shared_ptr` 개체 수를 계산 합니다.|
| **연산자** | |
|[operator=](#op_eq)|소유하는 리소스를 대체합니다.|

## <a name="element_type"></a>element_type

요소의 형식입니다.

```cpp
typedef T element_type; // through C++17
using element_type = remove_extent_t<T>; // C++20
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `T`의 동의어입니다.

### <a name="example"></a>예제

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

## <a name="expired"></a>종료

소유권이 만료 되었는지 테스트 합니다. 즉, 참조 된 개체가 삭제 되었는지 테스트 합니다.

```cpp
bool expired() const noexcept;
```

### <a name="remarks"></a>설명

멤버 함수는가 만료 된 `*this` 경우 true를 반환 하 고 그렇지 않으면 **false**를 반환 합니다.

### <a name="example"></a>예제

```cpp
// std__memory__weak_ptr_expired.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

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

## <a name="lock"></a>잠기지

리소스의 `shared_ptr` 소유권을 공유 하는을 가져옵니다.

```cpp
shared_ptr<T> lock() const noexcept;
```

### <a name="remarks"></a>설명

멤버 함수는가 만료 된 경우 빈 [shared_ptr](shared-ptr-class.md) `*this` 개체를 반환 하 고, 그렇지 `shared_ptr<T>` 않은 경우에는 `*this` 가 가리키는 리소스를 소유 하는 개체를 반환 합니다. 의 `expired() ? shared_ptr<T>() : shared_ptr<T>(*this)`원자성 실행에 해당 하는 값을 반환 합니다.

### <a name="example"></a>예제

```cpp
// std__memory__weak_ptr_lock.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

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

## <a name="op_eq"></a>연산자 =

소유하는 리소스를 대체합니다.

```cpp
weak_ptr& operator=(const weak_ptr& ptr) noexcept;

template <class Other>
weak_ptr& operator=(const weak_ptr<Other>& ptr) noexcept;

template <class Other>
weak_ptr& operator=(const shared_ptr<Other>& ptr) noexcept;
```

### <a name="parameters"></a>매개 변수

*다른*\
인수 공유 또는 약한 포인터에 의해 제어 되는 형식입니다.

*ptr*\
복사할 약한 포인터 또는 공유 포인터입니다.

### <a name="remarks"></a>설명

연산자는 모두 현재가 `*this` 가리키는 리소스를 해제 하 고 명명 된 리소스의 소유권을에 `*this`할당 합니다. 연산자가 실패 하면 변경 되지 않은 `*this` 상태로 유지 됩니다. 각 연산자에는와 동일한 `weak_ptr(ptr).swap(*this)`효과가 있습니다.

### <a name="example"></a>예제

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

## <a name="owner_before"></a>owner_before

이 이 `weak_ptr` 제공 된 포인터 앞에 정렬 (또는 보다 작음) 되는 경우 true를 반환 합니다.

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr) const noexcept;

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr) const noexcept;
```

### <a name="parameters"></a>매개 변수

*ptr*\
`shared_ptr` 또는에 대 한 lvalue 참조 입니다.`weak_ptr`

### <a name="remarks"></a>설명

가 *ptr*이전에 정렬 된 경우 `*this` 템플릿 멤버 함수는 true를 반환 합니다.

## <a name="reset"></a>다시 설정

소유 된 리소스를 해제 합니다.

```cpp
void reset() noexcept;
```

### <a name="remarks"></a>설명

멤버 함수는가 `*this` 가리키는 리소스를 해제 하 고를 빈 `weak_ptr` 개체로 변환 `*this` 합니다.

### <a name="example"></a>예제

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

## <a name="swap"></a>스왑을

두 `weak_ptr` 개체를 교환합니다.

```cpp
void swap(weak_ptr& wp) noexcept;
```

특수화도 포함 합니다.

```cpp
template<class T>
void swap(weak_ptr<T>& a, weak_ptr<T>& b) noexcept;
```

### <a name="parameters"></a>매개 변수

*wp*\
교환할 취약 포인터입니다.

### <a name="remarks"></a>설명

`*this`이후에가 `*this` 처음 가리키는 리소스는 wp에서 가리키는 것 이며, 처음에는 wp에서 가리키는 리소스는에서 가리킵니다. `swap` 함수는 두 리소스에 대 한 참조 횟수를 변경 하지 않으며 예외를 throw 하지 않습니다. 템플릿 특수화 `a.swap(b)`의 효과는에 해당 합니다.

### <a name="example"></a>예제

```cpp
// std__memory__weak_ptr_swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

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

## <a name="use_count"></a>use_count

공유 리소스를 소유 `shared_ptr` 하는 개체 수를 계산 합니다.

```cpp
long use_count() const noexcept;
```

### <a name="remarks"></a>설명

구성원 함수는 `*this`가 가리키는 리소스를 소유한 `shared_ptr` 개체의 수를 반환합니다.

### <a name="example"></a>예제

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

## <a name="weak_ptr"></a>weak_ptr

`weak_ptr`를 생성합니다.

```cpp
constexpr weak_ptr() noexcept;

weak_ptr(const weak_ptr& wp) noexcept;

weak_ptr(weak_ptr&& wp) noexcept;

template <class Other>
weak_ptr(const weak_ptr<Other>& wp) noexcept;

template <class Other>
weak_ptr(weak_ptr<Other>&& sp) noexcept;

template <class Other>
weak_ptr(const shared_ptr<Other>& sp) noexcept;
```

### <a name="parameters"></a>매개 변수

*다른*\
인수 공유/취약 포인터에 의해 제어되는 형식입니다. 이러한 생성자는 오버 로드 확인에 참여 하지 않습니다. _그 외\*_  의 경우는와 `element_type*`호환 되지 않습니다.

*wp*\
복사할 취약 포인터입니다.

*sp-2*\
복사할 공유 포인터입니다.

### <a name="remarks"></a>설명

기본 생성자는 빈 `weak_ptr` 개체를 생성 합니다. 인수 포인터가 비어 있는 경우 각 인수를 사용 하 `weak_ptr` 는 생성자는 빈 개체를 생성 합니다. 그렇지 않으면 인수에 의해 `weak_ptr` 이름이 지정 된 리소스를 가리키는 개체를 생성 합니다. 공유 개체의 참조 횟수가 변경 되지 않습니다.

### <a name="example"></a>예제

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

## <a name="tilde-weak_ptr"></a>~ weak_ptr

`weak_ptr`을 삭제합니다.

```cpp
~weak_ptr();
```

### <a name="remarks"></a>설명

소멸자는이 `weak_ptr` 를 소멸 하지만 저장 된 포인터가 가리키는 개체의 참조 횟수에는 영향을 주지 않습니다.

## <a name="see-also"></a>참고자료

[헤더 파일 참조](cpp-standard-library-header-files.md)\
[\<memory>](memory.md)\
[shared_ptr 클래스](shared-ptr-class.md)
