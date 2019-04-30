---
title: remove_extent 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_extent
helpviewer_keywords:
- remove_extent class
- remove_extent
ms.assetid: b9320862-3891-49fc-80bc-571eb2c035cf
ms.openlocfilehash: 1425de12158354c649ec355124f8c255255b29c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368879"
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

*T*<br/>
수정할 형식입니다.

## <a name="remarks"></a>설명

인스턴스의 `remove_extent<T>` 는 형식인 수정 된 `T1` 때 *T* 형식인 `T1[N]`고, 그렇지 않으면 *T*합니다.

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

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_all_extents 클래스](../standard-library/remove-all-extents-class.md)<br/>
