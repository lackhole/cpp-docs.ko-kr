---
title: 컴파일러 오류 C2646
ms.date: 11/04/2016
f1_keywords:
- C2646
helpviewer_keywords:
- C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
ms.openlocfilehash: a5c4dbc967c304fc6b13eb00e2c7093380ec8be9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758218"
---
# <a name="compiler-error-c2646"></a>컴파일러 오류 C2646

전역 또는 네임스페이스 범위의 익명 구조체 또는 공용 구조체는 static으로 선언해야 합니다.

익명 구조체 또는 공용 구조체가 전역 또는 네임스페이스 범위를 가지지만 `static`으로 선언되지 않았습니다.

다음 샘플에서는 C2646 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C2646.cpp
// compile with: /c
union { int i; };   // C2646 not static

// OK
static union { int j; };
union U { int i; };
```
