---
title: 컴파일러 오류 C2637
ms.date: 11/04/2016
f1_keywords:
- C2637
helpviewer_keywords:
- C2637
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
ms.openlocfilehash: 4231a811911fdf600b47962e929f6f3cff1f1bca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395458"
---
# <a name="compiler-error-c2637"></a>컴파일러 오류 C2637

'identifier': 데이터 멤버에 대 한 포인터를 수정할 수 없습니다.

데이터 멤버에 대 한 포인터는 호출 규칙을 사용할 수 없습니다. 를 해결 하려면 호출 규칙을 제거 하거나 멤버 함수에 대 한 포인터를 선언 합니다.

다음 샘플에서는 C2637 오류가 생성 됩니다.

```
// C2637.cpp
// compile with: /c
struct S {};
int __stdcall S::*pms1;   // C2637

// OK
int S::*pms2;
int (__stdcall S::*pms3)(...);
```