---
title: 컴파일러 오류 C2490
ms.date: 11/04/2016
f1_keywords:
- C2490
helpviewer_keywords:
- C2490
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
ms.openlocfilehash: 86d9f41db8ba386a64878eebfae989011f637d71
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757087"
---
# <a name="compiler-error-c2490"></a>컴파일러 오류 C2490

' t o k e n '은 ' naked ' 특성이 있는 함수에 사용할 수 없습니다.

[Naked](../../cpp/naked-cpp.md) 로 정의 된 함수는 구조적 예외 처리를 사용할 수 없습니다.

다음 샘플에서는 C2490를 생성 합니다.

```cpp
// C2490.cpp
// processor: x86
__declspec( naked ) int func() {
   __try{}   // C2490, structured exception handling
}
```
