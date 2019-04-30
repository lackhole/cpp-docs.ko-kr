---
title: remove_cv 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_cv
helpviewer_keywords:
- remove_cv class
- remove_cv
ms.assetid: 8502602a-1c80-479c-84e0-33bd1d6496d6
ms.openlocfilehash: dcabf9b4687d473898dea98f1001647299a40b76
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368905"
---
# <a name="removecv-class"></a>remove_cv 클래스

형식에서 비 const/휘발성 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct remove_cv;

template <class T>
using remove_cv_t = typename remove_cv<T>::type;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
수정할 형식입니다.

## <a name="remarks"></a>설명

인스턴스의 `remove_cv<T>` 는 형식인 수정 된 `T1` 때 *T* 형식인 `const T1`를 `volatile T1`, 또는 `const volatile T1`고, 그렇지 않으면 *T*합니다.

## <a name="example"></a>예제

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_cv_t<const volatile int> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_cv_t<const volatile int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_cv_t<const volatile int> == int
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const 클래스](../standard-library/remove-const-class.md)<br/>
[remove_volatile 클래스](../standard-library/remove-volatile-class.md)<br/>
