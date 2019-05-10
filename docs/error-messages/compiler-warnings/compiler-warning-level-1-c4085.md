---
title: 컴파일러 경고(수준 1) C4085
ms.date: 11/04/2016
f1_keywords:
- C4085
helpviewer_keywords:
- C4085
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
ms.openlocfilehash: cfd2296d2e58899bf818281716af2074c2f0ce91
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406478"
---
# <a name="compiler-warning-level-1-c4085"></a>컴파일러 경고(수준 1) C4085

pragma 매개 변수는 'on' 또는 'off'이어야 합니다.

pragma에 **on** 또는 **off** 매개 변수가 필요합니다. pragma가 무시됩니다.

다음 샘플에서는 C4085를 생성합니다.

```
// C4085.cpp
// compile with: /W1 /LD
#pragma optimize( "t", maybe )  // C4085
```