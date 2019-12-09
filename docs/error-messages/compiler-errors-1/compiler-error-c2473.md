---
title: 컴파일러 오류 C2473
ms.date: 11/04/2016
f1_keywords:
- C2473
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
ms.openlocfilehash: 2f7ce0e18070c2b5ee6ebb2284d5564b3d750d77
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743720"
---
# <a name="compiler-error-c2473"></a>컴파일러 오류 C2473

'identifier': 함수 정의로 보이지만 매개 변수 목록이 없습니다.

컴파일러가 매개 변수 목록 없이 함수처럼 보이는 항목을 발견했습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2473을 생성합니다.

```cpp
// C2473.cpp
// compile with: /clr /c
class A {
   int i {}   // C2473
};

class B {
   int i() {}   // OK
};
```
