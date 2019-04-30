---
title: 컴파일러 오류 C3902
ms.date: 11/04/2016
f1_keywords:
- C3902
helpviewer_keywords:
- C3902
ms.assetid: feb3bb29-f836-4d77-ba71-3876f7f4f216
ms.openlocfilehash: d90bf299c566ce72e3d1cbfeb545def0a43d6cbf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375992"
---
# <a name="compiler-error-c3902"></a>컴파일러 오류 C3902

'accessor': 마지막 매개 변수의 형식은 '형식' 이어야 합니다.

하나 이상의 집합 메서드의 마지막 매개 변수 형식의 속성의 형식과 일치 해야 합니다. 자세한 내용은 [property](../../extensions/property-cpp-component-extensions.md)을 참조하세요.

다음 샘플에서는 C3902 오류가 생성 됩니다.

```
// C3902.cpp
// compile with: /clr /c
using namespace System;
ref class X {
   property String ^Name {
      void set(int);   // C3902
      // try the following line instead
      // void set(String^){}
   }

   property double values[int,int] {
      void set(int, int, float);   // C3902
      // try the following line instead
      // void set(int, int, double){}
   }
};
```