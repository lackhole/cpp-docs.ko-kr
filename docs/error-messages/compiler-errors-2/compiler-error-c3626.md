---
title: 컴파일러 오류 C3626
ms.date: 11/04/2016
f1_keywords:
- C3626
helpviewer_keywords:
- C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
ms.openlocfilehash: 7d86f0f650f6a13ac764497d6d5b52f001f5c35d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757672"
---
# <a name="compiler-error-c3626"></a>컴파일러 오류 C3626

' keyword ': ' __event ' 키워드는 대리자에 대 한 포인터인 COM 인터페이스, 멤버 함수 및 데이터 멤버에만 사용할 수 있습니다.

키워드를 잘못 사용 했습니다.

다음 샘플에서는 C3626를 생성 합니다.

```cpp
// C3626.cpp
// compile with: /c
struct A {
   __event int i;   // C3626
// try the following line instead
// __event int i();
};
```
