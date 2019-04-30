---
title: __func__
ms.date: 10/19/2017
f1_keywords:
- __func__
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
ms.openlocfilehash: eecd3efea6239c92a8bc81c0ed13a9563e5b87d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154297"
---
# <a name="func"></a>__func__

**(C + + 11)** 미리 정의된 식별자 &#95;&#95;func&#95;&#95;는 바깥쪽 함수의 정규화되지 않고/표시되지 않은 이름을 포함하는 문자열로 암시적으로 정의됩니다. &#95;&#95;func&#95;&#95;는 C++ 표준에서 위임되며 및 Microsoft 확장이 아닙니다.

## <a name="syntax"></a>구문

```cpp
__func__
```

## <a name="return-value"></a>반환 값

함수 이름을 포함하는 문자의 null로 끝나는 const char 배열을 반환합니다.

## <a name="example"></a>예제

```cpp
#include <string>
#include <iostream>

namespace Test
{
    struct Foo
    {
        static void DoSomething(int i, std::string s)
        {
           std::cout << __func__ << std::endl; // Output: DoSomething
        }
    };
}

int main()
{
    Test::Foo::DoSomething(42, "Hello");

    return 0;
}
```

## <a name="requirements"></a>요구 사항

C++11