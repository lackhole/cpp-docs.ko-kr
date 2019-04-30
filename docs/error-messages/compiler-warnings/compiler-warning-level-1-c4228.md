---
title: 컴파일러 경고(수준 1) C4228
ms.date: 11/04/2016
f1_keywords:
- C4228
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
ms.openlocfilehash: c737a48883b97970af70014e2bda4bdc508ab471
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207570"
---
# <a name="compiler-warning-level-1-c4228"></a>컴파일러 경고(수준 1) C4228

비표준 확장이 사용 됨: 선언 자 목록에서 쉼표 뒤의 한정자는 무시 됩니다.

한정자의 사용 하 여 같은 **상수** 또는 `volatile` 변수를 선언할 때 쉼표는 Microsoft 확장 한 후 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>예제

```
// C4228.cpp
// compile with: /W1
int j, const i = 0;  // C4228
int k;
int const m = 0;  // ok
int main()
{
}
```