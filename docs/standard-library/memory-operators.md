---
title: '&lt;memory&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- memory/std::operator!=
- memory/std::operator>
- memory/std::operator>=
- memory/std::operator<
- memory/std::operator<=
- memory/std::operator<<
- memory/std::operator==
ms.assetid: 257e3ba9-c4c2-4ae8-9b11-b156ba9c28de
ms.openlocfilehash: ca1412efb4d095ef9a371b3739d4c282683821dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348460"
---
# <a name="ltmemorygt-operators"></a>&lt;memory&gt; 연산자

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|
|[연산자==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

개체 간의 같지 않음을 테스트합니다.

```cpp
template <class Type, class Other>
bool operator!=(
    const allocator<Type>& left,
    const allocator<Other>& right) throw();

template <class T, class Del1, class U, class Del2>
bool operator!=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator!=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
같지 않음을 테스트할 개체 중 하나입니다.

*right*<br/>
같지 않음을 테스트할 개체 중 하나입니다.

*Ty1*<br/>
왼쪽 공유 포인터로 제어되는 형식입니다.

*Ty2*<br/>
오른쪽 공유 포인터로 제어되는 형식입니다.

### <a name="return-value"></a>반환 값

개체가 같지 않으면 **true**이고, 개체가 같으면 **false**입니다.

### <a name="remarks"></a>설명

첫 번째 템플릿 연산자는 false를 반환합니다. (모든 기본 할당자가 같습니다.)

두 번째 및 세 번째 템플릿 연산자는 `!(left == right)`을 반환합니다.

### <a name="example"></a>예제

```cpp
// memory_op_me.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<double> Alloc;
   vector <char>:: allocator_type v1Alloc;

   if ( Alloc != v1Alloc )
      cout << "The allocator objects Alloc & v1Alloc not are equal."
           << endl;
   else
      cout << "The allocator objects Alloc & v1Alloc are equal."
           << endl;
}
```

```Output
The allocator objects Alloc & v1Alloc are equal.
```

### <a name="example"></a>예제

```cpp
// std__memory__operator_ne.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(0));
    std::shared_ptr<int> sp1(new int(0));

    std::cout << "sp0 != sp0 == " << std::boolalpha
        << (sp0 != sp0) << std::endl;
    std::cout << "sp0 != sp1 == " << std::boolalpha
        << (sp0 != sp1) << std::endl;

    return (0);
    }
```

```Output
sp0 != sp0 == false
sp0 != sp1 == true
```

## <a name="op_eq_eq"></a>  operator==

개체 간의 같음을 테스트합니다.

```cpp
template <class Type, class Other>
bool operator==(
    const allocator<Type>& left,
    const allocator<Other>& right) throw();

template <class Ty1, class Del1, class Ty2, class Del2>
bool operator==(
    const unique_ptr<Ty1, Del1>& left,
    const unique_ptr<Ty2, Del2>& right);

template <class Ty1, class Ty2>
bool operator==(
    const shared_ptr<Ty1>& left;,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
같은지 여부를 테스트할 개체 중 하나입니다.

*right*<br/>
같은지 여부를 테스트할 개체 중 하나입니다.

*Ty1*<br/>
왼쪽 공유 포인터로 제어되는 형식입니다.

*Ty2*<br/>
오른쪽 공유 포인터로 제어되는 형식입니다.

### <a name="return-value"></a>반환 값

**true 이면** 개체가 같으면 **false** 개체 같지 않은 경우.

### <a name="remarks"></a>설명

첫 번째 템플릿 연산자는 true를 반환합니다. (모든 기본 할당자가 같습니다.)

두 번째 및 세 번째 템플릿 연산자는 `left.get() ==  right.get()`을 반환합니다.

### <a name="example"></a>예제

```cpp
// memory_op_eq.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<char> Alloc;
   vector <int>:: allocator_type v1Alloc;

   allocator<char> cAlloc(Alloc);
   allocator<int> cv1Alloc(v1Alloc);

   if ( cv1Alloc == v1Alloc )
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."
           << endl;

   if ( cAlloc == Alloc )
      cout << "The allocator objects cAlloc & Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cAlloc & Alloc are not equal."
           << endl;
}
```

```Output
The allocator objects cv1Alloc & v1Alloc are equal.
The allocator objects cAlloc & Alloc are equal.
```

### <a name="example"></a>예제

```cpp
// std__memory__operator_eq.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(0));
    std::shared_ptr<int> sp1(new int(0));

    std::cout << "sp0 == sp0 == " << std::boolalpha
        << (sp0 == sp0) << std::endl;
    std::cout << "sp0 == sp1 == " << std::boolalpha
        << (sp0 == sp1) << std::endl;

    return (0);
    }
```

```Output
sp0 == sp0 == true
sp0 == sp1 == false
```

## <a name="op_gt_eq"></a>  operator&gt;=

한 개체가 두 번째 개체보다 크거나 같은지 테스트합니다.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator>=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U, Del2>& right);

