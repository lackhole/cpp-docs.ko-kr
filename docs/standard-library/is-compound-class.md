---
title: is_compound 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_compound
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
ms.openlocfilehash: f270a1a58bb8023d91d84b0d1ca3395d36298c95
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337104"
---
# <a name="iscompound-class"></a>is_compound 클래스

지정된 형식이 기본 형식이 아닌지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_compound;
```

### <a name="parameters"></a>매개 변수

*Ty*<br/>
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 **false** 하는 경우 형식의 *Ty* 은 기본 형식 (즉, [is_fundamental](../standard-library/is-fundamental-class.md)\<Ty > 보유  **true**); 그 외 **true**합니다. 조건자는 따라서 **true** 하는 경우 *Ty* 가 배열 형식, 함수 형식에 대 한 포인터 **void** , 개체 또는 함수, 참조, 클래스, 집합체, 열거형 또는 비정적 클래스 멤버에 대 한 포인터 또는 *cv 한정* 그 중 하나는 형식입니다.

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

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_class 클래스](../standard-library/is-class-class.md)<br/>
