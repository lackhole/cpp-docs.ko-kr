---
title: 컴파일러 오류 C2534
ms.date: 11/04/2016
f1_keywords:
- C2534
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
ms.openlocfilehash: 4b1e481c733f52b0be419b7fd786b26a90362f9c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737091"
---
# <a name="compiler-error-c2534"></a>컴파일러 오류 C2534

' identifier ': 생성자는 값을 반환할 수 없습니다.

생성자는 값을 반환 하거나 반환 형식 (`void` 반환 형식이 아니더라도)을 포함할 수 없습니다.

생성자 정의에서 `return` 문을 제거 하 여이 오류를 해결할 수 있습니다.

다음 샘플에서는 C2534를 생성 합니다.

```cpp
// C2534.cpp
class A {
public:
   int i;
   A() { return i; }   // C2534
};
```
