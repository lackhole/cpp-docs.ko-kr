---
title: remove_volatile 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_volatile
helpviewer_keywords:
- remove_volatile class
- remove_volatile
ms.assetid: 8b87e2c2-a581-4eb3-8691-c5603910d61d
ms.openlocfilehash: 19514d1839fa6e0afcecb690dcb12657a85f3c2e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451259"
---
# <a name="removevolatile-class"></a>remove_volatile 클래스

형식에서 비휘발성 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct remove_volatile;

template <class T>
using remove_volatile_t = typename remove_volatile<T>::type;
```

### <a name="parameters"></a>매개 변수

*트*\
수정할 형식입니다.

## <a name="remarks"></a>설명

의 `remove_volatile<T>` 인스턴스는 *t* 가 형식이 `volatile T1`면이 고, `T1` 그렇지 않으면 인 수정 된 형식을 보유 합니다 .

## <a name="example"></a>예제

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_volatile_t<volatile int> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << " remove_volatile_t<volatile int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_volatile_t<volatile int> == int
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)\
[add_volatile 클래스](../standard-library/add-volatile-class.md)
