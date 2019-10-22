---
title: aligned_union 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::aligned_union
helpviewer_keywords:
- aligned_union
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
ms.openlocfilehash: ae03802549f7791e51dccf1ea98a7b18929a4a4b
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72690103"
---
# <a name="aligned_union-class"></a>aligned_union 클래스

공용 구조체 형식 및 필요한 크기를 저장할 수 있도록 적절하게 맞춰지고 충분히 큰 POD 형식을 제공합니다.

## <a name="syntax"></a>구문

```cpp
template <std::size_t Len, class... Types>
struct aligned_union;

template <std::size_t Len, class... Types>
using aligned_union_t = typename aligned_union<Len, Types...>::type;
```

### <a name="parameters"></a>매개 변수

*Len* \
공용 구조체에서 가장 큰 형식의 맞춤 값입니다.

*형식*\
기본 공용 구조체의 고유 형식입니다.

## <a name="remarks"></a>주의

클래스 템플릿을 사용 하 여 초기화 되지 않은 저장소에 공용 구조체를 저장 하는 데 필요한 맞춤 및 크기를 가져옵니다. 멤버 typedef `type` *형식*에 나열 된 모든 형식의 저장소에 적합 한 POD 형식을 이름으로 합니다. 최소 크기는 *Len*입니다. 형식 `std::size_t`의 정적 멤버 `alignment_value`에는 *형식*에 나열 된 모든 형식에 필요한 가장 엄격한 맞춤이 포함 되어 있습니다.

## <a name="example"></a>예제

다음 예제에서는 `aligned_union`을 사용하여 공용 구조체 배치를 위한 맞춤화된 스택 버퍼를 할당하는 방법을 보여줍니다.

```cpp
// std__type_traits__aligned_union.cpp
#include <iostream>
#include <type_traits>

union U_type
{
    int i;
    float f;
    double d;
    U_type(float e) : f(e) {}
};

typedef std::aligned_union<16, int, float, double>::type aligned_U_type;

int main()
{
    // allocate memory for a U_type aligned on a 16-byte boundary
    aligned_U_type au;
    // do placement new in the aligned memory on the stack
    U_type* u = new (&au) U_type(1.0f);
    if (nullptr != u)
    {
        std::cout << "value of u->i is " << u->i << std::endl;
        // must clean up placement objects manually!
        u->~U_type();
    }
}
```

```Output
value of u->i is 1065353216
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참조

[<type_traits>](../standard-library/type-traits.md)\
[alignment_of 클래스](../standard-library/alignment-of-class.md)
