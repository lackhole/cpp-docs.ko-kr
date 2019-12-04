---
title: 컴파일러 오류 C2193
ms.date: 11/04/2016
f1_keywords:
- C2193
helpviewer_keywords:
- C2193
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
ms.openlocfilehash: 25ebfc73fb46eca3a27875075af2d4ed46ed2fef
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758556"
---
# <a name="compiler-error-c2193"></a>컴파일러 오류 C2193

' identifier ': 세그먼트에 이미 있습니다.

`alloc_text` 및 `code_seg` pragma를 사용 하 여 함수를 두 개의 서로 다른 세그먼트에 배치 했습니다.

다음 샘플에서는 C2193를 생성 합니다.

```cpp
// C2193.cpp
// compile with: /c
extern "C" void MYFUNCTION();
#pragma alloc_text(MYCODE, MYFUNCTION)
#pragma code_seg("MYCODE2")
extern "C" void MYFUNCTION() {}   // C2193
extern "C" void MYFUNCTION2() {}
```
