---
title: 컴파일러 오류 C3887
ms.date: 11/04/2016
f1_keywords:
- C3887
helpviewer_keywords:
- C3887
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
ms.openlocfilehash: f64b72fe5d546550c32f60a27360d8a77c8255bd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736583"
---
# <a name="compiler-error-c3887"></a>컴파일러 오류 C3887

' var ': 리터럴 데이터 멤버에 대 한 이니셜라이저는 상수 식 이어야 합니다.

[리터럴](../../extensions/literal-cpp-component-extensions.md) 데이터 멤버는 상수 식 초기화할 수 있습니다.

다음 샘플에서는 C3887를 생성 합니다.

```cpp
// C3887.cpp
// compile with: /clr
ref struct Y1 {
   static int i = 9;
   literal
   int staticConst = i;   // C3887
};
```

가능한 해결 방법:

```cpp
// C3887b.cpp
// compile with: /clr /c
ref struct Y1 {
   literal
   int staticConst = 9;
};
```
