---
title: 컴파일러 경고 (수준 1) C4227
ms.date: 11/04/2016
f1_keywords:
- C4227
helpviewer_keywords:
- C4227
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
ms.openlocfilehash: aea4d082b21d59aa430befd89d2032fb7ebc0e65
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627276"
---
# <a name="compiler-warning-level-1-c4227"></a>컴파일러 경고 (수준 1) C4227

오래 된 사용: 참조에 대 한 한정자는 무시 됩니다.

`const` 또는 `volatile` C++ 와 같은 한정자를 사용 하는 것은 오래 된 습관입니다.

## <a name="example"></a>예제

```cpp
// C4227.cpp
// compile with: /W1 /c
int j = 0;
int &const i = j;   // C4227
```