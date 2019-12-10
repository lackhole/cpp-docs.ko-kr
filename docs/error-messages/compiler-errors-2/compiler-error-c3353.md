---
title: 컴파일러 오류 C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: 332e0b253aed53f2adadf448b6a9c0681abc825e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747453"
---
# <a name="compiler-error-c3353"></a>컴파일러 오류 C3353

'delegate': 대리자는 전역 함수 또는 관리되는 또는 WinRT 형식의 멤버 함수에서만 만들어질 수 있습니다.

[Delegate](../../extensions/delegate-cpp-component-extensions.md) 키워드로 선언 된 대리자는 전역 범위 에서만 선언할 수 있습니다.

다음 샘플에서는 C3353을 생성합니다.

```cpp
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```
