---
title: 컴파일러 오류 C3901
ms.date: 11/04/2016
f1_keywords:
- C3901
helpviewer_keywords:
- C3901
ms.assetid: 19af4141-39ad-4c16-a68f-3ae76f648186
ms.openlocfilehash: 31fbb1e89a0619b4dc8b3f6c86f7f6bc748b80d6
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344576"
---
# <a name="compiler-error-c3901"></a>컴파일러 오류 C3901

'accessor_function': 'type' 반환 형식이 있어야 합니다.

하나 이상의 get 메서드의 반환 형식이 속성 형식과 일치 해야 합니다. 자세한 내용은 [property](../../extensions/property-cpp-component-extensions.md)을 참조하세요.

다음 샘플에서는 C3901를 생성합니다.

```
// C3901.cpp
// compile with: /clr /c
using namespace System;
ref class X {
   property String^ Name {
      void get();   // C3901
      // try the following line instead
      // String^ get();
   };
};

ref class Y {
   property double values[int, int] {
      int get(int, int);   // C3901
      // try the following line instead
      // double get(int, int);
   };
};
```