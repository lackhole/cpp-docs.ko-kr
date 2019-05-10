---
title: is_object 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_object
helpviewer_keywords:
- is_object class
- is_object
ms.assetid: b452ceea-5676-488f-925b-ab881126c387
ms.openlocfilehash: 89c554bda1c82fbedda5b027dbb70b12c2c7cec4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413657"
---
# <a name="isobject-class"></a>is_object 클래스

형식이 개체 형식인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_object;
```

### <a name="parameters"></a>매개 변수

*Ty*<br/>
형식이 쿼리입니다.

## <a name="remarks"></a>설명

아니면 false 보유 하는 형식 조건자의 인스턴스 유형을 *Ty* 참조 형식, 함수 형식 이거나 void 또는 `cv-qualified` 그 중 하나의 형식을 그렇지 않으면 true입니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__is_object.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct functional
    {
    int f();
    };

int main()
    {
    std::cout << "is_object<trivial> == " << std::boolalpha
        << std::is_object<trivial>::value << std::endl;
    std::cout << "is_object<functional> == " << std::boolalpha
        << std::is_object<functional>::value << std::endl;
    std::cout << "is_object<trivial&> == " << std::boolalpha
        << std::is_object<trivial&>::value << std::endl;
    std::cout << "is_object<float()> == " << std::boolalpha
        << std::is_object<float()>::value << std::endl;
    std::cout << "is_object<void> == " << std::boolalpha
        << std::is_object<void>::value << std::endl;

    return (0);
    }
```

```Output
is_object<trivial> == true
is_object<functional> == true
is_object<trivial&> == false
is_object<float()> == false
is_object<void> == false
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_function 클래스](../standard-library/is-function-class.md)<br/>
