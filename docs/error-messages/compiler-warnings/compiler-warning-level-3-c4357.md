---
title: 컴파일러 경고(수준 3) C4357
ms.date: 11/04/2016
f1_keywords:
- C4357
helpviewer_keywords:
- C4357
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
ms.openlocfilehash: a7923fdcda2a781c9680f8b3753fd101c73be19c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402023"
---
# <a name="compiler-warning-level-3-c4357"></a>컴파일러 경고(수준 3) C4357

매개 변수 배열 인수에 대 한 형식 인수 목록에 대리자 'del' 'function'를 생성 하는 경우 무시 됩니다.

`ParamArray` 특성을 무시 하 고 `function` 가변 인수를 사용 하 여 호출할 수 없습니다.

다음 샘플에서는 C4357 오류가 생성 됩니다.

```
// C4357.cpp
// compile with: /clr /W3 /c
using namespace System;
public delegate void f(int i, ... array<Object^>^ varargs);   // C4357

public delegate void g(int i, array<Object^>^ varargs);   // OK
```