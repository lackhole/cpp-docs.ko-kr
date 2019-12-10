---
title: 컴파일러 오류 C3139
ms.date: 11/04/2016
f1_keywords:
- C3139
helpviewer_keywords:
- C3139
ms.assetid: 95c92263-10ac-4ff3-b385-6312dd92adbc
ms.openlocfilehash: 274f3cdb3425a8a0e1e282ca6e9ca79f70077233
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761260"
---
# <a name="compiler-error-c3139"></a>컴파일러 오류 C3139

' struct ': 멤버 없이 UDT를 내보낼 수 없습니다.

빈 UDT (사용자 정의 형식)에 [내보내기](../../windows/export.md) 특성을 적용 하려고 했습니다. 예를 들면 다음과 같습니다.:

```cpp
// C3139.cpp
#include "unknwn.h"
[emitidl];
[module(name=xx)];

[export] struct MyStruct {   // C3139 empty type
};
int main(){}
```
