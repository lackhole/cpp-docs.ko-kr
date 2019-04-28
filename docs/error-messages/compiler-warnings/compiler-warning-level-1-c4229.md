---
title: 컴파일러 경고(수준 1) C4229
ms.date: 11/04/2016
f1_keywords:
- C4229
helpviewer_keywords:
- C4229
ms.assetid: aadfc83b-1e5f-4229-bd0a-9c10a5d13182
ms.openlocfilehash: 05d11a02d3aea8748a2955dff77a0af750ee0275
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207507"
---
# <a name="compiler-warning-level-1-c4229"></a>컴파일러 경고(수준 1) C4229

된 구문을 사용 했습니다: 데이터의 한정자는 무시 됩니다.

와 같은 Microsoft 한정자를 사용 하 여 `__cdecl` 데이터 선언에는 오래 된 방법입니다.

## <a name="example"></a>예제

```
// C4229.cpp
// compile with: /W1 /LD
int __cdecl counter;   // C4229 cdecl ignored
```