---
title: 컴파일러 오류 C2495
ms.date: 11/04/2016
f1_keywords:
- C2495
helpviewer_keywords:
- C2495
ms.assetid: bb7066fe-3549-4901-97e4-157f3c04dd57
ms.openlocfilehash: 5e16404e8c23a902a2cdbfc436cecdff21e68b6a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757022"
---
# <a name="compiler-error-c2495"></a>컴파일러 오류 C2495

' identifier ': ' nothrow '는 함수 선언 또는 정의에만 적용할 수 있습니다.

[Nothrow](../../cpp/nothrow-cpp.md) 확장 특성은 함수 선언 또는 정의에만 적용할 수 있습니다.

다음 샘플에서는 C2495를 생성 합니다.

```cpp
// C2495.cpp
// compile with: /c
__declspec(nothrow) class X {   // C2495
   int m_data;
} x;

__declspec(nothrow) void test();   // OK
```
