---
title: 컴파일러 오류 C3887
ms.date: 11/04/2016
f1_keywords:
- C3887
helpviewer_keywords:
- C3887
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
ms.openlocfilehash: 85434cb8daba0db82843c09e2d1bb09d98960272
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58777443"
---
# <a name="compiler-error-c3887"></a>컴파일러 오류 C3887

'var': 리터럴 데이터 멤버에 대 한 이니셜라이저는 상수 식 이어야 합니다.

A [리터럴](../../extensions/literal-cpp-component-extensions.md) 데이터 멤버는 상수 식만 초기화할 수 있습니다.

다음 샘플에서는 C3887 오류가 생성 됩니다.

```
// C3887.cpp
// compile with: /clr
ref struct Y1 {
   static int i = 9;
   literal
   int staticConst = i;   // C3887
};
```

해결 방법:

```
// C3887b.cpp
// compile with: /clr /c
ref struct Y1 {
   literal
   int staticConst = 9;
};
```