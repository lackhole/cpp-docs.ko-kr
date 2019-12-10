---
title: 컴파일러 오류 C3923
ms.date: 11/04/2016
f1_keywords:
- C3923
helpviewer_keywords:
- C3923
ms.assetid: db8838e9-6344-4cd6-83e0-a8abeb12c4c0
ms.openlocfilehash: e688afcfd477ce88c437f22f864bfb97b1d2ade1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757776"
---
# <a name="compiler-error-c3923"></a>컴파일러 오류 C3923

'member': WinRT 또는 관리되는 클래스의 멤버 함수에는 지역 클래스, 구조체 또는 공용 구조체 정의를 사용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3923 오류가 발생하는 경우를 보여 줍니다.

```cpp
// C3923.cpp
// compile with: /clr /c
ref struct x {
   void Test() {
      struct a {};   // C3923
      class b {};   // C3923
      union c {};   // C3923
   }
};
```
