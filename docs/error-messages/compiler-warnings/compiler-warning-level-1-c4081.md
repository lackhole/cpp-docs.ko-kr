---
title: 컴파일러 경고(수준 1) C4081
ms.date: 11/04/2016
f1_keywords:
- C4081
helpviewer_keywords:
- C4081
ms.assetid: 6f656373-a080-4989-bbc9-e2f894b03293
ms.openlocfilehash: 39b2c7b117f2040d68e42dd6cca37942c11bf0da
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626940"
---
# <a name="compiler-warning-level-1-c4081"></a>컴파일러 경고(수준 1) C4081

'token1'이 필요한데 'token2'가 있습니다.

이 컨텍스트에서는 컴파일러에 다른 토큰이 필요합니다.

## <a name="example"></a>예제

```cpp
// C4081.cpp
// compile with: /W1 /LD
#pragma optimize) "l", on )   // C4081
```