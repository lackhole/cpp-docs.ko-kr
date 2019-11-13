---
title: 컴파일러 경고 (수준 1) C4945
ms.date: 11/04/2016
f1_keywords:
- C4945
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
ms.openlocfilehash: 6a20effcebe1a36fa1356fffefa3a23a0056a0f0
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052254"
---
# <a name="compiler-warning-level-1-c4945"></a>컴파일러 경고 (수준 1) C4945

' symbol ': ' assembly2 '에서 기호를 가져올 수 없습니다. 다른 어셈블리 ' assembly1 '에서 ' 기호 '를 이미 가져왔습니다.

참조 된 어셈블리에서 기호를 가져왔지만 해당 기호를 이미 참조 된 다른 어셈블리에서 가져왔습니다. 어셈블리 중 하나를 참조 하지 않거나 어셈블리 중 하나에서 변경 된 기호 이름을 가져옵니다.

다음 샘플에서는 C4945를 생성 합니다.

```csharp
// C4945a.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

그런 다음

```csharp
// C4945b.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

그런 다음

```cpp
// C4945c.cpp
// compile with: /clr /LD /W1
#using "C4945a.dll"
#using "C4945b.dll"   // C4945
```