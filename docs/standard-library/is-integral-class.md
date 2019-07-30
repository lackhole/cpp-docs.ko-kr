---
title: is_integral 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_integral
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
ms.openlocfilehash: a367bb06f49dd2c9c64f0c257a3573add5645efe
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456245"
---
# <a name="isintegral-class"></a>is_integral 클래스

형식이 정수 계열인지 테스트합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>매개 변수

*Ty*\
형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 조건자의 인스턴스는 *Ty* 형식이 정수 계열 형식 중 하나 이거나 `cv-qualified` 정수 계열 형식 중 하나의 형식인 경우 true이 고 그렇지 않은 경우 false입니다.

정수 계열 형식은 **bool**, **char**, **unsigned char**, **signed char**, **wchar_t**, **short**, **unsigned short**, **int**, **unsigned int**, **long**, **unsigned long**중 하나입니다. 또한 제공 하는 컴파일러를 사용 하 여 정수 계열 형식은 **long long**, **unsigned long long**, **__int64**및 **unsigned __int64**중 하나가 될 수 있습니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__is_integral.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_integral<trivial> == " << std::boolalpha
        << std::is_integral<trivial>::value << std::endl;
    std::cout << "is_integral<int> == " << std::boolalpha
        << std::is_integral<int>::value << std::endl;
    std::cout << "is_integral<float> == " << std::boolalpha
        << std::is_integral<float>::value << std::endl;

    return (0);
    }
```

```Output
is_integral<trivial> == false
is_integral<int> == true
is_integral<float> == false
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)\
[is_enum 클래스](../standard-library/is-enum-class.md)\
[is_floating_point 클래스](../standard-library/is-floating-point-class.md)
