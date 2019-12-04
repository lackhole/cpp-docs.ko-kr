---
title: 컴파일러 오류 C2531
ms.date: 11/04/2016
f1_keywords:
- C2531
helpviewer_keywords:
- C2531
ms.assetid: c49afe15-55f8-4dc8-ac01-bf653622a7db
ms.openlocfilehash: 4247e026f6680adab45ceebe2b395ad781ccfc7e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737116"
---
# <a name="compiler-error-c2531"></a>컴파일러 오류 C2531

' identifier ': 비트 필드에 대 한 참조가 잘못 되었습니다.

비트 필드에 대 한 참조는 허용 되지 않습니다.

다음 샘플에서는 C2531를 생성 합니다.

```cpp
// C2531.cpp
// compile with: /c
class P {
   int &b1 : 10;   // C2531
   int b2 : 10;   // OK
};
```
