---
title: binary_negate 클래스
ms.date: 02/21/2019
f1_keywords:
- functional/std::binary_negate
helpviewer_keywords:
- binary_negate class
ms.assetid: 7b86f02c-af7e-4c7f-9df1-08addae4dd65
ms.openlocfilehash: 5e00e398f1c43d0a8d762ca42c3f4f3ab51b9866
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414102"
---
# <a name="binarynegate-class"></a>binary_negate 클래스

지정된 이항 함수의 반환 값을 부정하는 멤버 함수를 제공하는 템플릿 클래스입니다. C + + 17 위해에서 사용 되지 않음 [not_fn](functional-functions.md#not_fn)합니다.

## <a name="syntax"></a>구문

```cpp
template <class Operation>
class binary_negate
    : public binaryFunction <typename Operation::first_argument_type,
                              typename Operation::second_argument_type, bool>
{
public:
    explicit binary_negate(const Operation& Func);
    bool operator()(const typename Operation::first_argument_type& left,
                    const typename Operation::second_argument_type& right) const;
};
```

### <a name="parameters"></a>매개 변수

*Func*<br/>
부정할 이항 함수입니다.

*left*<br/>
부정할 이항 함수의 왼쪽 피연산자입니다.

*right*<br/>
부정할 이항 함수의 오른쪽 피연산자입니다.

## <a name="return-value"></a>반환 값

이항 함수의 부정입니다.

## <a name="remarks"></a>설명

이항 함수 개체의 복사본을 저장 하는 템플릿 클래스 *Func*합니다. 해당 멤버 함수 정의 `operator()` 반환 `!Func(left, right)`합니다.

`binary_negate`의 생성자는 직접 사용되는 경우가 거의 없습니다. **binary_negator** 어댑터 조건자를 선언하고 사용하는 데 일반적으로 [not2](../standard-library/functional-functions.md#not2) 도우미 함수가 사용됩니다.

## <a name="example"></a>예제

```cpp
// functional_binary_negate.cpp
// compile with: /EHsc
#define _CRT_RAND_S
#include <stdlib.h>

#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   vector <unsigned int> v1;
   vector <unsigned int>::iterator Iter1;

   unsigned int i;
   v1.push_back( 6262 );
   v1.push_back( 6262 );
   unsigned int randVal = 0;
   for ( i = 0 ; i < 5 ; i++ )
   {
      rand_s(&randVal);
      v1.push_back( randVal );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use default binary predicate less<unsigned int>( )
   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order,
   // use the binary_negate function
   sort( v1.begin( ), v1.end( ),
   binary_negate<less<unsigned int> >(less<unsigned int>( ) ) );

   // The helper function not2 could also have been used
   // in the above line and is usually preferred for convenience
   // sort( v1.begin( ), v1.end( ), not2(less<unsigned int>( ) ) );

   cout << "Resorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
/* Output:
Original vector v1 = ( 6262 6262 2233879413 2621500314 580942933 3715465425 3739828298 )
Sorted vector v1 = ( 6262 6262 580942933 2233879413 2621500314 3715465425 3739828298 )
Resorted vector v1 = ( 3739828298 3715465425 2621500314 2233879413 580942933 6262 6262 )
*/
```

## <a name="requirements"></a>요구 사항

**헤더:** \<functional>

std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
