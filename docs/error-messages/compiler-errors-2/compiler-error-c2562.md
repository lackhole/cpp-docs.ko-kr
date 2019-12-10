---
title: 컴파일러 오류 C2562
ms.date: 11/04/2016
f1_keywords:
- C2562
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
ms.openlocfilehash: 78536fdc0c2a6a6e9c4842fdea6423037496b30b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755553"
---
# <a name="compiler-error-c2562"></a>컴파일러 오류 C2562

' identifier ': ' void ' 함수에서 값을 반환 합니다.

함수는 `void`로 선언 되지만 값을 반환 합니다.

이 오류는 잘못 된 함수 프로토타입이 원인일 수 있습니다.

이 오류는 함수 선언에서 반환 형식을 지정 하는 경우 수정할 수 있습니다.

다음 샘플에서는 C2562를 생성 합니다.

```cpp
// C2562.cpp
// compile with: /c
void testfunc() {
   int i;
   return i;   // C2562 delete the return to resolve
}
```
