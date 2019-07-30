---
title: is_empty 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_empty
helpviewer_keywords:
- is_empty class
- is_empty
ms.assetid: 44a6fc92-7e55-4fbe-9a24-2a0ce2dccba0
ms.openlocfilehash: 6300107ecf9c4ea1e237a60bf18f26b6416f7fba
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452706"
---
# <a name="isempty-class"></a>is_empty 클래스

형식이 빈 클래스인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_empty;
```

### <a name="parameters"></a>매개 변수

*Ty*\
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 *Ty* 형식이 빈 클래스인 경우 true이 고 그렇지 않은 경우 false입니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__is_empty.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct empty
    {
    };

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_empty<trivial> == " << std::boolalpha
        << std::is_empty<trivial>::value << std::endl;
    std::cout << "is_empty<empty> == " << std::boolalpha
        << std::is_empty<empty>::value << std::endl;
    std::cout << "is_empty<int> == " << std::boolalpha
        << std::is_empty<int>::value << std::endl;

    return (0);
    }
```

```Output
is_empty<trivial> == false
is_empty<empty> == true
is_empty<int> == false
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)
