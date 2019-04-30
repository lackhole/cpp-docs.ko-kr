---
title: 컴파일러 경고(수준 1) C4945
ms.date: 11/04/2016
f1_keywords:
- C4945
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
ms.openlocfilehash: 62dfbaed28f1afcdedb41d83158dfe4e8e0f61b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384168"
---
# <a name="compiler-warning-level-1-c4945"></a>컴파일러 경고(수준 1) C4945

'symbol': 'assembly2'에서 기호를 가져올 수 없습니다: 'symbol' 어셈블리가 'assembly1'에서 이미 가져온 대로

기호가 참조 된 어셈블리에서 가져온 하지만 해당 기호를 다른 참조 된 어셈블리에서 이미 가져왔습니다. 중 하나는 어셈블리 중 하나를 참조 하지 않거나 어셈블리 중 하나에서 변경 기호 이름을 가져옵니다.

다음 샘플에서는 C4945 생성 합니다.

```
// C4945a.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

그런 다음

```
// C4945b.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

그런 다음

```
// C4945c.cpp
// compile with: /clr /LD /W1
#using "C4945a.dll"
#using "C4945b.dll"   // C4945
```