---
title: 컴파일러 오류 C2762
ms.date: 11/04/2016
f1_keywords:
- C2762
helpviewer_keywords:
- C2762
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
ms.openlocfilehash: c2f325fc9266321f224429afd3c295141627ecd6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759856"
---
# <a name="compiler-error-c2762"></a>컴파일러 오류 C2762

' class ': ' argument '의 템플릿 인수로 잘못 된 식입니다.

[/Za](../../build/reference/za-ze-disable-language-extensions.md)를 사용 하는 경우 컴파일러는 정수를 포인터로 변환 하지 않습니다.

다음 샘플에서는 C2762를 생성 합니다.

```cpp
// C2762.cpp
// compile with: /Za
template<typename T, T *pT>
class X2 {};

void f2() {
   X2<int, 0> x21;   // C2762
   // try the following line instead
   // X2<int, static_cast<int *>(0)> x22;
}
```
