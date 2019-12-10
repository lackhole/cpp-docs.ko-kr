---
title: 컴파일러 오류 C3155
ms.date: 11/04/2016
f1_keywords:
- C3155
helpviewer_keywords:
- C3155
ms.assetid: b04a42e1-64e7-40f8-81fe-c7945348b2cf
ms.openlocfilehash: ccbe96075a22ef67d7ebd1f2998b42820bbc79f9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745904"
---
# <a name="compiler-error-c3155"></a>컴파일러 오류 C3155

속성 인덱서에는 특성을 사용할 수 없습니다.

인덱싱된 속성이 잘못 선언 되었습니다. 자세한 내용은 [방법:/cli에서 C++속성 사용](../../dotnet/how-to-use-properties-in-cpp-cli.md)을 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3155를 생성 합니다.

```cpp
// C3155.cpp
// compile with: /clr /c
using namespace System;
ref struct R {
   property int F[[ParamArray] int] {   // C3155
   // try the following line instead
   // property int F[ int] {   // OK
      int get(int i) {
         return 0;
      }
   }
};
```
