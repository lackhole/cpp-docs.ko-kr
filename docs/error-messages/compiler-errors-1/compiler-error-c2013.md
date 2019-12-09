---
title: 컴파일러 오류 C2013
ms.date: 11/04/2016
f1_keywords:
- C2013
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
ms.openlocfilehash: 3dd8c315351ccf38989fc113e7ee31b25e38a07f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757412"
---
# <a name="compiler-error-c2013"></a>컴파일러 오류 C2013

'>'가 없습니다.

`#include` 지시문에 닫는 꺾쇠 괄호가 없습니다. 오류를 해결하려면 닫는 대괄호를 추가합니다.

다음 샘플에서는 C2013을 생성합니다.

```cpp
// C2013.cpp
#include <stdio.h    // C2013
```

가능한 해결 방법:

```cpp
// C2013b.cpp
// compile with: /c
#include <stdio.h>
```
