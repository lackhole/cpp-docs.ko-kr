---
title: 컴파일러 오류 C2793
ms.date: 11/04/2016
f1_keywords:
- C2793
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
ms.openlocfilehash: 5b8712473631b16e2bbb47430966ccc0c552b9df
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739391"
---
# <a name="compiler-error-c2793"></a>컴파일러 오류 C2793

' token ': ':: ', 식별자 또는 ' operator ' 키워드 뒤에 예기치 않은 토큰이 필요 합니다.

`__super::` 따를 수 있는 토큰은 식별자 또는 키워드 `operator`뿐입니다.

다음 샘플에서는 C2793를 생성 합니다.

```cpp
// C2793.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::(); // C2793
   }
};
```
