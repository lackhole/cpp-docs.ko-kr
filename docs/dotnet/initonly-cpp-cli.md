---
title: initonly(C++/CLI)
ms.date: 11/04/2016
f1_keywords:
- initonly_cpp
- initonly
helpviewer_keywords:
- initonly attribute [C++]
ms.assetid: f745d7fa-dc08-46f1-9b97-0977be58a008
ms.openlocfilehash: cdfc278225ce4ab418dfaaf41fb413d088ad77df
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58766576"
---
# <a name="initonly-ccli"></a>initonly(C++/CLI)

**initonly** 해당 변수 할당을 표시 하는 상황에 맞는 키워드는 선언 또는 동일한 클래스의 정적 생성자에서의 일부로 서만 발생할 수 있습니다.

다음 예제에서는 `initionly`을 사용하는 방법을 보여 줍니다.

```
// mcpp_initonly.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst1;

   initonly
   static int staticConst2 = 0;

   static Y1() {
      staticConst1 = 0;
   }
};
```

## <a name="see-also"></a>참고자료

[클래스 및 구조체(C++)](../extensions/classes-and-structs-cpp-component-extensions.md)
