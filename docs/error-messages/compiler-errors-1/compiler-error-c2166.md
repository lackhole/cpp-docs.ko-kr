---
title: 컴파일러 오류 C2166
ms.date: 11/04/2016
f1_keywords:
- C2166
helpviewer_keywords:
- C2166
ms.assetid: 12789c3a-cc76-48bb-ae2e-64283e0964ed
ms.openlocfilehash: 36b4bcbd3eda213b840194cb635172a241f04b14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174721"
---
# <a name="compiler-error-c2166"></a>컴파일러 오류 C2166

l-value가 const 개체를 지정합니다.

코드에서 `const`로 선언된 항목을 수정하려고 합니다.

다음 샘플에서는 C2166을 생성합니다.

```
// C2166.cpp
int f();
int main() {
   ( (const int&) 1 ) = 5;   // C2166
}
```