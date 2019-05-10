---
title: 컴파일러 오류 C2213
ms.date: 11/04/2016
f1_keywords:
- C2213
helpviewer_keywords:
- C2213
ms.assetid: ff012278-7f3b-4d49-aaed-2349756f6225
ms.openlocfilehash: 125529aa23d43d9acd63652f73f636fee567f90a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400437"
---
# <a name="compiler-error-c2213"></a>컴파일러 오류 C2213

'modifier': __based에 대 한 인수가 잘못 되었습니다.

인수 수정 `__based` 올바르지 않습니다.

다음 샘플에서는 C2213 오류가 생성 됩니다.

```
// C2213.cpp
// compile with: /c
int i;
int *j;
char __based(i) *p;   // C2213
char __based(j) *p2;   // OK
```