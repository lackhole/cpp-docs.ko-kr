---
title: 컴파일러 오류 C3626
ms.date: 11/04/2016
f1_keywords:
- C3626
helpviewer_keywords:
- C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
ms.openlocfilehash: d0360b16c2e59bd01c3a5dd4be9c49b578b9c45b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221809"
---
# <a name="compiler-error-c3626"></a>컴파일러 오류 C3626

'keyword': '__event' 키워드는 COM 인터페이스, 멤버 함수 및 대리자에 대 한 포인터는 데이터 멤버에만 사용할 수 있습니다

키워드를 잘못 사용 했습니다.

다음 샘플에서는 C3626를 생성합니다.

```
// C3626.cpp
// compile with: /c
struct A {
   __event int i;   // C3626
// try the following line instead
// __event int i();
};
```