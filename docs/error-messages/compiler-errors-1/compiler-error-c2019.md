---
title: 컴파일러 오류 C2019
ms.date: 11/04/2016
f1_keywords:
- C2019
helpviewer_keywords:
- C2019
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
ms.openlocfilehash: 5343d6760a7a7f2c868d92790bf9930e431e3517
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757516"
---
# <a name="compiler-error-c2019"></a>컴파일러 오류 C2019

전처리기 지시문이 있어야 하는데 'character'가 있습니다.

문자 뒤에 `#` 기호가 있지만 전처리기 지시문의 첫 글자가 아닙니다.

다음 샘플에서는 C2019를 생성 합니다.

```cpp
// C2019.cpp
#!define TRUE 1   // C2019
```

가능한 해결 방법:

```cpp
// C2019b.cpp
// compile with: /c
#define TRUE 1
```
