---
title: 컴파일러 오류 C2199
ms.date: 11/04/2016
f1_keywords:
- C2199
helpviewer_keywords:
- C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
ms.openlocfilehash: e5892a537cbf337b23ff2356583cec4bf5925677
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368489"
---
# <a name="compiler-error-c2199"></a>컴파일러 오류 C2199

구문 오류: 찾을 ' 식별자 (' 전역 범위에서 (계획 된 선언?)

지정된 된 컨텍스트는 구문 오류가 발생 했습니다. 잘못 된 선언 구문이 있을 수 있습니다.

다음 샘플에서는 C2199 오류가 생성 됩니다.

```
// C2199.cpp
// compile with: /c
int j = int(1) int(1);   // C2199
int j = 1;   // OK
```