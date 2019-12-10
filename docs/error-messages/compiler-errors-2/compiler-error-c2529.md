---
title: 컴파일러 오류 C2529
ms.date: 11/04/2016
f1_keywords:
- C2529
helpviewer_keywords:
- C2529
ms.assetid: 73a99e55-b91e-488d-9b72-cc80faaeb436
ms.openlocfilehash: f5a10131fe03bd98078e87f71d07bf02c51d34f4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760415"
---
# <a name="compiler-error-c2529"></a>컴파일러 오류 C2529

' name ': 참조에 대 한 참조가 잘못 되었습니다.

포인터 구문을 사용 하 고 포인터에 대 한 참조를 선언 하 여이 오류를 해결할 수 있습니다.

다음 샘플에서는 C2529를 생성 합니다.

```cpp
// C2529.cpp
// compile with: /c
int i;
int &ri = i;
int &(&rri) = ri;   // C2529
```
