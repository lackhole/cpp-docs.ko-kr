---
title: 컴파일러 오류 C2490
ms.date: 11/04/2016
f1_keywords:
- C2490
helpviewer_keywords:
- C2490
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
ms.openlocfilehash: 9e06883d0e8b6103eb44d086d3872d86c50a58b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361806"
---
# <a name="compiler-error-c2490"></a>컴파일러 오류 C2490

' keyword' 'naked' 특성이 있는 함수에 사용할 수 없습니다

로 정의 된 함수 [naked](../../cpp/naked-cpp.md) 구조적된 예외 처리를 사용할 수 없습니다.

다음 샘플에서는 C2490 오류가 생성 됩니다.

```
// C2490.cpp
// processor: x86
__declspec( naked ) int func() {
   __try{}   // C2490, structured exception handling
}
```