---
title: 심각한 오류 C1016
ms.date: 11/04/2016
f1_keywords:
- C1016
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
ms.openlocfilehash: 7463c6962817716611f3571e073712f374773fa7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243863"
---
# <a name="fatal-error-c1016"></a>심각한 오류 C1016

\#ifdef 예상 #ifndef에는 식별자는 식별자가 필요 합니다.

조건부 컴파일 지시문([#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) 또는 `#ifndef`)에 평가할 식별자가 없습니다. 오류를 해결하려면 식별자를 지정합니다.

다음 샘플에서는 C1016을 생성합니다.

```
// C1016.cpp
#ifdef   // C1016
#define FC1016
#endif

int main() {}
```

해결 방법:

```
// C1016b.cpp
#ifdef X
#define FC1016
#endif

int main() {}
```