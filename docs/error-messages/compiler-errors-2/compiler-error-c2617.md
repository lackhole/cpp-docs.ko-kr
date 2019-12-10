---
title: 컴파일러 오류 C2617
ms.date: 11/04/2016
f1_keywords:
- C2617
helpviewer_keywords:
- C2617
ms.assetid: d6a435d2-7d95-4dbf-ad4a-abe4744f63e8
ms.openlocfilehash: 60dd4e7de083bc4258eb7289d7b1c90d90871655
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754786"
---
# <a name="compiler-error-c2617"></a>컴파일러 오류 C2617

' function ': return 문이 일치 하지 않습니다.

지정 된 함수에는 선언 된 반환 형식이 없으며 이전 return 문에서는 값을 제공 하지 않았습니다.

다음 샘플에서는 C2617를 생성 합니다.

```cpp
// C2617.cpp
int i;
func() {   // no return type prototype
   if( i ) return;   // no return value
   else return( 1 );   // C2617 detected on this line
}
```

가능한 해결 방법:

```cpp
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
