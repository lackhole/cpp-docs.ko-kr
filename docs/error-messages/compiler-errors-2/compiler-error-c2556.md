---
title: 컴파일러 오류 C2556
ms.date: 11/04/2016
f1_keywords:
- C2556
helpviewer_keywords:
- C2556
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
ms.openlocfilehash: 4a2b4dc9dcd71d518845651dee97c566b778eb0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353068"
---
# <a name="compiler-error-c2556"></a>컴파일러 오류 C2556

'identifier': 오버 로드 된 함수 반환 형식에 따라 다릅니다

오버 로드 된 함수에 동일한 매개 변수 목록 이지만 다른 반환 형식이 있습니다. 각 오버 로드 된 함수는 고유한 형식 매개 변수 목록이 있어야 합니다.

다음 샘플에서는 C2556 오류가 생성 됩니다.

```
// C2556.cpp
// compile with: /c
class C {
   int func();
   double func();   // C2556
   int func(int i);   // ok parameter lists differ
};
```