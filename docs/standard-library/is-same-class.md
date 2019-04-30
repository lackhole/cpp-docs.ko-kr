---
title: is_same 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_same
helpviewer_keywords:
- is_same class
- is_same
ms.assetid: d9df6c1d-c270-4ec2-802a-af275648dd1d
ms.openlocfilehash: 5bb306ec29da225293affd0207f67271f59ec599
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413556"
---
# <a name="issame-class"></a>is_same 클래스

두 형식이 동일한지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty1, class Ty2>
struct is_same;
```

### <a name="parameters"></a>매개 변수

*Ty1*<br/>
쿼리할 첫 번째 형식입니다.

*Ty2*<br/>
쿼리할 두 번째 형식입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스 형태인 경우 true 형식을 *Ty1* 하 고 *Ty2* 동일한 형식이, 그렇지 않은 경우 false입니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__is_same.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct base
    {
    int val;
    };

struct derived
    : public base
    {
    };

int main()
    {
    std::cout << "is_same<base, base> == " << std::boolalpha
        << std::is_same<base, base>::value << std::endl;
    std::cout << "is_same<base, derived> == " << std::boolalpha
        << std::is_same<base, derived>::value << std::endl;
    std::cout << "is_same<derived, base> == " << std::boolalpha
        << std::is_same<derived, base>::value << std::endl;
    std::cout << "is_same<int, int> == " << std::boolalpha
        << std::is_same<int, int>::value << std::endl;
    std::cout << "is_same<int, const int> == " << std::boolalpha
        << std::is_same<int, const int>::value << std::endl;

    return (0);
    }
```

```Output
is_same<base, base> == true
is_same<base, derived> == false
is_same<derived, base> == false
is_same<int, int> == true
is_same<int, const int> == false
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_convertible 클래스](../standard-library/is-convertible-class.md)<br/>
[is_base_of 클래스](../standard-library/is-base-of-class.md)<br/>
