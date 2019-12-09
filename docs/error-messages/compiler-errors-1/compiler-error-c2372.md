---
title: 컴파일러 오류 C2372
ms.date: 11/04/2016
f1_keywords:
- C2372
helpviewer_keywords:
- C2372
ms.assetid: 406bea63-c8d3-4231-9d26-c70af6980840
ms.openlocfilehash: d5f4653ded6d2800d74418a712bbcb3d4d4d6676
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745618"
---
# <a name="compiler-error-c2372"></a>컴파일러 오류 C2372

' identifier ': 재정의 서로 다른 유형의 간접 참조

식별자가 이미 다른 파생 형식으로 정의 되어 있습니다.

다음 샘플에서는 C2326을 생성합니다.

```cpp
// C2372.cpp
// compile with: /c
extern int *fp;
extern int fp[];   // C2372
extern int fp2[];   // OK
```
