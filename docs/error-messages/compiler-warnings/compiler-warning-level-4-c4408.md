---
title: 컴파일러 경고(수준 4) C4408
ms.date: 11/04/2016
f1_keywords:
- C4408
helpviewer_keywords:
- C4408
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
ms.openlocfilehash: 3c7613d42bbd0ac7fa58a0b95ba68efb60d9f50a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391571"
---
# <a name="compiler-warning-level-4-c4408"></a>컴파일러 경고(수준 4) C4408

anonymousstruct 또는 공용 구조체 데이터 멤버를 선언 하지 않았습니다.

익명 구조체 또는 공용 구조체에 데이터 멤버가 하나 이상 있어야 합니다.

다음 샘플에서는 C4408 오류가 발생하는 경우를 보여 줍니다.

```
// C4408.cpp
// compile with: /W4 /LD
static union
{
   // int i;
};
// a named union can have no data members
// } MyUnion;
```