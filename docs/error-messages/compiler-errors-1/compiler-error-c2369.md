---
title: 컴파일러 오류 C2369
ms.date: 11/04/2016
f1_keywords:
- C2369
helpviewer_keywords:
- C2369
ms.assetid: 2a3933f6-2313-40ff-800f-921b296fdbbf
ms.openlocfilehash: 8abb9a7b8d15fa2dd9999612551a0d0da1e34e30
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230355"
---
# <a name="compiler-error-c2369"></a>컴파일러 오류 C2369

'array': 재정의. 첨자가 다릅니다.

배열이 다른 아래 첨자로 이미 선언되었습니다.

다음 샘플에서는 C2369를 생성합니다.

```
// C2369.cpp
// compile with: /c
int a[10];
int a[20];   // C2369
int b[20];   // OK
```