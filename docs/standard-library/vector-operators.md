---
title: '&lt;vector&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- vector/std::operator!=
- vector/std::operator&gt;
- vector/std::operator&gt;=
- vector/std::operator&lt;
- vector/std::operator&lt;=
- vector/std::operator==
ms.assetid: 1d14f312-6f59-4ec7-88ae-95f89a558823
helpviewer_keywords:
- std::operator!= (vector)
- std::operator&gt; (vector)
- std::operator&gt;= (vector)
- std::operator&lt; (vector)
- std::operator&lt;= (vector)
- std::operator== (vector)
ms.openlocfilehash: f659f1291c4111d83cc8715fd0deb104a9685f4f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185947"
---
# <a name="ltvectorgt-operators"></a>&lt;vector&gt; 연산자

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[연산자==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

연산자의 좌변에 있는 개체가 우변에 있는 개체와 같지 않은지 테스트합니다.

```cpp
bool operator!=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
`vector` 형식의 개체입니다.

*right*<br/>
`vector` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

벡터가 같지 않으면 **true**이고 벡터가 같으면 **false**입니다.

### <a name="remarks"></a>설명

포함된 요소 수가 같고 개별 요소의 값이 같으면 두 벡터는 같은 것이고 그렇지 않으면 목록은 같지 않은 것입니다.

### <a name="example"></a>예제

```cpp
// vector_op_ne.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
     v2.push_back( 2 );

   if ( v1 != v2 )
      cout << "Vectors not equal." << endl;
   else
      cout << "Vectors equal." << endl;
}
```

```Output
Vectors not equal.
```

## <a name="op_lt"></a>  operator&lt;

연산자의 좌변에 있는 개체가 우변에 있는 개체보다 작은지 테스트합니다.

```cpp
bool operator<(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
`vector` 형식의 개체입니다.

*right*<br/>
`vector` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 벡터가 연산자 우변의 벡터보다 작으면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="example"></a>예제

```cpp
// vector_op_lt.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 4 );

   v2.push_back( 1 );
   v2.push_back( 3 );

   if ( v1 < v2 )
      cout << "Vector v1 is less than vector v2." << endl;
   else
      cout << "Vector v1 is not less than vector v2." << endl;
}
```

```Output
Vector v1 is less than vector v2.
```

## <a name="op_lt_eq"></a>  operator&lt;=

연산자의 좌변에 있는 개체가 우변에 있는 개체보다 작거나 같은지 테스트합니다.

```cpp
bool operator<=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
`vector` 형식의 개체입니다.

*right*<br/>
`vector` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 벡터가 연산자 우변의 벡터보다 작거나 같으면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="example"></a>예제

```cpp
// vector_op_le.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 4 );

   v2.push_back( 1 );
   v2.push_back( 3 );

   if ( v1 <= v2 )
      cout << "Vector v1 is less than or equal to vector v2." << endl;
   else
      cout << "Vector v1 is greater than vector v2." << endl;
}
```

```Output
Vector v1 is less than or equal to vector v2.
```

## <a name="op_eq_eq"></a>  operator==

연산자의 좌변에 있는 개체가 우변에 있는 개체와 같은지 테스트합니다.

```cpp
bool operator==(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
`vector` 형식의 개체입니다.

*right*<br/>
`vector` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 벡터가 연산자 우변의 벡터와 같으면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

포함된 요소 수가 같고 개별 요소의 값이 같으면 두 벡터는 같은 것이고 그렇지 않으면 목록은 같지 않은 것입니다.

### <a name="example"></a>예제

```cpp
// vector_op_eq.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v2.push_back( 1 );

   if ( v1 == v2 )
      cout << "Vectors equal." << endl;
   else
      cout << "Vectors not equal." << endl;
}
```

```Output
Vectors equal.
```

## <a name="op_gt"></a>  operator&gt;

연산자의 좌변에 있는 개체가 우변에 있는 개체보다 큰지 테스트합니다.

```cpp
bool operator>(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
`vector` 형식의 개체입니다.

*right*<br/>
`vector` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 벡터가 연산자 우변의 벡터보다 크면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="example"></a>예제

```cpp
// vector_op_gt.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 3 );
   v1.push_back( 1 );

   v2.push_back( 1 );
   v2.push_back( 2 );
   v2.push_back( 2 );

   if ( v1 > v2 )
      cout << "Vector v1 is greater than vector v2." << endl;
   else
      cout << "Vector v1 is not greater than vector v2." << endl;
}
```

```Output
Vector v1 is greater than vector v2.
```

## <a name="op_gt_eq"></a>  operator&gt;=

연산자의 좌변에 있는 개체가 우변에 있는 개체보다 크거나 같은지 테스트합니다.

```cpp
bool operator>=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
`vector` 형식의 개체입니다.

*right*<br/>
`vector` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 벡터가 벡터 우변의 벡터보다 크거나 같으면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="example"></a>예제

```cpp
// vector_op_ge.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 3 );
   v1.push_back( 1 );

     v2.push_back( 1 );
   v2.push_back( 2 );
   v2.push_back( 2 );

   if ( v1 >= v2 )
      cout << "Vector v1 is greater than or equal to vector v2." << endl;
   else
      cout << "Vector v1 is less than vector v2." << endl;
}
```

```Output
Vector v1 is greater than or equal to vector v2.
```

## <a name="see-also"></a>참고자료

[\<vector>](../standard-library/vector.md)<br/>
