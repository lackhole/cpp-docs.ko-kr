---
title: 컴파일러 오류 C2673
ms.date: 11/04/2016
f1_keywords:
- C2673
helpviewer_keywords:
- C2673
ms.assetid: 780230c0-619b-4a78-b01d-ff5886306741
ms.openlocfilehash: 5ade00d0b912a44c0916e5ce5aa7f23b2cc91cf8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757165"
---
# <a name="compiler-error-c2673"></a>컴파일러 오류 C2673

' function ': 전역 함수에는 ' this ' 포인터가 없습니다.

전역 함수가 `this`에 액세스 하려고 했습니다.

다음 샘플에서는 C2673를 생성 합니다.

```cpp
// C2673.cpp
int main() {
   this = 0;   // C2673
}
```
