---
title: 심각한 오류 C1070
ms.date: 11/04/2016
f1_keywords:
- C1070
helpviewer_keywords:
- C1070
ms.assetid: 1058269a-5db6-4c23-a97f-b5269eb9188b
ms.openlocfilehash: 7e156a230ce9550b65d1b8775947fc7294c15377
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166921"
---
# <a name="fatal-error-c1070"></a>심각한 오류 C1070

'filename' 파일에서 #if/#endif 쌍이 짝이 맞지 않습니다.

`#if`, `#ifdef`또는 `#ifndef` 지시문에 해당하는 `#endif`가 없습니다.

다음 샘플에서는 C1070을 생성합니다.

```
// C1070.cpp
#define TEST

#ifdef TEST

#ifdef TEST
#endif
// C1070
```

해결 방법:

```
// C1070b.cpp
// compile with: /c
#define TEST

#ifdef TEST
#endif

#ifdef TEST
#endif
```