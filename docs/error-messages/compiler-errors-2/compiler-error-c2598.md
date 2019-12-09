---
title: 컴파일러 오류 C2598
ms.date: 11/04/2016
f1_keywords:
- C2598
helpviewer_keywords:
- C2598
ms.assetid: 40777c62-39ba-441e-b081-f49f94b43547
ms.openlocfilehash: a1ad34d454c5dc80feaac1df1383854391100ab0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759323"
---
# <a name="compiler-error-c2598"></a>컴파일러 오류 C2598

링크 사양은 전역 범위에 있어야 합니다.

링크 지정자는 로컬 범위에서 선언 됩니다.

다음 샘플에서는 C2598를 생성 합니다.

```cpp
// C2598.cpp
// compile with: /c
void func() {
   extern "C" int func2();   // C2598
}

extern "C" int func( int i );
```
