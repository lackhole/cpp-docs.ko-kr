---
title: 컴파일러 오류 C2194
ms.date: 11/04/2016
f1_keywords:
- C2194
helpviewer_keywords:
- C2194
ms.assetid: df6e631c-0062-4844-9088-4cc7a0ff879f
ms.openlocfilehash: 6059b54c0b30bd11e1c8bc6f3779f4739d344ff7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174577"
---
# <a name="compiler-error-c2194"></a>컴파일러 오류 C2194

'identifier': 텍스트 세그먼트

합니다 `data_seg` pragma를 사용 하는 세그먼트 이름이 사용 `code_seg`합니다.

다음 샘플에서는 C2194 오류가 생성 됩니다.

```
// C2194.cpp
// compile with: /c
#pragma code_seg("MYCODE")
#pragma data_seg("MYCODE")   // C2194
#pragma data_seg("MYCODE2")   // OK
```