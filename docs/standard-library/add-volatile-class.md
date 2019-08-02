---
title: add_volatile 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_volatile
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
ms.openlocfilehash: becea4ff52342a79d0b87ffe0022e2cf84c47949
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456527"
---
# <a name="addvolatile-class"></a>add_volatile 클래스

지정 된 형식에서 **휘발성** 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>매개 변수

*트*\
수정할 형식입니다.

## <a name="remarks"></a>설명

`add_volatile<T>` 의 인스턴스에는 *t* 가 참조, 함수 또는 휘발성의 정규화 된 형식이 고 그렇지 *않은 경우* **volatile** *t*인 멤버 **typedef** `type` 가 있습니다. 별칭 `add_volatile_t` 은 멤버 **typedef** `type`에 액세스 하기 위한 바로 가기입니다.

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

[<type_traits>](../standard-library/type-traits.md)\
[remove_volatile 클래스](../standard-library/remove-volatile-class.md)
