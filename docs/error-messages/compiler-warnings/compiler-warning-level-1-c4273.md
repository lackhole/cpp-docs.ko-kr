---
title: 컴파일러 경고(수준 1) C4273
ms.date: 11/04/2016
f1_keywords:
- C4273
helpviewer_keywords:
- C4273
ms.assetid: cc18611d-9454-40a4-ad73-69823d5888fb
ms.openlocfilehash: 4d00ed0113f9954e7400da24f37b51b9fdd247bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207222"
---
# <a name="compiler-warning-level-1-c4273"></a>컴파일러 경고(수준 1) C4273

'function': DLL 링크가 일치 하지 않는

파일에서 두 개의 정의의 용도 다릅니다 [dllimport](../../cpp/dllexport-dllimport.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4273 오류가 발생 합니다.

```
// C4273.cpp
// compile with: /W1 /c
char __declspec(dllimport) c;
char c;   // C4273, delete this line or the line above to resolve
```

## <a name="example"></a>예제

다음 샘플에서는 C4273 오류가 발생 합니다.

```
// C4273_b.cpp
// compile with: /W1 /clr /c
#include <stdio.h>
extern "C" int printf_s(const char *, ...);   // C4273
```