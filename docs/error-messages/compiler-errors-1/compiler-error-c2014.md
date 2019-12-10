---
title: 컴파일러 오류 C2014
ms.date: 11/04/2016
f1_keywords:
- C2014
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
ms.openlocfilehash: 6c7e941970415c933b38f35b6c09247a3c0fd411
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757399"
---
# <a name="compiler-error-c2014"></a>컴파일러 오류 C2014

전처리기 명령은 first 공백 아닌 space로 시작 해야 합니다.

전처리기 지시문의 `#` 부호는 공백이 아닌 줄의 첫 번째 문자 여야 합니다.

다음 샘플에서는 C2014를 생성 합니다.

```cpp
// C2014.cpp
int k; #include <stdio.h>   // C2014
```

가능한 해결 방법:

```cpp
// C2014b.cpp
// compile with: /c
int k;
#include <stdio.h>
```
