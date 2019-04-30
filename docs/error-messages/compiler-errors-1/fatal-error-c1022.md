---
title: 심각한 오류 C1022
ms.date: 11/04/2016
f1_keywords:
- C1022
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
ms.openlocfilehash: 044ebbbe895677acf74977e56879c292486e18cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383141"
---
# <a name="fatal-error-c1022"></a>심각한 오류 C1022

#endif가 필요합니다.

`#if`, `#ifdef`또는 `#ifndef` 지시문에 일치하는 `#endif` 지시문이 없습니다. 각 `#if`, `#ifdef`또는 `#ifndef` 에 일치하는 `#endif`가 있어야 합니다.

다음 샘플에서는 C1022를 생성합니다.

```
// C1022.cpp
#define true 1

#if (true)
#else
#else    // C1022
```

해결 방법:

```
// C1022b.cpp
// compile with: /c
#define true 1

#if (true)
#else
#endif
```