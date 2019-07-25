---
title: is_compound 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_compound
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
ms.openlocfilehash: 003ddcf77c30bc2dc5491218dfbf00731517bdeb
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452899"
---
# <a name="iscompound-class"></a>is_compound 클래스

지정된 형식이 기본 형식이 아닌지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_compound;
```

### <a name="parameters"></a>매개 변수

*Ty*\
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 *Ty* 형식이 기본 형식이 면 **false** 가 됩니다. 즉, [is_fundamental](../standard-library/is-fundamental-class.md)\<Ty > **true**이면 true이 고, 그렇지 않으면 **true**입니다. 따라서이 조건자는 *Ty* 가 배열 형식, 함수 형식, **void** 또는 개체 또는 함수에 대 한 포인터, 참조, 클래스, 공용 구조체, 열거형 또는 비정적 클래스 멤버에 대 한 포인터 또는의 *cv 한정* 형식인 경우 **true** 입니다. 그 중 하나입니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__is_compound.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_compound<trivial> == " << std::boolalpha
        << std::is_compound<trivial>::value << std::endl;
    std::cout << "is_compound<int[]> == " << std::boolalpha
        << std::is_compound<int[]>::value << std::endl;
    std::cout << "is_compound<int()> == " << std::boolalpha
        << std::is_compound<int()>::value << std::endl;
    std::cout << "is_compound<int&> == " << std::boolalpha
        << std::is_compound<int&>::value << std::endl;
    std::cout << "is_compound<void *> == " << std::boolalpha
        << std::is_compound<void *>::value << std::endl;
    std::cout << "is_compound<int> == " << std::boolalpha
        << std::is_compound<int>::value << std::endl;

    return (0);
    }
```

```Output
is_compound<trivial> == true
is_compound<int[]> == true
is_compound<int()> == true
is_compound<int&> == true
is_compound<void *> == true
is_compound<int> == false
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)\
[is_class 클래스](../standard-library/is-class-class.md)
