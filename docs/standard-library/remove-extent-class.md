---
title: remove_extent 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_extent
helpviewer_keywords:
- remove_extent class
- remove_extent
ms.assetid: b9320862-3891-49fc-80bc-571eb2c035cf
ms.openlocfilehash: 73af53d2b93d794e2479a33721bfeae71e531794
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451284"
---
# <a name="removeextent-class"></a>remove_extent 클래스

배열 형식에서 요소 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct remove_extent;

template <class T>
using remove_extent_t = typename remove_extent<T>::type;
```

### <a name="parameters"></a>매개 변수

*트*\
수정할 형식입니다.

## <a name="remarks"></a>설명

의 `remove_extent<T>` 인스턴스는 *t* 가 형식이 `T1[N]`면이 고, `T1` 그렇지 않으면 인 수정 된 형식을 보유 합니다 .

## <a name="example"></a>예제

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "remove_extent_t<int> == "
        << typeid(std::remove_extent_t<int>).name()
        << std::endl;T
    std::cout << "remove_extent_t<int[5]> == "
        << typeid(std::remove_extent_t<int[5]>).name()
        << std::endl;T
    std::cout << "remove_extent_t<int[5][10]> == "
        << typeid(std::remove_extent_t<int[5][10]>).name()
        << std::endl;
    return (0);
    }
```

```Output
remove_extent_t<int> == int
remove_extent_t<int[5]> == int
remove_extent_t<int[5][10]> == int [10]
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)\
[remove_all_extents 클래스](../standard-library/remove-all-extents-class.md)
