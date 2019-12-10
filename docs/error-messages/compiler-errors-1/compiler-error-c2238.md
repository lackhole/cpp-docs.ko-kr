---
title: 컴파일러 오류 C2238
ms.date: 11/04/2016
f1_keywords:
- C2238
helpviewer_keywords:
- C2238
ms.assetid: 3d53060c-d6b7-4603-b9cf-d7c65eb64cd2
ms.openlocfilehash: 32b9633a1478206bb7ee5d132754fec48925d16d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759219"
---
# <a name="compiler-error-c2238"></a>컴파일러 오류 C2238

'token' 앞에 예기치 않은 토큰이 있습니다.

잘못된 토큰이 있습니다.

다음 샘플에서는 C2238을 생성합니다.

```cpp
// C2238.cpp
// compile with: /c
class v {
virtual: int vvv;   // C2238
};
```
