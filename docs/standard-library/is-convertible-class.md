---
title: is_convertible 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_convertible
helpviewer_keywords:
- is_convertible class
- is_convertible
ms.assetid: 75614008-1894-42ea-bd57-974399628536
ms.openlocfilehash: cdc3276f229fb9c1ac059a9eeb29e77655b4fc69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337377"
---
# <a name="isconvertible-class"></a>is_convertible 클래스

한 가지 형식을 다른 형식으로 변환할 수 있는지 여부를 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class From, class To>
struct is_convertible;
```

### <a name="parameters"></a>매개 변수

*From*<br/>
변환할 원본 형식입니다.

*Ty*<br/>
변환할 대상 형식입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 식 `To to = from;`이 올바른 형식인 경우 true입니다(여기서 `from`은 `From` 형식의 개체임).

## <a name="example"></a>예제

```cpp
// std__type_traits__is_convertible.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha
        << std::is_convertible<trivial, int>::value << std::endl;
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha
        << std::is_convertible<trivial, trivial>::value << std::endl;
    std::cout << "is_convertible<char, int> == " << std::boolalpha
        << std::is_convertible<char, int>::value << std::endl;

    return (0);
    }
```

```Output
is_convertible<trivial, int> == false
is_convertible<trivial, trivial> == true
is_convertible<char, int> == true
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_base_of 클래스](../standard-library/is-base-of-class.md)<br/>
