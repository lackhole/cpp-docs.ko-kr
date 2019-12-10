---
title: 컴파일러 오류 C2735
ms.date: 11/04/2016
f1_keywords:
- C2735
helpviewer_keywords:
- C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
ms.openlocfilehash: 81ae9353709ddb5ab0d878e6dc157511d95a94fd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755761"
---
# <a name="compiler-error-c2735"></a>컴파일러 오류 C2735

' keyword ' 키워드는 정식 매개 변수 형식 지정자에 사용할 수 없습니다.

이 컨텍스트에서는 키워드를 사용할 수 없습니다.

다음 샘플에서는 C2735를 생성 합니다.

```cpp
// C2735.cpp
void f(inline int){}   // C2735
```
