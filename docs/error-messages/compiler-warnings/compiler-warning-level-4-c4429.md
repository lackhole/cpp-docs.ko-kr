---
title: 컴파일러 경고(수준 4) C4429
ms.date: 11/04/2016
f1_keywords:
- C4429
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
ms.openlocfilehash: d4eb7e7075c7adf418254e748f104a6d57c72741
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391532"
---
# <a name="compiler-warning-level-4-c4429"></a>컴파일러 경고(수준 4) C4429

가능한 불완전 하거나 형식이 잘못 된 유니버설 문자 이름

컴파일러가 잘못 된 형식의 유니버설 문자 이름은 수 있는 문자 시퀀스를 발견 했습니다. 유니버설 문자 이름은 `\u` 뒤에 네 개의 16 진수 또는 `\U` 8 개의 16 진수가 옵니다.

다음 샘플에서는 C4429 오류가 생성 됩니다.

```
// C4429.cpp
// compile with: /W4 /WX
int \ug0e4 = 0;   // C4429
// Try the following line instead:
// int \u00e4 = 0;   // OK, a well-formed universal character name.
```