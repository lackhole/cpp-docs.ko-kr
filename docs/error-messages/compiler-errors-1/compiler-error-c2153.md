---
title: 컴파일러 오류 C2153
ms.date: 11/04/2016
f1_keywords:
- C2153
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
ms.openlocfilehash: 1f03b196b7ddaae80dac1941cdde5be16acace5f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748686"
---
# <a name="compiler-error-c2153"></a>컴파일러 오류 C2153

16 진수 상수에는 16 진수가 적어도 하나는 있어야 합니다.

16 진수 상수 0x, 0X 및 \x가 잘못 되었습니다. 하나 이상의 16 진수가 x 또는 X 뒤에와 야 합니다.

다음 샘플에서는 C2153를 생성 합니다.

```cpp
// C2153.cpp
int main() {
   int a= 0x;    // C2153
   int b= 0xA;   // OK
}
```
