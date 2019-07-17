---
title: less 구조체
ms.date: 11/04/2016
f1_keywords:
- functional/std::less
helpviewer_keywords:
- less struct
- less function
ms.assetid: 39349da3-11cd-4774-b2cc-b46af5aae5d7
ms.openlocfilehash: 13aef35856066f9c1897c3d8855c5ff537aa3567
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245344"
---
# <a name="less-struct"></a>less 구조체

작음 수행 하는 이진 조건자-작업 보다 (`operator<`) 인수에 대해 합니다.

## <a name="syntax"></a>구문

```cpp
template <class Type = void>
struct less : public binary_function <Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator<
template <>
struct less<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        -> decltype(std::forward<T>(Left) <std::forward<U>(Right));
};
```

### <a name="parameters"></a>매개 변수

*형식*하십시오 *T*, *U*\
지정되었거나 유추된 형식의 피연산자를 가져오는 `operator<`를 지원하는 모든 형식입니다.

*왼쪽*\
작음 연산의 왼쪽 피연산자입니다. 형식의 lvalue 참조 인수를 사용 하는 특수화 되지 않은 템플릿은 *형식*합니다. 특수화 된 템플릿은 완벽 하 게 전달의 lvalue 및 rvalue 참조 인수 형식 유추 *T*합니다.

*오른쪽*\
작음 연산의 오른쪽 피연산자입니다. 형식의 lvalue 참조 인수를 사용 하는 특수화 되지 않은 템플릿은 *형식*합니다. 특수화 된 템플릿은 완벽 하 게 전달의 lvalue 및 rvalue 참조 인수 형식 유추 *U*합니다.

## <a name="return-value"></a>반환 값

`Left < Right`의 결과입니다. 특수화된 템플릿은 `operator<`에 의해 반환되는 형식을 가지고 있는 결과를 완벽하게 전달합니다.

## <a name="remarks"></a>설명

이진 조건자 `less` < `Type`> 형식의 요소 값의 집합이 엄밀히 약한 정렬을 제공 *형식* 동등 클래스에이 이와 같은 수치는 표준 충족 하는 경우에 하 여 그렇게 정렬에 대 한 요구 사항입니다. 고유한 값의 모든 요소가 서로를 기준으로 정렬된다는 점에서 모든 포인터 형식에 대한 특수화는 요소의 전체 순서 지정을 생성합니다.

## <a name="example"></a>예제

```cpp
// functional_less.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

struct MyStruct {
   MyStruct(int i) : m_i(i){}

   bool operator < (const MyStruct & rhs) const {
      return m_i < rhs.m_i;
   }

   int m_i;
};

int main() {
   using namespace std;
   vector <MyStruct> v1;
   vector <MyStruct>::iterator Iter1;
   vector <MyStruct>::reverse_iterator rIter1;

   int i;
   for ( i = 0 ; i < 7 ; i++ )
       v1.push_back( MyStruct(rand()));

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )
cout << Iter1->m_i << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   sort( v1.begin( ), v1.end( ), less<MyStruct>());

   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin() ; Iter1 != v1.end() ; Iter1++ )
cout << Iter1->m_i << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = (41 18467 6334 26500 19169 15724 11478)
Sorted vector v1 = (41 6334 11478 15724 18467 19169 26500)
```
