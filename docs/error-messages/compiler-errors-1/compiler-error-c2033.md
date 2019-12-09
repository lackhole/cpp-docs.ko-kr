---
title: 컴파일러 오류 C2033
ms.date: 11/04/2016
f1_keywords:
- C2033
helpviewer_keywords:
- C2033
ms.assetid: fd5a1637-9db2-4c98-a7cc-b63b39737cd9
ms.openlocfilehash: 6fec222117f28e885d6187e6733559433f4943d3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750964"
---
# <a name="compiler-error-c2033"></a>컴파일러 오류 C2033

'identifier': 비트 필드에 간접 참조를 사용할 수 없습니다.

비트 필드가 허용되지 않는 포인터로 선언되었습니다.

다음 샘플에서는 C2033을 생성합니다.

```cpp
// C2033.cpp
struct S {
   int *b : 1;  // C2033
};
```

가능한 해결 방법:

```cpp
// C2033b.cpp
// compile with: /c
struct S {
   int b : 1;
};
```
