---
title: is_pointer 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_pointer
helpviewer_keywords:
- is_pointer class
- is_pointer
ms.assetid: 44e0a403-7241-4e0a-8922-32877bcb9a4c
ms.openlocfilehash: d8b15f9eb5ef817f5576387b0d8119b86aa86af7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455741"
---
# <a name="ispointer-class"></a>is_pointer 클래스

형식이 포인터인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_pointer;
```

### <a name="parameters"></a>매개 변수

*Ty*\
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 *Ty* 형식이 **void**에 대 한 포인터, 개체에 대 한 포인터 또는 함수에 대 한 포인터 또는 `cv-qualified` 그 중 하나의 폼 인 경우 true이 고 그렇지 않은 경우 false입니다. Ty가 `is_pointer` 멤버에 대  한 포인터 또는 멤버 함수에 대 한 포인터인 경우는 false입니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__is_pointer.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_pointer<trivial> == " << std::boolalpha
        << std::is_pointer<trivial>::value << std::endl;
    std::cout << "is_pointer<int trivial::*> == " << std::boolalpha
        << std::is_pointer<int trivial::*>::value << std::endl;
    std::cout << "is_pointer<trivial *> == " << std::boolalpha
        << std::is_pointer<trivial *>::value << std::endl;
    std::cout << "is_pointer<int> == " << std::boolalpha
        << std::is_pointer<int>::value << std::endl;
    std::cout << "is_pointer<int *> == " << std::boolalpha
        << std::is_pointer<int *>::value << std::endl;

    return (0);
    }
```

```Output
is_pointer<trivial> == false
is_pointer<int trivial::*> == false
is_pointer<trivial *> == true
is_pointer<int> == false
is_pointer<int *> == true
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)\
[is_member_pointer 클래스](../standard-library/is-member-pointer-class.md)\
[is_reference 클래스](../standard-library/is-reference-class.md)
