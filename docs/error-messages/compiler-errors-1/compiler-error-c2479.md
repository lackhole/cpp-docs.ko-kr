---
title: 컴파일러 오류 C2479
ms.date: 11/04/2016
f1_keywords:
- C2479
helpviewer_keywords:
- C2479
ms.assetid: c74c7869-e65b-4ca1-b6fa-eb39fed4458a
ms.openlocfilehash: c7bddd21faab8c55f349c6e03fbcd3db42c3fa7d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743564"
---
# <a name="compiler-error-c2479"></a>컴파일러 오류 C2479

' identifier ': ' allocate () '는 정적 범위의 데이터 항목에만 유효 합니다.

`__declspec( allocate())` 구문은 정적 데이터에만 사용할 수 있습니다.

다음 샘플에서는 C2479를 생성 합니다.

```cpp
// C2479.cpp
// compile with: /c
#pragma section("mycode", read)
static __declspec(allocate("mycode")) void DoNothing() {}   // C2479
__declspec(allocate("mycode"))  int i = 0;   // OK
```
