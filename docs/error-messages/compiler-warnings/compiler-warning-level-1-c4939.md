---
title: 컴파일러 경고(수준 1) C4939
ms.date: 11/04/2016
f1_keywords:
- C4939
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
ms.openlocfilehash: c2c8f794356ea429f7cf647af18e06e7ebe9183e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74050269"
---
# <a name="compiler-warning-level-1-c4939"></a>컴파일러 경고(수준 1) C4939

\#pragma vtordisp는 더 이상 사용 되지 않으며 Visual의 이후 릴리스에서 제거 될 예정입니다.C++

[vtordisp](../../preprocessor/vtordisp.md) pragma는 이후 Visual C++ 릴리스에서 제거될 예정입니다.

## <a name="example"></a>예제

다음 샘플에서는 C4939를 생성합니다.

```cpp
// C4939.cpp
// compile with: /c /W1
#pragma vtordisp(off)   // C4939
```