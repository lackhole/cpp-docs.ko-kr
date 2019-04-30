---
title: 컴파일러 오류 C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: e966295b5ab63350828ddb73d6791a9e30bb5c59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404106"
---
# <a name="compiler-error-c3615"></a>컴파일러 오류 C3615

> constexpr 함수 '*함수*' 상수 식이 될 수 없습니다

함수 *함수* 으로 평가할 수 없습니다. `constexpr` 컴파일 타임에 있습니다. 되도록 `constexpr`에서 함수를 호출할 수 있습니다. 다른 `constexpr` 함수입니다.

## <a name="example"></a>예제

조건부 계산 연산의 왼쪽 피연산자에서 유효 하지 않을 때 visual Studio 2017 오류를 올바르게 생성을 `constexpr` 컨텍스트. 다음 코드는 Visual Studio 2017 아니라 Visual Studio 2015에서 컴파일합니다.

```cpp
// C3615.cpp
// Compile with: /c

template<int N>
struct myarray
{
    int size() const { return N; }
};

constexpr bool f(const myarray<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615 starting in Visual Studio 2017
}
```

선언 하거나이 문제를 해결 하려면 합니다 `array::size()` 역할도 `constexpr` 또는 제거 합니다 `constexpr` 한정자 `f`합니다.