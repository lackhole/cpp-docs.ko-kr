---
title: 컴파일러 오류 C2194
ms.date: 11/04/2016
f1_keywords:
- C2194
helpviewer_keywords:
- C2194
ms.assetid: df6e631c-0062-4844-9088-4cc7a0ff879f
ms.openlocfilehash: 7d7c1324ea295752a09cf9c87ef37164ab6a06db
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758543"
---
# <a name="compiler-error-c2194"></a>컴파일러 오류 C2194

' identifier ': 텍스트 세그먼트입니다.

`data_seg` pragma는 `code_seg`와 함께 사용 된 세그먼트 이름을 사용 합니다.

다음 샘플에서는 C2194를 생성 합니다.

```cpp
// C2194.cpp
// compile with: /c
#pragma code_seg("MYCODE")
#pragma data_seg("MYCODE")   // C2194
#pragma data_seg("MYCODE2")   // OK
```
