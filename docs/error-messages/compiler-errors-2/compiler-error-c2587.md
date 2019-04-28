---
title: 컴파일러 오류 C2587
ms.date: 11/04/2016
f1_keywords:
- C2587
helpviewer_keywords:
- C2587
ms.assetid: 7637a2c7-35d4-4b5a-a8f2-515a7bda98fd
ms.openlocfilehash: 08a576d5672f0df1cbec7269f83a3f182ce0e1c3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350508"
---
# <a name="compiler-error-c2587"></a>컴파일러 오류 C2587

'identifier': 기본 매개 변수로 잘못 된 지역 변수 사용

지역 변수는 기본 매개 변수로 허용 되지 않습니다.

다음 샘플에서는 C2587 오류가 생성 됩니다.

```
// C2587.cpp
// compile with: /c
int i;
void func() {
   int j;
   extern void func2( int k = j );  // C2587 -- local variable
   extern void func3( int k = i );   // OK
}
```