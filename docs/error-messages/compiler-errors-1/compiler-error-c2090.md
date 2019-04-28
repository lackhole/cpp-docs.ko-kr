---
title: 컴파일러 오류 C2090
ms.date: 11/04/2016
f1_keywords:
- C2090
helpviewer_keywords:
- C2090
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
ms.openlocfilehash: d805a4d6e0da0e94288ac36c6680a952b7633b86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347248"
---
# <a name="compiler-error-c2090"></a>컴파일러 오류 C2090

함수가 배열을 반환합니다.

함수는 배열을 반환할 수 없습니다. 대신 배열에 대 한 포인터를 반환 합니다.

다음 샘플에서는 C2090 오류가 생성 됩니다.

```
// C2090.cpp
int func1(void)[] {}   // C2090
```

해결 방법:

```
// C2090b.cpp
// compile with: /c
int* func2(int * i) {
   return i;
}
```