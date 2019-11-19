---
title: 컴파일러 경고 (수준 1) C4229
ms.date: 11/04/2016
f1_keywords:
- C4229
helpviewer_keywords:
- C4229
ms.assetid: aadfc83b-1e5f-4229-bd0a-9c10a5d13182
ms.openlocfilehash: 3d2372275da02a7c3bbde6c8bf044c621c5d3d09
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624925"
---
# <a name="compiler-warning-level-1-c4229"></a>컴파일러 경고 (수준 1) C4229

오래 된 사용: 데이터의 한정자는 무시 됩니다.

데이터 선언에 `__cdecl`와 같은 Microsoft 한정자를 사용 하는 것은 오래 된 방법입니다.

## <a name="example"></a>예제

```cpp
// C4229.cpp
// compile with: /W1 /LD
int __cdecl counter;   // C4229 cdecl ignored
```