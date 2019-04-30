---
title: 컴파일러 경고(수준 1) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: a45cd6cf86eb8ab1edb33ad5e0df8374972c425e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386488"
---
# <a name="compiler-warning-level-1-c4215"></a>컴파일러 경고(수준 1) C4215

비표준 확장이 사용 됨: long float

기본 Microsoft 확장명 (/Ze) 취급 **float long** 으로 **double**합니다. ANSI 호환성 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) 하지 않습니다. 사용 하 여 **이중** 호환성을 유지 합니다.

다음 샘플에서는 C4215 오류가 생성 됩니다.

```
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```