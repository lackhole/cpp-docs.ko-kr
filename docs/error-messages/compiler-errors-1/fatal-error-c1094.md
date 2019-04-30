---
title: 심각한 오류 C1094
ms.date: 11/04/2016
f1_keywords:
- C1094
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
ms.openlocfilehash: 23891a783a018f6d84ea820af98992f61632984c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366500"
---
# <a name="fatal-error-c1094"></a>심각한 오류 C1094

'-Zmval1': 명령줄 옵션이 미리 컴파일된 헤더를 작성 하는 데 사용 되는 값과 일치 하지 않습니다 ('-Zmval2')

에 전달 되는 값 [/Yc](../../build/reference/yc-create-precompiled-header-file.md) 에 전달 되는 동일한 값 이어야 [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (**/Zm** 모든 컴파일에서 사용 하거나 만들 미리 컴파일된 동일한는 동일한 값 이어야 합니다 헤더 파일)입니다.

다음 샘플에서는 C1094를 생성합니다.

```
// C1094.h
int func1();
```

그리고

```
// C1094.cpp
// compile with: /Yc"C1094.h" /Zm200
int u;
int main() {
   int sd = 32;
}
#include "C1094.h"
```

그리고

```
// C1094b.cpp
// compile with: /Yu"C1094.h" /Zm300 /c
#include "C1094.h"   // C1094 compile with /Zm200
void Test() {}
```