---
title: 컴파일러 경고 (수준 4) C4463
ms.date: 11/04/2016
f1_keywords:
- C4463
helpviewer_keywords:
- C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
ms.openlocfilehash: e125a532f87533958ec43ed5580665ad4108856b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400801"
---
# <a name="compiler-warning-level-4-c4463"></a>컴파일러 경고 (수준 4) C4463

> 오버플로. 할당 *값* 의 값만 포함할 수 있는 비트 필드에 *low_value* 에 *high_value*

할당 된 *값* 비트 필드를 보유할 수 있는 값의 범위를 벗어났습니다. 부호 있는 비트 필드 형식에 부호에 대 한 비트 우선 순서를 사용 하면 *n* 부호 있는 비트 필드는-2는 비트 필드 크기 범위<sup>n-1</sup> 2<sup>n-1</sup>-1, 부호 없는 동안 비트 필드 범위가 0에서 2로<sup>n</sup>-1입니다.

## <a name="example"></a>예제

형식의 비트 필드에 값 3 할당 하려고 했기 때문에이 예제에서는 생성 C4463 `int` 크기가 2는 범위가-2에서 1로 합니다.

이 문제를 해결 하려면 허용 되는 범위의 값으로 할당 된 값을 변경할 수 있습니다. 비트 필드는 0에서 3 사이에 부호 없는 값을 보유할 것을 하는 경우에 선언 형식을 변경할 수 있습니다 `unsigned`합니다. 필드에 범위-4-3 값을 보유할 것을 하는 경우 3 비트 필드 크기를 변경할 수 있습니다.

```cpp
// C4463_overflow.cpp
// compile with: cl /W4 /EHsc C4463_overflow.cpp
struct S {
    int x : 2; // int type treats high-order bit as sign
};

int main() {
    S s;
    s.x = 3; // warning C4463: overflow; assigning 3
    // to bit-field that can only hold values from -2 to 1
    // To fix, change assigned value to fit in range,
    // increase size of bitfield, and/or change base type
    // to unsigned.
}
```
