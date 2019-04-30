---
title: is_reference 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_reference
helpviewer_keywords:
- is_reference class
- is_reference
ms.assetid: 3d9e631f-3092-430c-843e-e914ab58c257
ms.openlocfilehash: 793a84f03dba762ff686627004ffe3830a5d98d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413569"
---
# <a name="isreference-class"></a>is_reference 클래스

형식이 참조인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_reference;
```

### <a name="parameters"></a>매개 변수

*Ty*<br/>
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *Ty* 함수, 그렇지 않으면 false 또는 개체에 대 한 참조입니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__is_reference.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_reference<trivial> == " << std::boolalpha
        << std::is_reference<trivial>::value << std::endl;
    std::cout << "is_reference<trivial&> == " << std::boolalpha
        << std::is_reference<trivial&>::value << std::endl;
    std::cout << "is_reference<int()> == " << std::boolalpha
        << std::is_reference<int()>::value << std::endl;
    std::cout << "is_reference<int(&)()> == " << std::boolalpha
        << std::is_reference<int(&)()>::value << std::endl;

    return (0);
    }
```

```Output
is_reference<trivial> == false
is_reference<trivial&> == true
is_reference<int()> == false
is_reference<int(&)()> == true
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_pointer 클래스](../standard-library/is-pointer-class.md)<br/>
