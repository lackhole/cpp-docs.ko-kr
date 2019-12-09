---
title: 컴파일러 오류 C2166
ms.date: 11/04/2016
f1_keywords:
- C2166
helpviewer_keywords:
- C2166
ms.assetid: 12789c3a-cc76-48bb-ae2e-64283e0964ed
ms.openlocfilehash: 73b3c29c5e4bdd22a50330a8a90aad37a9d45cbf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758413"
---
# <a name="compiler-error-c2166"></a>컴파일러 오류 C2166

l-value가 const 개체를 지정합니다.

코드에서 `const`로 선언된 항목을 수정하려고 합니다.

다음 샘플에서는 C2166을 생성합니다.

```cpp
// C2166.cpp
int f();
int main() {
   ( (const int&) 1 ) = 5;   // C2166
}
```
