---
title: add_const 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_const
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
ms.openlocfilehash: dc457fd4efba538e96200f7f42f84a73fc1b5228
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411242"
---
# <a name="addconst-class"></a>add_const 클래스

형식에서 const 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct add_const;
```

### <a name="parameters"></a>매개 변수

*Ty*<br/>
수정할 형식입니다.

## <a name="remarks"></a>설명

형식 수정자의 인스턴스는 수정 된 형식인 됩니다 *Ty* 하는 경우 *Ty* 라인인 대 한 참조, 함수 또는 const 한정 된 형식 `const Ty`합니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__add_const.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
{
    std::add_const<int>::type *p = (const int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_const<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_const<int> == int
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const 클래스](../standard-library/remove-const-class.md)<br/>
