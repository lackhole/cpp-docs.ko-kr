---
title: 컴파일러 오류 C3769
ms.date: 11/04/2016
f1_keywords:
- C3769
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
ms.openlocfilehash: 03f51ae589c56b28eb7a1484669d5982cd8f5dcb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757191"
---
# <a name="compiler-error-c3769"></a>컴파일러 오류 C3769

' type ': 중첩 된 클래스는 바로 바깥쪽 클래스와 같은 이름을 사용할 수 없습니다.

중첩 된 클래스는 바로 바깥쪽 클래스와 동일한 이름을 사용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3769를 생성 합니다.

```cpp
// C3769.cpp
// compile with: /c
class x {
   class x {};   // C3769
   class y {
      class x{};   // OK
   };
};
```
