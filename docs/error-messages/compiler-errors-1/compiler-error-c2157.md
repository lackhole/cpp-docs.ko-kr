---
title: 컴파일러 오류 C2157
ms.date: 11/04/2016
f1_keywords:
- C2157
helpviewer_keywords:
- C2157
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
ms.openlocfilehash: 2fa73148c9dbce843d3d1d075ca836f47b5ae074
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755891"
---
# <a name="compiler-error-c2157"></a>컴파일러 오류 C2157

'function': pragma 목록에서 사용하려면 먼저 선언해야 합니다.

함수 이름이 선언되지 않은 상태에서 [alloc_text](../../preprocessor/alloc-text.md) pragma에 대한 함수 목록에서 참조되었습니다.

다음 샘플에서는 C2157을 생성합니다.

```cpp
// C2157.cpp
// compile with: /c
#pragma alloc_text( "func", func)   // C2157

// OK
extern "C" void func();
#pragma alloc_text( "func", func)
```
