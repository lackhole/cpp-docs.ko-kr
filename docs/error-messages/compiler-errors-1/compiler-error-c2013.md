---
title: 컴파일러 오류 C2013
ms.date: 11/04/2016
f1_keywords:
- C2013
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
ms.openlocfilehash: b279202b8b32197a99d230040207aa50bc100495
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351133"
---
# <a name="compiler-error-c2013"></a>컴파일러 오류 C2013

'>'가 없습니다.

`#include` 지시문에 닫는 꺾쇠 괄호가 없습니다. 오류를 해결하려면 닫는 대괄호를 추가합니다.

다음 샘플에서는 C2013을 생성합니다.

```
// C2013.cpp
#include <stdio.h    // C2013
```

해결 방법:

```
// C2013b.cpp
// compile with: /c
#include <stdio.h>
```