template <class Ty1, class Ty2>
bool operator>=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 개체 중 하나입니다.

*right*<br/>
비교할 개체 중 하나입니다.

*Ty1*<br/>
왼쪽 공유 포인터로 제어되는 형식입니다.

*Ty2*<br/>
오른쪽 공유 포인터로 제어되는 형식입니다.

### <a name="remarks"></a>설명

템플릿 연산자 반환 `left.get() >= right.get()`합니다.

## <a name="op_lt"></a>  operator&lt;

한 개체가 두 번째 개체보다 작은지 테스트합니다.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator<(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator<(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 개체 중 하나입니다.

*right*<br/>
비교할 개체 중 하나입니다.

*Ty1*<br/>
왼쪽 포인터에 의해 제어되는 형식입니다.

*Ty2*<br/>
오른쪽 포인터에 의해 제어되는 형식입니다.

## <a name="op_lt_eq"></a>  operator&lt;=

한 개체가 두 번째 개체보다 작거나 같은지 테스트합니다.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator<=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator<=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 개체 중 하나입니다.

*right*<br/>
비교할 개체 중 하나입니다.

*Ty1*<br/>
왼쪽 공유 포인터로 제어되는 형식입니다.

*Ty2*<br/>
오른쪽 공유 포인터로 제어되는 형식입니다.

### <a name="remarks"></a>설명

템플릿 연산자 반환 `left.get() <= right.get()`

## <a name="op_gt"></a>  operator&gt;

한 개체가 두 번째 개체보다 큰지 테스트합니다.

```cpp
template <class Ty1, class Del1, class Ty2, class Del2>
bool operator>(
    const unique_ptr<Ty1, Del1>& left,
    const unique_ptr<Ty2&, Del2gt;& right);

template <class Ty1, class Ty2>
bool operator>(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
비교할 개체 중 하나입니다.

*right*<br/>
비교할 개체 중 하나입니다.

*Ty1*<br/>
왼쪽 공유 포인터로 제어되는 형식입니다.

*Ty2*<br/>
오른쪽 공유 포인터로 제어되는 형식입니다.

## <a name="op_lt_lt"></a>  operator&lt;&lt;

공유 포인터를 스트림에 씁니다.

```cpp
template <class Elem, class Tr, class Ty>
std::basic_ostream<Elem, Tr>& operator<<(std::basic_ostream<Elem, Tr>& out,
    shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>매개 변수

*Elem*<br/>
스트림 요소의 형식입니다.

*Tr*<br/>
스트림 요소 특성의 형식입니다.

*Ty*<br/>
공유 포인터에 의해 제어되는 형식입니다.

*out*<br/>
출력 스트림입니다.

*sp*<br/>
공유 포인터입니다.

### <a name="remarks"></a>설명

템플릿 함수가 `out << sp.get()`을 반환합니다.

### <a name="example"></a>예제

```cpp
// std__memory__operator_sl.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(5));

    std::cout << "sp0 == " << sp0 << " (varies)" << std::endl;

    return (0);
    }
```

```Output
sp0 == 3f3040 (varies)
```

## <a name="see-also"></a>참고자료

[\<memory>](../standard-library/memory.md)<br/>
