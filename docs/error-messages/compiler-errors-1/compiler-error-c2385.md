---
title: 컴파일러 오류 C2385
ms.date: 11/04/2016
f1_keywords:
- C2385
helpviewer_keywords:
- C2385
ms.assetid: 6d3dd1f2-e56d-49d7-865c-6a9acdb17417
ms.openlocfilehash: bffb4c1088c41832e69b0c6f161b47f6f9f08d06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393703"
---
# <a name="compiler-error-c2385"></a>컴파일러 오류 C2385

'member' 액세스가 모호 합니다

멤버 (둘 이상의 개체에서 상속 된) 둘 이상의 개체에서 파생 될 수 있습니다.  이 오류를 해결 하려면

- 캐스트를 통해 모호 하지 않은 멤버를 확인 합니다.

- 모호한 기본 클래스 멤버를 이름을 바꿉니다.

## <a name="example"></a>예제

다음 샘플 C2385를 생성합니다.

```
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