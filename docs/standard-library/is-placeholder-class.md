---
title: is_placeholder 클래스
ms.date: 11/04/2016
f1_keywords:
- functional/std::is_placeholder
helpviewer_keywords:
- is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
ms.openlocfilehash: 9fa7d4aaade6244fe26f89f3a667598d39471a47
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245146"
---
# <a name="isplaceholder-class"></a>is_placeholder 클래스

형식이 자리 표시자인지 테스트합니다.

## <a name="syntax"></a>구문

구조체 is_placeholder {static const int 값;};

## <a name="remarks"></a>설명

`Ty` 형식이 자리 표시자가 아니면 상수 값 `value`는 0이고, 그렇지 않으면 해당 값은 바인딩된 함수 호출 인수의 위치입니다. N번째 자리 표시자 `_N`에 대해 `N` 값을 확인하는 데 사용됩니다.

## <a name="example"></a>예제

```cpp
// std__functional__is_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

using namespace std::placeholders;

template<class Expr>
void test_for_placeholder(const Expr&)
{
    std::cout << std::is_placeholder<Expr>::value << std::endl;
}

int main()
{
    test_for_placeholder(3.0);
    test_for_placeholder(_3);

    return (0);
}
```

```Output
0
3
```
