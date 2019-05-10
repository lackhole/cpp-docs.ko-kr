---
title: add_cv 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_cv
helpviewer_keywords:
- add_cv class
- add_cv
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
ms.openlocfilehash: 37001815710b197ec77ed0d45a16ea971ad1edce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411229"
---
# <a name="addcv-class"></a>add_cv 클래스

사용 하면 **const volatile** 형식에서 형식입니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct add_cv;

template <class T>
using add_cv_t = typename add_cv<T>::type;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
수정할 형식입니다.

## <a name="remarks"></a>설명

수정 된 형식 인스턴스의 `add_cv<T>` 에 `type` 멤버 **typedef** 같음 *T* 둘 다로 수정 [add_volatile](../standard-library/add-volatile-class.md) 및 [ add_const](../standard-library/add-const-class.md)되지 않은 경우 *T* 이미 cv 한정자가, 참조 또는 함수입니다.

`add_cv_t<T>` 도우미 형식은 `add_cv<T>` 멤버 typedef `type`에 액세스하기 위한 바로 가기입니다.

## <a name="example"></a>예제

```cpp
// add_cv.cpp
// compile by using: cl /EHsc /W4 add_cv.cpp
#include <type_traits>
#include <iostream>

struct S {
    void f() {
        std::cout << "invoked non-cv-qualified S.f()" << std::endl;
    }
    void f() const {
        std::cout << "invoked const S.f()" << std::endl;
    }
    void f() volatile {
        std::cout << "invoked volatile S.f()" << std::endl;
    }
    void f() const volatile {
        std::cout << "invoked const volatile S.f()" << std::endl;
    }
};

template <class T>
void invoke() {
    T t;
    ((T *)&t)->f();
}

int main()
{
    invoke<S>();
    invoke<std::add_const<S>::type>();
    invoke<std::add_volatile<S>::type>();
    invoke<std::add_cv<S>::type>();
}
```

```Output
invoked non-cv-qualified S.f()
invoked const S.f()
invoked volatile S.f()
invoked const volatile S.f()
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const 클래스](../standard-library/remove-const-class.md)<br/>
[remove_volatile 클래스](../standard-library/remove-volatile-class.md)<br/>
