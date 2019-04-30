---
title: 컴파일러 오류 C3697
ms.date: 11/04/2016
f1_keywords:
- C3697
helpviewer_keywords:
- C3697
ms.assetid: 2d3f63c4-b7f8-421d-a7a5-2bf17fd054f9
ms.openlocfilehash: 55eadd55af8d4e6f088a0d0eb732d820242cae66
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363689"
---
# <a name="compiler-error-c3697"></a>컴파일러 오류 C3697

'한정자':이 한정자를 사용할 수 없습니다 ' ^'

추적 핸들 (^)에 사용할 수 없는 한정자를 적용 했습니다.

다음 샘플에서는 C3697 오류가 생성 됩니다.

```
// C3697.cpp
// compile with: /clr
using namespace System;
int main() {
   String ^__restrict s;   // C3697
   String ^ s2;   // OK
}
```