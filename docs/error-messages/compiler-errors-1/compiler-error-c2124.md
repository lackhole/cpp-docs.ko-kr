---
title: 컴파일러 오류 C2124
ms.date: 11/04/2016
f1_keywords:
- C2124
helpviewer_keywords:
- C2124
ms.assetid: 93392aaa-5582-4d68-8cc5-bd9c62a0ae7e
ms.openlocfilehash: 82bc4447aaf27190c013edf48a20a56c57a646c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397655"
---
# <a name="compiler-error-c2124"></a>컴파일러 오류 C2124

0으로 나누기 또는 나머지 연산을 수행했습니다.

상수 식의 분모가 0입니다. 이 오류를 해결하려면 0으로 나누지 마세요.

다음 샘플에서는 C2124를 생성합니다.

```
// C2124.cpp
int main() {
  int i = 1 / 0;   // C2124  do not divide by zero
  int i2 = 12 / 2;   // OK
}
```