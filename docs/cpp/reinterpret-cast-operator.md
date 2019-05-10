---
title: reinterpret_cast 연산자
ms.date: 11/04/2016
f1_keywords:
- reinterpret_cast_cpp
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
ms.openlocfilehash: 421a1fdce6834f800cd33a55d75c9dc4f88ffc93
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403427"
---
# <a name="reinterpretcast-operator"></a>reinterpret_cast 연산자

포인터가 다른 포인터 형식으로 변환될 수 있도록 합니다. 또한 정수 계열 형식이 포인터 형식으로 변환될 수 있도록 하고 그 반대로도 변환될 수 있도록 합니다.

## <a name="syntax"></a>구문

```
reinterpret_cast < type-id > ( expression )
```

## <a name="remarks"></a>설명

오용 합니다 **reinterpret_cast** 연산자 수 쉽게 안전 하지 않을 수 있습니다. 원하는 변환이 본질적으로 낮은 수준이 아닌 한 다른 캐스트 연산자 중 하나를 사용해야 합니다.

**reinterpret_cast** 변환에 대 한와 같은 연산자를 사용할 수 있습니다 `char*` 하 `int*`, 또는 `One_class*` 에 `Unrelated_class*`, 본질적으로 안전 하지 않은 합니다.

결과 **reinterpret_cast** 원래 형식으로 다시 캐스팅 되 이외의 용도로 안전 하 게 사용할 수 없습니다. 다른 용도로 사용하는 경우에는 기껏해야 이식할 수 없는 결과가 생성됩니다.

합니다 **reinterpret_cast** 연산자 떨어져 캐스팅할 수 없습니다는 **const**를 **volatile**, 또는 **__unaligned** 특성입니다. 참조 [const_cast 연산자](../cpp/const-cast-operator.md) 이러한 특성을 제거 하는 방법은 합니다.

합니다 **reinterpret_cast** 연산자 대상 형식의 null 포인터 값으로 null 포인터 값을 변환 합니다.

유용 하 게 사용할 **reinterpret_cast** 해시 함수에서 값 방식으로 두 고유 인덱스에 매핑하는 값을 거의 끝을 동일한 인덱스 됩니다.

```cpp
#include <iostream>
using namespace std;

// Returns a hash code based on an address
unsigned short Hash( void *p ) {
   unsigned int val = reinterpret_cast<unsigned int>( p );
   return ( unsigned short )( val ^ (val >> 16));
}

using namespace std;
int main() {
   int a[20];
   for ( int i = 0; i < 20; i++ )
      cout << Hash( a + i ) << endl;
}

Output:
64641
64645
64889
64893
64881
64885
64873
64877
64865
64869
64857
64861
64849
64853
64841
64845
64833
64837
64825
64829
```

합니다 **reinterpret_cast** 포인터가 정수 계열 형식으로 처리 될 수 있습니다. 결과는 비트 이동되고 자신과 XOR 연산이 수행되어 고유한 인덱스(높은 확률로 고유함)를 생성합니다. 이 인덱스는 표준 C 스타일 캐스트를 통해 함수의 반환 형식으로 잘립니다.

## <a name="see-also"></a>참고자료

[캐스팅 연산자](../cpp/casting-operators.md)<br/>
[키워드(C++)](../cpp/keywords-cpp.md)