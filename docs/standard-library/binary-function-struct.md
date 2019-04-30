---
title: binary_function 구조체
ms.date: 02/21/2019
f1_keywords:
- functional/std::binary_function
helpviewer_keywords:
- binary_function class
ms.assetid: 79b6d53d-644c-4add-b0ba-3a5f40f69c60
ms.openlocfilehash: 2a6735ab558480039a0d2fa0e83ee4c5de02c5f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414095"
---
# <a name="binaryfunction-struct"></a>binary_function 구조체

이항 함수 개체를 제공하는 파생 클래스에 상속될 수 있는 형식을 정의하는 빈 기본 구조체입니다. C++17에서 제거 하는 C + + 11에서 사용 되지 않습니다.

## <a name="syntax"></a>구문

```cpp
struct binary_function {
   typedef Arg1 first_argument_type;
   typedef Arg2 second_argument_type;
   typedef Result result_type;
   };
```

## <a name="remarks"></a>설명

템플릿 구조체는 다음 형식의 멤버 함수를 정의하는 클래스의 기준으로 사용됩니다.

> *result_type* ** operator()( const** <em>first_argument_type</em>**&, const** <em>second_argument_type</em>**& ) const**

이러한 모든 이항 함수는 첫 번째 인수 형식을 *first_argument_type*, 두 번째 인수 형식을 *second_argument_type*, 반환 형식을 *result_type*으로 참조할 수 있습니다.

## <a name="example"></a>예제

```cpp
// functional_binary_function.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

template <class Type> class average:
binary_function<Type, Type, Type>
{
public:
   result_type operator( ) ( first_argument_type a,
                 second_argument_type b )
   {
      return (result_type) ( ( a + b ) / 2 );
   }
};

int main( )
{
   vector <double> v1, v2, v3 ( 6 );
   vector <double>::iterator Iter1, Iter2, Iter3;

   for ( int i = 1 ; i <= 6 ; i++ )
      v1.push_back( 11.0 / i );

   for ( int j = 0 ; j <= 5 ; j++ )
      v2.push_back( -2.0 * j );

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Finding the element-wise averages of the elements of v1 & v2
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      average<double>( ) );

   cout << "The element-wise averages are: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
/* Output:
The vector v1 = ( 11 5.5 3.66667 2.75 2.2 1.83333 )
The vector v2 = ( -0 -2 -4 -6 -8 -10 )
The element-wise averages are: ( 5.5 1.75 -0.166667 -1.625 -2.9 -4.08333 )
*/
```

## <a name="requirements"></a>요구 사항

**헤더:** \<functional>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
