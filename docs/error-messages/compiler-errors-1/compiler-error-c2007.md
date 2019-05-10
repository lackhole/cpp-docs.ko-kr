---
title: 컴파일러 오류 C2007
ms.date: 11/04/2016
f1_keywords:
- C2007
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
ms.openlocfilehash: f3c7b1a18dda9b2f9af7e346c2a1ed2f0303bb61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208901"
---
# <a name="compiler-error-c2007"></a>컴파일러 오류 C2007

\#구문 정의

식별자가 없는 뒤를 `#define`입니다. 이 오류를 해결 하려면 식별자를 사용 합니다.

다음 샘플에서는 C2007 오류가 생성 됩니다.

```
// C2007.cpp
#define   // C2007
```

해결 방법:

```
// C2007b.cpp
// compile with: /c
#define true 1
```