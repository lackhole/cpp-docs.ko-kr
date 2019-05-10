---
title: 컴파일러 경고(수준 4) C4343
ms.date: 11/04/2016
f1_keywords:
- C4343
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
ms.openlocfilehash: c8f0bb514a3da932500f986e50a20af0947827c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403989"
---
# <a name="compiler-warning-level-4-c4343"></a>컴파일러 경고(수준 4) C4343

\#pragma optimize("g",off) /Og 옵션을 재정의합니다.

이 경고는 IPF(Itanium Processor Family) 컴파일러에서만 사용되며 pragma [optimize](../../preprocessor/optimize.md) 가 [/Og](../../build/reference/og-global-optimizations.md) 컴파일러 옵션을 재정의했음을 보고합니다.

다음 샘플에서는 C4343을 생성합니다.

```
// C4343.cpp
// compile with: /Og /W4 /LD
// processor: IPF
#pragma optimize ("g", off)   // C4343
```