---
title: 심각한 오류 C1070
ms.date: 11/04/2016
f1_keywords:
- C1070
helpviewer_keywords:
- C1070
ms.assetid: 1058269a-5db6-4c23-a97f-b5269eb9188b
ms.openlocfilehash: 848c871049f498efc938ded4de11b4b8b6411976
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747464"
---
# <a name="fatal-error-c1070"></a>심각한 오류 C1070

'filename' 파일에서 #if/#endif 쌍이 짝이 맞지 않습니다.

`#if`, `#ifdef`또는 `#ifndef` 지시문에 해당하는 `#endif`가 없습니다.

다음 샘플에서는 C1070을 생성합니다.

```cpp
// C1070.cpp
#define TEST

#ifdef TEST

#ifdef TEST
#endif
// C1070
```

가능한 해결 방법:

```cpp
// C1070b.cpp
// compile with: /c
#define TEST

#ifdef TEST
#endif

#ifdef TEST
#endif
```
