---
title: 컴파일러 오류 C2267
ms.date: 11/04/2016
f1_keywords:
- C2267
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
ms.openlocfilehash: c897f8e6b38743ee98ec29707b222901ddde9d7c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758738"
---
# <a name="compiler-error-c2267"></a>컴파일러 오류 C2267

' function ': 블록 범위를 사용 하는 정적 함수가 잘못 되었습니다.

지역 함수는 `static`선언 됩니다. 정적 함수는 전역 범위를 가져야 합니다.

다음 샘플에서는 C2267를 생성 합니다.

```cpp
// C2267.cpp
static int func2();   // OK
int main() {
    static int func1();   // C2267
}
```
