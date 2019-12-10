---
title: 심각한 오류 C1016
ms.date: 11/04/2016
f1_keywords:
- C1016
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
ms.openlocfilehash: b5774503297c596a351d72f3af4de6040628b078
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756957"
---
# <a name="fatal-error-c1016"></a>심각한 오류 C1016

\#ifdef를 사용할 때 식별자 # ifndef에 식별자가 필요 합니다.

조건부 컴파일 지시문([#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) 또는 `#ifndef`)에 평가할 식별자가 없습니다. 오류를 해결하려면 식별자를 지정합니다.

다음 샘플에서는 C1016을 생성합니다.

```cpp
// C1016.cpp
#ifdef   // C1016
#define FC1016
#endif

int main() {}
```

가능한 해결 방법:

```cpp
// C1016b.cpp
#ifdef X
#define FC1016
#endif

int main() {}
```
