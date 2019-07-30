---
title: bad_weak_ptr 클래스
ms.date: 11/04/2016
f1_keywords:
- memory/std::bad_weak_ptr
helpviewer_keywords:
- bad_weak_ptr
- bad_weak_ptr class
ms.assetid: a09336d5-7237-4480-ab6b-3787e0e6025e
ms.openlocfilehash: e1d536eed6727a5d1e828d358aa6b64521d748b8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454264"
---
# <a name="badweakptr-class"></a>bad_weak_ptr 클래스

불량 weak_ptr 예외를 보고합니다.

## <a name="syntax"></a>구문

```cpp
class bad_weak_ptr : public std::exception
{
    bad_weak_ptr();
    const char *what() throw();
};
```

## <a name="remarks"></a>설명

이 클래스는 [weak_ptr 클래스](../standard-library/weak-ptr-class.md) 형식의 인수를 사용하는 [shared_ptr 클래스](../standard-library/shared-ptr-class.md) 생성자에서 throw될 수 있는 예외를 설명합니다. 멤버 함수 `what`에서 `"bad_weak_ptr"`을 반환합니다.

## <a name="example"></a>예제

```cpp
// std__memory__bad_weak_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int);
        wp = sp;
    }

    try
    {
        std::shared_ptr<int> sp1(wp); // weak_ptr has expired
    }
    catch (const std::bad_weak_ptr&)
    {
        std::cout << "bad weak pointer" << std::endl;
    }
    catch (...)
    {
        std::cout << "unknown exception" << std::endl;
    }

    return (0);
}
```

```Output
bad weak pointer
```

## <a name="see-also"></a>참고자료

[weak_ptr 클래스](../standard-library/weak-ptr-class.md)
