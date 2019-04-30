---
title: 컴파일러 오류 C3644
ms.date: 11/04/2016
f1_keywords:
- C3644
helpviewer_keywords:
- C3644
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
ms.openlocfilehash: 6d147d6a5955208bbca1ccf9a2f2bcfe3f485b4f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385630"
---
# <a name="compiler-error-c3644"></a>컴파일러 오류 C3644

'function': 관리 코드를 생성 하는 함수를 컴파일할 수 없습니다.

함수에서 일부 키워드의 현재 상태를 사용 하면 함수가를 네이티브로 컴파일하도록 합니다.

다음 샘플에서는 C3644 오류가 생성 됩니다.

```
// C3644.cpp
// compile with: /clr
// processor: x86

void __clrcall Func2(int i) {
   __asm {}   // C3644
}
```