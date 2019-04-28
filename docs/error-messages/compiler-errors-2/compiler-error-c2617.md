---
title: 컴파일러 오류 C2617
ms.date: 11/04/2016
f1_keywords:
- C2617
helpviewer_keywords:
- C2617
ms.assetid: d6a435d2-7d95-4dbf-ad4a-abe4744f63e8
ms.openlocfilehash: 21add86e37d32525b69a02e848444919fe2a79f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208520"
---
# <a name="compiler-error-c2617"></a>컴파일러 오류 C2617

'function': return 문이 일관성이 없습니다

지정된 된 함수는 선언 된 반환 형식 및 이전 문에서 값을 제공 하지 않은 반환 없습니다.

다음 샘플에서는 C2617 오류가 생성 됩니다.

```
// C2617.cpp
int i;
func() {   // no return type prototype
   if( i ) return;   // no return value
   else return( 1 );   // C2617 detected on this line
}
```

해결 방법:

```
// C2617b.cpp
// compile with: /c
int i;
int MyF() {
   if (i)
      return 0;
   else
      return (1);
}
```