---
title: 컴파일러 오류 C2012
ms.date: 11/04/2016
f1_keywords:
- C2012
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
ms.openlocfilehash: a04f4a1758c9adb6e72b11881d18d210c9f36206
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752394"
---
# <a name="compiler-error-c2012"></a>컴파일러 오류 C2012

' < ' 뒤에 이름이 없습니다.

`#include` 지시문에 필요한 파일 이름이 없습니다.

다음 샘플에서는 C2012를 생성합니다.

```cpp
// C2012.cpp
#include <   // C2012 include the filename to resolve
```

가능한 해결 방법:

```cpp
// C2012b.cpp
// compile with: /c
#include <stdio.h>
```
