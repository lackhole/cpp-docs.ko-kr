---
title: 컴파일러 오류 C2007
ms.date: 11/04/2016
f1_keywords:
- C2007
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
ms.openlocfilehash: 15ac3f76e99b3d101788fdcfd6760f6f9b284f34
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756541"
---
# <a name="compiler-error-c2007"></a>컴파일러 오류 C2007

구문 정의 \#

`#define`뒤에는 식별자가 표시 되지 않습니다. 오류를 해결 하려면 식별자를 사용 합니다.

다음 샘플에서는 C2007를 생성 합니다.

```cpp
// C2007.cpp
#define   // C2007
```

가능한 해결 방법:

```cpp
// C2007b.cpp
// compile with: /c
#define true 1
```
