---
title: 컴파일러 오류 C2236
ms.date: 11/04/2016
f1_keywords:
- C2236
helpviewer_keywords:
- C2236
ms.assetid: 0b6771a7-a783-4729-9c3d-7a3339c432cc
ms.openlocfilehash: 988377d2995468c84b86872ab6f2b25f5c3df9f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404314"
---
# <a name="compiler-error-c2236"></a>컴파일러 오류 C2236

예기치 않은 토큰 'identifier'입니다. ';'이 없습니다.

식별자가 이미 형식으로 정의되었으며 사용자 정의 형식으로 재정의할 수 없습니다.

다음 샘플에서는 C2236을 생성합니다.

```
// C2236.cpp
// compile with: /c
int class A {};  // C2236 "int class" is unexpected
int i;
class B {};
```