---
title: 심각한 오류 C1019
ms.date: 11/04/2016
f1_keywords:
- C1019
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
ms.openlocfilehash: f33139393f7f6225edf0c4b3f992b93d35bd6afa
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756918"
---
# <a name="fatal-error-c1019"></a>심각한 오류 C1019

예기치 않은 #else입니다.

`#else` 지시문이 `#if`, `#ifdef`또는 `#ifndef` 구문 외부에 표시됩니다. `#else` 는 이러한 구문 중 하나 내에서만 사용합니다.

다음 샘플에서는 C1019를 생성합니다.

```cpp
// C1019.cpp
#else   // C1019
#endif

int main() {}
```

가능한 해결 방법:

```cpp
// C1019b.cpp
#if 1
#else
#endif

int main() {}
```
