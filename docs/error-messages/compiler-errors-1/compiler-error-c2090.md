---
title: 컴파일러 오류 C2090
ms.date: 11/04/2016
f1_keywords:
- C2090
helpviewer_keywords:
- C2090
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
ms.openlocfilehash: 3c87bc75e984c544646a28a663302acd5733ac25
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755943"
---
# <a name="compiler-error-c2090"></a>컴파일러 오류 C2090

함수가 배열을 반환 합니다.

함수는 배열을 반환할 수 없습니다. 대신 배열에 대 한 포인터를 반환 합니다.

다음 샘플에서는 C2090를 생성 합니다.

```cpp
// C2090.cpp
int func1(void)[] {}   // C2090
```

가능한 해결 방법:

```cpp
// C2090b.cpp
// compile with: /c
int* func2(int * i) {
   return i;
}
```
