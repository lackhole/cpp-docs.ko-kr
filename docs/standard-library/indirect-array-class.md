---
title: indirect_array 클래스
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 6be0c5153cbc94d09b414fc9e14fa498c7a4cfa7
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687914"
---
# <a name="indirect_array-class"></a>indirect_array 클래스

부모 valarray의 인덱스 하위 집합을 지정 하 여 정의 된 하위 집합 배열 간의 작업을 제공 하 여 valarray의 하위 집합인 개체를 지 원하는 내부 보조 클래스 템플릿입니다.

## <a name="syntax"></a>구문

## <a name="remarks"></a>주의

이 클래스는 `valarray<size_t>` 개체에서 선택할 요소의 시퀀스를 설명 하는 클래스 `valarray<Type>`의 개체 `xa`와 함께 **valarray \<Type** [array](../standard-library/valarray-class.md) 클래스 `va` 개체에 대 한 참조를 저장 하는 개체를 설명 합니다.

@No__t_1 형식의 식을 작성 하 여 `indirect_array<Type>` 개체만 생성 합니다. Indirect_array 클래스의 멤버 함수는 선택한 요소의 시퀀스에만 영향을 주는 점을 제외 하 고 `valarray<Type>`에 대해 정의 된 해당 함수 서명 처럼 동작 합니다.

이 시퀀스는 xa로 구성 됩니다 **.** 요소의 [크기를 조정](../standard-library/valarray-class.md#size) 합니다. 여기서 요소 `I` `va` 내에서 **xa**[`I`]가 됩니다.

## <a name="example"></a>예제:

```cpp
// indirect_array.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      va [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      va [ i ] =  -1;

   cout << "The initial operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   // Select 2nd, 4th & 6th elements
   // and assign a value of 10 to them
   valarray<size_t> indx ( 3 );
   indx [0] = 2;
   indx [1] = 4;
   indx [2] = 6;
   va[indx] = 10;

   cout << "The modified operand valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>Output

```cpp
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).
```

## <a name="requirements"></a>요구 사항

**헤더:** \<valarray>

**네임스페이스:** std

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
