---
title: 컴파일러 오류 C2385
ms.date: 11/04/2016
f1_keywords:
- C2385
helpviewer_keywords:
- C2385
ms.assetid: 6d3dd1f2-e56d-49d7-865c-6a9acdb17417
ms.openlocfilehash: 1247e4da05d65677f602a82591efd3e0c0c374e0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745257"
---
# <a name="compiler-error-c2385"></a>컴파일러 오류 C2385

' member '의 모호한 액세스

멤버는 둘 이상의 개체에서 파생 될 수 있습니다 (둘 이상의 개체에서 상속 됨).  이 오류를 해결 하려면

- 캐스트를 제공 하 여 멤버를 명확 하 게 만듭니다.

- 기본 클래스에서 모호한 멤버의 이름을 바꿉니다.

## <a name="example"></a>예제

다음 샘플에서는 C2385를 생성 합니다.

```cpp
// C2385.cpp
// C2385 expected
#include <stdio.h>

struct A
{
    void x(int i)
    {
        printf_s("\nIn A::x");
    }
};

struct B
{
    void x(char c)
    {
        printf_s("\nIn B::x");
    }
};

// Delete the following line to resolve.
struct C : A, B {}

// Uncomment the following 4 lines to resolve.
// struct C : A, B
// {
//     using B::x;
//     using A::x;
// };

int main()
{
    C aC;
    aC.x(100);
    aC.x('c');
}

struct C : A, B
{
    using B::x;
    using A::x;
};
```
