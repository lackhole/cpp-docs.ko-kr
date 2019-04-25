---
title: 컴파일러 오류 C2162
ms.date: 11/04/2016
f1_keywords:
- C2162
helpviewer_keywords:
- C2162
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
ms.openlocfilehash: 02c0101324b28ebe548c38c6dc617faaa62315b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174785"
---
# <a name="compiler-error-c2162"></a>컴파일러 오류 C2162

예상된 매크로 정식 매개 변수

문자열 화 연산자 (#) 뒤의 토큰이 정식 매개 변수 이름이 아닙니다.

## <a name="example"></a>예제

다음 샘플에서는 C2162를 생성합니다.

```
// C2162.cpp
// compile with: /c
#include <stdio.h>

#define print(a) printf_s(b)   // OK
#define print(a) printf_s(#b)    // C2162
```