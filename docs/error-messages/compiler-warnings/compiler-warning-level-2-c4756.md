---
title: 컴파일러 경고 (수준 2) C4756
ms.date: 11/04/2016
f1_keywords:
- C4756
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
ms.openlocfilehash: 640eb77273fdbda0b12bbf2c2a326e970951cbda
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051999"
---
# <a name="compiler-warning-level-2-c4756"></a>컴파일러 경고 (수준 2) C4756

상수 산술 연산에서 오버플로가 발생 했습니다.

컴파일하는 동안 상수 산술 연산을 수행 하는 동안 컴파일러에서 예외가 발생 했습니다.

다음 샘플에서는 C4756를 생성 합니다.

```cpp
// C4756.cpp
// compile with: /W2 /Od
int main()
{
   float f = 1e100+1e100;   // C4756
}
```