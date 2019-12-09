---
title: 컴파일러 오류 C2236
ms.date: 11/04/2016
f1_keywords:
- C2236
helpviewer_keywords:
- C2236
ms.assetid: 0b6771a7-a783-4729-9c3d-7a3339c432cc
ms.openlocfilehash: f61c5cd6da036d54c6184871deb45fed0210c48a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759232"
---
# <a name="compiler-error-c2236"></a>컴파일러 오류 C2236

예기치 않은 토큰 'identifier'입니다. ';'이 없습니다.

식별자가 이미 형식으로 정의되었으며 사용자 정의 형식으로 재정의할 수 없습니다.

다음 샘플에서는 C2236을 생성합니다.

```cpp
// C2236.cpp
// compile with: /c
int class A {};  // C2236 "int class" is unexpected
int i;
class B {};
```
