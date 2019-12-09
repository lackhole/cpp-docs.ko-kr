---
title: 컴파일러 오류 C2034
ms.date: 11/04/2016
f1_keywords:
- C2034
helpviewer_keywords:
- C2034
ms.assetid: 953d70fa-bde9-4ce6-a55d-741e7bc63ff4
ms.openlocfilehash: c416c833edf522e4e67cf84aaf7fc945ee8a7972
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755111"
---
# <a name="compiler-error-c2034"></a>컴파일러 오류 C2034

' identifier ': 비트 필드의 형식이 비트 수에 비해 너무 작습니다.

비트 필드 선언의 비트 수가 기본 형식의 크기를 초과 합니다.

다음 샘플에서는 C2034를 생성 합니다.

```cpp
// C2034.cpp
struct A {
   char test : 9;   // C2034, char has 8 bits
};
```

가능한 해결 방법:

```cpp
// C2034b.cpp
// compile with: /c
struct A {
   char test : 8;
};
```
