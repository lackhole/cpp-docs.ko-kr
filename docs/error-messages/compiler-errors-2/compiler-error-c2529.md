---
title: 컴파일러 오류 C2529
ms.date: 11/04/2016
f1_keywords:
- C2529
helpviewer_keywords:
- C2529
ms.assetid: 73a99e55-b91e-488d-9b72-cc80faaeb436
ms.openlocfilehash: b634f2369805114209860f5e304a7cd2cca2ec91
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266455"
---
# <a name="compiler-error-c2529"></a>컴파일러 오류 C2529

'name': 참조에 대 한 참조가 잘못 되었습니다.

포인터에 대 한 참조를 선언 하는 포인터 구문을 사용 하 여이 오류를 해결할 수 있습니다.

다음 샘플에서는 C2529 오류가 생성 됩니다.

```
// C2529.cpp
// compile with: /c
int i;
int &ri = i;
int &(&rri) = ri;   // C2529
```