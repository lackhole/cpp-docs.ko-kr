---
title: add_volatile 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_volatile
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
ms.openlocfilehash: ff48b1848e2d7631d789621a5ef845d04d8e8821
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411138"
---
# <a name="addvolatile-class"></a>add_volatile 클래스

만듭니다는 **volatile** 지정된 된 형식에서 형식입니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
수정할 형식입니다.

## <a name="remarks"></a>설명

인스턴스의 `add_volatile<T>` 멤버가 **typedef** `type` 즉 *T* 경우 *T* 대 한 참조, 함수 또는 휘발성 한정 형식인,이 고, 그렇지 **volatile** *T*합니다. 별칭 `add_volatile_t` 멤버에 액세스 하려면 바로 가기입니다 **typedef** `type`합니다.

## <a name="example"></a>예제

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_volatile_t<int> *p = (volatile int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_volatile<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_volatile<int> == int
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_volatile 클래스](../standard-library/remove-volatile-class.md)<br/>
