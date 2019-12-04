---
title: 컴파일러 오류 C3083
ms.date: 11/04/2016
f1_keywords:
- C3083
helpviewer_keywords:
- C3083
ms.assetid: 05ff791d-52bb-41eb-9511-3ef89d7f4710
ms.openlocfilehash: ee4a2bc683a757e079295c16d1022739eaa5726c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759713"
---
# <a name="compiler-error-c3083"></a>컴파일러 오류 C3083

' function ': ':: '의 왼쪽에 있는 기호는 형식 이어야 합니다.

함수를 잘못 호출 했습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3083를 생성 합니다.

```cpp
// C3083.cpp
// compile with: /c
struct N {
   ~N();
};

struct N1 {
   ~N1();
};

N::N::~N() {}   // C3083
N1::~N1() {}   // OK
```
