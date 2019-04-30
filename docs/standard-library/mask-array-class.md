---
title: mask_array 클래스
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: 108c942bef33e44b515d46e953c9d99274e3ce8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412984"
---
# <a name="maskarray-class"></a>mask_array 클래스

하위 집합 배열 간의 작업을 제공하여 부울 식으로 지정된 부모 valarray의 하위 집합인 개체를 지원하는 내부 보조 템플릿 클래스입니다.

## <a name="syntax"></a>구문

## <a name="remarks"></a>설명

개체에 대 한 참조를 저장 하는 개체를 설명 하는 클래스 `va` 클래스의 [valarray](../standard-library/valarray-class.md)**\<유형 >**, 개체와 함께 `ba` 클래스의 [ valarray\<bool >](../standard-library/valarray-bool-class.md)에서 선택할 요소의 시퀀스를 설명 하는 `valarray<Type>` 개체입니다.

생성 하는 `mask_array<Type>` 개체 형식의 식을 작성 해야만 [va&#91;ba&#93;](../standard-library/valarray-class.md#op_at)합니다. Mask_array 클래스의 멤버 함수에 대해 정의 된 해당 함수 시그니처 처럼 동작 `valarray<Type>`에 선택한 요소의 시퀀스에만 영향을 제외 하 고, 합니다.

시퀀스의 최대 구성 `ba.size` 요소입니다. 요소 *J* 는 **ba**[ *J*]가 true인 경우에만 포함됩니다. 따라서 가지에 있는 true 요소 수 만큼의 요소가 시퀀스에 `ba`입니다. 하는 경우 `I` 에서 가장 낮은 true 요소의 인덱스가 `ba`, 한 다음 **va**[ `I`]는 선택한 시퀀스의 요소 0입니다.

## <a name="example"></a>예제

```cpp
// mask_array.cpp
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

   // Use masked subsets to assign a value of 10
   // to all elements grrater than 3 in value
   va [va > 3 ] = 10;
   cout << "The modified operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>출력

```Output
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).
```

## <a name="requirements"></a>요구 사항

**헤더:** \<valarray>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
