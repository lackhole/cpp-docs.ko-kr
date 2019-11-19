---
title: 컴파일러 경고(수준 1) C4085
ms.date: 11/04/2016
f1_keywords:
- C4085
helpviewer_keywords:
- C4085
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
ms.openlocfilehash: bf006a2e566fe79b44f71192e95278392fe4f59e
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626870"
---
# <a name="compiler-warning-level-1-c4085"></a>컴파일러 경고(수준 1) C4085

pragma 매개 변수는 'on' 또는 'off'이어야 합니다.

pragma에 **on** 또는 **off** 매개 변수가 필요합니다. pragma가 무시됩니다.

다음 샘플에서는 C4085를 생성합니다.

```cpp
// C4085.cpp
// compile with: /W1 /LD
#pragma optimize( "t", maybe )  // C4085
```