---
title: 컴파일러 오류 C2279
ms.date: 11/04/2016
f1_keywords:
- C2279
helpviewer_keywords:
- C2279
ms.assetid: 1b5c88ef-2336-49b8-9ddb-d61f97c73e14
ms.openlocfilehash: b3b37788d6e4727761ab993f0502746edace18e9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759180"
---
# <a name="compiler-error-c2279"></a>컴파일러 오류 C2279

typedef 선언에는 예외 사양이 나타날 수 없습니다.

**/Za**에서는 typedef 선언에 [예외 사양을](../../cpp/exception-specifications-throw-cpp.md) 사용할 수 없습니다.

다음 샘플에서는 C2279를 생성 합니다.

```cpp
// C2279.cpp
// compile with: /Za /c
typedef int (*xy)() throw(...);   // C2279
typedef int (*xyz)();   // OK
```
