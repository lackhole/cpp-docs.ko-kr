---
title: 컴파일러 오류 C2041
ms.date: 11/04/2016
f1_keywords:
- C2041
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
ms.openlocfilehash: 37d32285f9c01efb981c5f02acba21f2d6fe3dc2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165672"
---
# <a name="compiler-error-c2041"></a>컴파일러 오류 C2041

'character' 기본 'number'에 대 한 숫자가 잘못 되었습니다

지정된 된 문자 (예: 8 진수 또는 16 진수) 기준에 유효한 숫자가 아닙니다.

다음 샘플에서는 C2041 오류가 생성 됩니다.

```
// C2041.cpp
int i = 081;   // C2041  8 is not a base 8 digit
```

해결 방법:

```
// C2041b.cpp
// compile with: /c
int j = 071;
```