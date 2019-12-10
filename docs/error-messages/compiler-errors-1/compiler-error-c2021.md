---
title: 컴파일러 오류 C2021
ms.date: 11/04/2016
f1_keywords:
- C2021
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
ms.openlocfilehash: 24463abcf123fda285356c86e3394d7274f2f6c8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751042"
---
# <a name="compiler-error-c2021"></a>컴파일러 오류 C2021

'character'가 아니라 지수 값이 필요합니다.

부동 소수점 상수의 지 수로 사용 되는 문자가 유효한 숫자가 아닙니다. 범위에 있는 지 수를 사용 해야 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2021를 생성 합니다.

```cpp
// C2021.cpp
float test1=1.175494351E;   // C2021
```

## <a name="example"></a>예제

가능한 해결 방법:

```cpp
// C2021b.cpp
// compile with: /c
float test2=1.175494351E8;
```
