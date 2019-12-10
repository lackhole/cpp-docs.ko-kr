---
title: 컴파일러 경고(수준 3) C4646
ms.date: 11/04/2016
f1_keywords:
- C4646
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
ms.openlocfilehash: a5f78a978baa1c5b4c7854692d7b8b6ff294f3a2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991728"
---
# <a name="compiler-warning-level-3-c4646"></a>컴파일러 경고(수준 3) C4646

__declspec(noreturn)으로 선언된 함수에 void가 아닌 반환 형식이 있습니다.

[noreturn](../../cpp/noreturn.md) `__declspec` 한정자로 표시한 함수에는 [void](../../cpp/void-cpp.md) 반환 형식이 있어야 합니다.

다음 샘플에서는 C4646을 생성합니다.

```cpp
// C4646.cpp
// compile with: /W3 /WX
int __declspec(noreturn) TestFunction()
{   // C4646  make return type void
}
```
