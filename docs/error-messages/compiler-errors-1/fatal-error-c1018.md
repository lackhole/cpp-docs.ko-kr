---
title: 심각한 오류 C1018
ms.date: 11/04/2016
f1_keywords:
- C1018
helpviewer_keywords:
- C1018
ms.assetid: 2ceb8a99-30b2-4b80-bf42-e9f3305b3c52
ms.openlocfilehash: 3273288f1d60fad840fd8e9c459ce5d209ddb6a4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756931"
---
# <a name="fatal-error-c1018"></a>심각한 오류 C1018

예기치 않은 #elif입니다.

`#elif` 지시문이 `#if`, `#ifdef`또는 `#ifndef` 구문 외부에 표시됩니다. `#elif` 는 이러한 구문 중 하나 내에서만 사용합니다.

다음 샘플에서는 C1018을 생성합니다.

```cpp
// C1018.cpp
#elif      // C1018
#endif

int main() {}
```

가능한 해결 방법:

```cpp
// C1018b.cpp
#if 1
#elif
#endif

int main() {}
```
