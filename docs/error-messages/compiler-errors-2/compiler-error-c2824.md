---
title: 컴파일러 오류 C2824
ms.date: 11/04/2016
f1_keywords:
- C2824
helpviewer_keywords:
- C2824
ms.assetid: 5bd865f7-e0af-404e-80fe-e2b798b44a59
ms.openlocfilehash: ee012d7244079fd881210eb969f4844a2c6e85d8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750639"
---
# <a name="compiler-error-c2824"></a>컴파일러 오류 C2824

' operator n e w '의 반환 형식은 ' void * ' 여야 합니다.

기반이 아닌 포인터를 사용 하는 경우 `new` 연산자의 오버 로드는 `void *`을 반환 해야 합니다.

다음 샘플에서는 C2824를 생성 합니다.

```cpp
// C2824.cpp
// compile with: /c
class   A {
   A* operator new(size_t i, char *m);   // C2824
   // try the following line instead
   // void* operator new(size_t i, char *m);
};
```
