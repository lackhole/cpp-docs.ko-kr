---
title: less_equal 구조체
ms.date: 11/04/2016
f1_keywords:
- functional/std::less_equal
helpviewer_keywords:
- less_equal function
- less_equal struct
ms.assetid: 32085782-c7e0-4310-9b40-8aa3c1bff211
ms.openlocfilehash: 67a686b139ae4abbf25a42a994cceaba008decf5
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245379"
---
# <a name="lessequal-struct"></a>less_equal 구조체

작음-보다-또는-같음 연산을 수행 하는 이진 조건자 (`operator<=`) 인수에 대해 합니다.

## <a name="syntax"></a>구문

```cpp
template <class Type = void>
struct less_equal : public binary_function <Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator<=
template <>
struct less_equal<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const
    -> decltype(std::forward<T>(Left) <= std::forward<U>(Right));
};
```

### <a name="parameters"></a>매개 변수

*형식*하십시오 *T*, *U*\
지정되었거나 유추된 형식의 피연산자를 가져오는 `operator<=`를 지원하는 모든 형식입니다.

*왼쪽*\
작거나 같음 연산의 왼쪽 피연산자입니다. 형식의 lvalue 참조 인수를 사용 하는 특수화 되지 않은 템플릿은 *형식*합니다. 특수화 된 템플릿은 완벽 하 게 전달의 lvalue 및 rvalue 참조 인수 형식 유추 *T*합니다.

*오른쪽*\
작거나 같음 연산의 오른쪽 피연산자입니다. 형식의 lvalue 참조 인수를 사용 하는 특수화 되지 않은 템플릿은 *형식*합니다. 특수화 된 템플릿은 완벽 하 게 전달의 lvalue 및 rvalue 참조 인수 형식 유추 *U*합니다.

## <a name="return-value"></a>반환 값

`Left <= Right`의 결과입니다. 특수화된 템플릿은 `operator<=`에 의해 반환되는 형식을 가지고 있는 결과를 완벽하게 전달합니다.

## <a name="remarks"></a>설명

이진 조건자 `less_equal` < `Type`> 형식의 요소 값의 집합이 엄밀히 약한 정렬을 제공 *형식* 동등 클래스에이 이와 같은 수치는 표준 충족 하는 경우에 하 여 그렇게 정렬에 대 한 요구 사항입니다. 고유한 값의 모든 요소가 서로를 기준으로 정렬된다는 점에서 모든 포인터 형식에 대한 특수화는 요소의 전체 순서 지정을 생성합니다.

## <a name="example"></a>예제

```cpp
// functional_less_equal.cpp
// compile with: /EHsc
#define _CRT_RAND_S
#include <stdlib.h>
#include <vector>
#include <algorithm>
#include <functional>
#include <cstdlib>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;
   vector <int>::reverse_iterator rIter1;
   unsigned int randomNumber;

   int i;
   for ( i = 0 ; i < 5 ; i++ )
   {
      if ( rand_s( &randomNumber ) == 0 )
      {
         // Convert the random number to be between 1 - 50000
         // This is done for readability purposes
         randomNumber = ( unsigned int) ((double)randomNumber /
            (double) UINT_MAX * 50000) + 1;

         v1.push_back( randomNumber );
      }
   }
   for ( i = 0 ; i < 3 ; i++ )
   {
      v1.push_back( 2836 );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use the binary predicate less_equal<int>( )
   sort( v1.begin( ), v1.end( ), less_equal<int>( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = (31247 37154 48755 15251 6205 2836 2836 2836)
Sorted vector v1 = (2836 2836 2836 6205 15251 31247 37154 48755)
```
