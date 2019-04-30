---
title: add_pointer 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_pointer
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
ms.openlocfilehash: fda2bcbd3484b9244d69358aac3e9baf5d37a4ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411216"
---
# <a name="addpointer-class"></a>add_pointer 클래스

지정된 형식에서 포인터-형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct add_pointer;

template <class T>
using add_pointer_t = typename add_pointer<T>::type;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
수정할 형식입니다.

## <a name="remarks"></a>설명

멤버 **typedef** `type` 와 같은 형식 이름을 `remove_reference<T>::type*`입니다. 별칭 `add_pointer_t` 멤버에 액세스 하려면 바로 가기입니다 **typedef** `type`합니다.

참조에서 포인터를 만드는 것은 잘못이기 때문에 `add_pointer`가 포인터-형식을 만들기 전에 지정된 형식에서 참조(있는 경우)를 제거합니다. 결과적으로, 형식이 참조인지 걱정하지 않고도 `add_pointer`를 포함하여 형식을 사용할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 `add_pointer` 형식이 해당 형식의 포인터와 같은 경우를 보여 줍니다.

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_pointer_t<int> *p = (int **)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_pointer_t<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_pointer_t<int> == int *
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_pointer 클래스](../standard-library/remove-pointer-class.md)<br/>
