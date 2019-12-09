---
title: 컴파일러 오류 C2777
ms.date: 11/04/2016
f1_keywords:
- C2777
helpviewer_keywords:
- C2777
ms.assetid: 5fe158c0-2a65-488a-aca2-61d4a8b32d43
ms.openlocfilehash: 67132f0acbee3614d8032685ae454386d97b8fb1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740015"
---
# <a name="compiler-error-c2777"></a>컴파일러 오류 C2777

속성 당 ' put ' 메서드를 하나만 지정할 수 있습니다.

Declspec 한정자 [속성](../../cpp/property-cpp.md) 에 `put` 속성이 둘 이상 있습니다.

다음 샘플에서는 C2777를 생성 합니다.

```cpp
// C2777.cpp
struct A {
   __declspec(property(put=PutProp,put=PutPropToo))   // C2777
   // try the following line instead
   // __declspec(property(put=PutProp))
      int prop;
   int PutProp(void);
   int PutPropToo(void);
};
```
