---
title: 컴파일러 오류 C2333
ms.date: 11/04/2016
f1_keywords:
- C2333
helpviewer_keywords:
- C2333
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
ms.openlocfilehash: cca7f0d3bd75cca8fdd621fb425dec42e6560f4e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747750"
---
# <a name="compiler-error-c2333"></a>컴파일러 오류 C2333

' function ': 함수 선언에 오류가 있습니다. 함수 본문을 건너뛰는 중

이 오류는 해당 클래스 내에 정의 된 멤버 함수에 대해 다른 오류 후에 발생 합니다.

다음 샘플에서는 C2333를 생성 합니다.

```cpp
// C2333.cpp
struct s1 {
   s1(s1) {}   // C2333
};
```
