---
title: 컴파일러 오류 C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: c23f17483925f25468214165fb459db577e576fc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209012"
---
# <a name="compiler-error-c2006"></a>컴파일러 오류 C2006

'directive' 파일 이름이 'token' 예상

같은 지시문 [#include](../../preprocessor/hash-include-directive-c-cpp.md) 하거나 [#import](../../preprocessor/hash-import-directive-cpp.md) 파일 이름이 필요 합니다. 이 오류를 해결 하려면 *토큰* 유효한 파일 이름이 됩니다. 또한 큰따옴표 또는 꺾쇠 괄호에 파일을 배치 합니다.

다음 샘플에서는 C2006 오류가 생성 됩니다.

```
// C2006.cpp
#include stdio.h   // C2006
```

해결 방법:

```
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```