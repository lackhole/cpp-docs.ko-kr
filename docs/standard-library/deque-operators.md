---
title: '&lt;deque&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- deque/std::operator!=
- deque/std::operator&gt;
- deque/std::operator&gt;=
- deque/std::operator&lt;
- deque/std::operator&lt;=
- deque/std::operator==
ms.assetid: 482d7c92-54c7-493b-99e6-2a73617481a5
helpviewer_keywords:
- std::operator!= (deque)
- std::operator&gt; (deque)
- std::operator&gt;= (deque)
- std::operator&lt; (deque)
- std::operator&lt;= (deque)
- std::operator== (deque)
ms.openlocfilehash: a5e88d421df2746cf2ca0aab5be4c19953162559
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394002"
---
# <a name="ltdequegt-operators"></a>&lt;deque&gt; 연산자

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[연산자==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체와 같지 않은지 테스트합니다.

```cpp
bool operator!=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
`deque` 형식의 개체입니다.

*right*<br/>
`deque` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

deque 개체가 같지 않으면 **true**이고, deque 개체가 같으면 **false**입니다.

### <a name="remarks"></a>설명

deque 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소의 값이 같으면 두 deque 개체는 같은 것입니다. 그렇지 않으면 목록은 같지 않은 것입니다.

### <a name="example"></a>예제

```cpp
// deque_op_ne.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c2.push_back( 2 );

   if ( c1 != c2 )
      cout << "The deques are not equal." << endl;
   else
      cout << "The deques are equal." << endl;
}
/* Output:
The deques are not equal.
*/
```

## <a name="op_lt"></a>  operator&lt;

연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체보다 작은지 테스트합니다.

```cpp
bool operator<(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
`deque` 형식의 개체입니다.

*right*<br/>
`deque` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 deque가 연산자 우변의 deque보다 작으며 같지 않으면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

deque 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 보다 작음 관계는 같지 않은 요소의 첫 번째 쌍 비교를 기반으로 합니다.

### <a name="example"></a>예제

```cpp
// deque_op_lt.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 4 );

   c2.push_back( 1 );
   c2.push_back( 3 );

   if ( c1 < c2 )
      cout << "Deque c1 is less than deque c2." << endl;
   else
      cout << "Deque c1 is not less than deque c2." << endl;
}
/* Output:
Deque c1 is less than deque c2.
*/
```

## <a name="op_lt_eq"></a>  operator&lt;=

연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체보다 작거나 같은지 테스트합니다.

```cpp
bool operator<=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
`deque` 형식의 개체입니다.

*right*<br/>
`deque` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 deque가 연산자 우변의 deque보다 작거나 같지 않으면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

deque 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 작거나 같음 관계는 같지 않은 첫 번째 요소 쌍의 비교를 기반으로 합니다.

### <a name="example"></a>예제

```cpp
// deque_op_le.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 4 );

   c2.push_back( 1 );
   c2.push_back( 3 );

   if ( c1 <= c2 )
      cout << "Deque c1 is less than or equal to deque c2." << endl;
   else
      cout << "Deque c1 is greater than deque c2." << endl;
}
/* Output:
Deque c1 is less than or equal to deque c2.
*/
```

## <a name="op_eq_eq"></a>  operator==

연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체와 같은지 테스트합니다.

```cpp
bool operator==(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
`deque` 형식의 개체입니다.

*right*<br/>
`deque` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 deque가 연산자 우변의 deque와 같으면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

deque 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 포함된 요소 수가 같고 개별 요소의 값이 같으면 두 deque는 같은 것입니다. 그렇지 않으면 목록은 같지 않은 것입니다.

### <a name="example"></a>예제

```cpp
// deque_op_eq.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c2.push_back( 1 );

   if ( c1 == c2 )
      cout << "The deques are equal." << endl;
   else
      cout << "The deques are not equal." << endl;

   c1.push_back( 1 );
   if ( c1 == c2 )
      cout << "The deques are equal." << endl;
   else
      cout << "The deques are not equal." << endl;
}
/* Output:
The deques are equal.
The deques are not equal.
*/
```

## <a name="op_gt"></a>  operator&gt;

연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체보다 큰지 테스트합니다.

```cpp
bool operator>(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
`deque` 형식의 개체입니다.

*right*<br/>
`deque` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 deque가 연산자 우변의 deque보다 크면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

deque 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 보다 큼 관계는 같지 않은 요소의 첫 번째 쌍 비교를 기반으로 합니다.

### <a name="example"></a>예제

```cpp
// deque_op_gt.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c1.push_back( 3 );
   c1.push_back( 1 );

   c2.push_back( 1 );
   c2.push_back( 2 );
   c2.push_back( 2 );

   if ( c1 > c2 )
      cout << "Deque c1 is greater than deque c2." << endl;
   else
      cout << "Deque c1 is not greater than deque c2." << endl;
}
/* Output:
Deque c1 is greater than deque c2.
*/
```

## <a name="op_gt_eq"></a>  operator&gt;=

연산자의 좌변에 있는 deque 개체가 우변에 있는 deque 개체보다 크거나 같은지 테스트합니다.

```cpp
bool operator>=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
`deque` 형식의 개체입니다.

*right*<br/>
`deque` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 deque가 연산자 우변의 deque보다 크거나 같으면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

deque 개체 간의 비교는 해당 요소의 쌍 비교를 기반으로 합니다. 두 개체 간의 크거나 같음 관계는 같지 않은 첫 번째 요소 쌍의 비교를 기반으로 합니다.

### <a name="example"></a>예제

```cpp
// deque_op_ge.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c1.push_back( 3 );
   c1.push_back( 1 );

   c2.push_back( 1 );
   c2.push_back( 2 );
   c2.push_back( 2 );

   if ( c1 >= c2 )
      cout << "Deque c1 is greater than or equal to deque c2." << endl;
   else
      cout << "Deque c1 is less than deque c2." << endl;
}
/* Output:
Deque c1 is greater than or equal to deque c2.
*/
```

## <a name="see-also"></a>참고자료

[\<deque>](../standard-library/deque.md)<br/>
