---
title: 컴파일러 오류 C3182
ms.date: 11/04/2016
f1_keywords:
- C3182
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
ms.openlocfilehash: 6866c7bbcee0a4097e490b344c79a6eec7f94570
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382419"
---
# <a name="compiler-error-c3182"></a>컴파일러 오류 C3182

'class': using 선언 또는 액세스 선언 멤버를 관리 되는 또는 WinRTtype 내에서 유효 하지 않은

A [를 사용 하 여](../../cpp/using-declaration.md) 선언은 모든 형식의 관리 되는 클래스 내에서 올바르지 않습니다.

다음 샘플에서는 C3182 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C3182a.cpp
// compile with: /clr /c
ref struct B {
   void mf(int) {
   }
};

ref struct D : B {
   using B::mf;   // C3182, delete to resolve
   void mf(char) {
   }
};
```
