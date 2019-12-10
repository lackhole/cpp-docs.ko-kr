---
title: 컴파일러 오류 C2156
ms.date: 11/04/2016
f1_keywords:
- C2156
helpviewer_keywords:
- C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
ms.openlocfilehash: da8a5a9bcdeb33a9b308e24b129fded0595449a3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755904"
---
# <a name="compiler-error-c2156"></a>컴파일러 오류 C2156

pragma는 함수 외부에 있어야 합니다.

전역 수준(함수 본문 외부)에서 지정해야 하는 pragma가 함수 내에 있습니다.

다음 샘플에서는 C2156을 생성합니다.

```cpp
// C2156.cpp
#pragma optimize( "l", on )   // OK
int main() {
   #pragma optimize( "l", on )   // C2156
}
```
