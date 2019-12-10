---
title: 컴파일러 오류 C2489
ms.date: 11/04/2016
f1_keywords:
- C2489
helpviewer_keywords:
- C2489
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
ms.openlocfilehash: 1977e32cec9d88a51aa6ec450a09be7fc33eb408
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757100"
---
# <a name="compiler-error-c2489"></a>컴파일러 오류 C2489

' identifier ': 초기화 된 auto 또는 register 변수는 ' naked ' 함수의 함수 범위에서 사용할 수 없습니다.

자세한 내용은 [naked](../../cpp/naked-cpp.md)를 참조 하세요.

다음 샘플에서는 C2489를 생성 합니다.

```cpp
// C2489.cpp
// processor: x86
__declspec( naked ) int func() {
   int i = 1;   // C2489
   register int j = 1;   // C2489
}
```
