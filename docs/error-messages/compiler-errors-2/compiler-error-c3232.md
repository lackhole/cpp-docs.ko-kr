---
title: 컴파일러 오류 C3232
ms.date: 11/04/2016
f1_keywords:
- C3232
helpviewer_keywords:
- C3232
ms.assetid: 3119b3a9-0eff-4a3f-b805-e4d160af9e39
ms.openlocfilehash: e0668cb66bf8e9fa6431b6f238167d594cd00416
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750314"
---
# <a name="compiler-error-c3232"></a>컴파일러 오류 C3232

'param': 정규화된 이름에는 제네릭 형식 매개 변수를 사용할 수 없습니다.

제네릭 형식 매개 변수가 잘못 사용되었습니다.

다음 샘플에서는 C3232를 생성합니다.

```cpp
// C3232.cpp
// compile with: /clr
generic <class T>
ref class C {
   typename T::TYPE t;   // C3232
};
```
