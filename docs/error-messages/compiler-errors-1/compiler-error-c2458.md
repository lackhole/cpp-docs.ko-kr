---
title: 컴파일러 오류 C2458
ms.date: 11/04/2016
f1_keywords:
- C2458
helpviewer_keywords:
- C2458
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
ms.openlocfilehash: 93e0159ca680b37aed2031c6e2ec41463e7e389d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744006"
---
# <a name="compiler-error-c2458"></a>컴파일러 오류 C2458

' identifier ': 정의 내에서 재정의 합니다.

클래스, 구조체, 공용 구조체 또는 열거형은 자체 선언에서 다시 정의 됩니다.

다음 샘플에서는 C2458를 생성 합니다.

```cpp
// C2458.cpp
class C {
   enum i { C };   // C2458
};
```
