---
title: 컴파일러 경고(수준 4) C4408
ms.date: 11/04/2016
f1_keywords:
- C4408
helpviewer_keywords:
- C4408
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
ms.openlocfilehash: 90ca85384b28f1cf2cdef5e4083813686b96c524
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74682965"
---
# <a name="compiler-warning-level-4-c4408"></a>컴파일러 경고(수준 4) C4408

anonymousstruct 또는 union이 데이터 멤버를 선언 하지 않았습니다.

익명 구조체 또는 공용 구조체에 데이터 멤버가 하나 이상 있어야 합니다.

다음 샘플에서는 C4408 오류가 발생하는 경우를 보여 줍니다.

```cpp
// C4408.cpp
// compile with: /W4 /LD
static union
{
   // int i;
};
// a named union can have no data members
// } MyUnion;
```