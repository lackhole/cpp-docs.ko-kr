---
title: 컴파일러 오류 C3886
ms.date: 11/04/2016
f1_keywords:
- C3886
helpviewer_keywords:
- C3886
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
ms.openlocfilehash: e9e9d4b478d5b53e50203d1f009295e1da444f2d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59775845"
---
# <a name="compiler-error-c3886"></a>컴파일러 오류 C3886

'var': 리터럴 데이터 멤버를 초기화 합니다

A [리터럴](../../extensions/literal-cpp-component-extensions.md) 변수를 선언할 때 초기화 해야 합니다.

다음 샘플에서는 C3886를 생성합니다.

```
// C3886.cpp
// compile with: /clr /c
ref struct Y1 {
   literal int staticConst;   // C3886
   literal int staticConst2 = 0;   // OK
};
```