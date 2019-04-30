---
title: 컴파일러 오류 C3155
ms.date: 11/04/2016
f1_keywords:
- C3155
helpviewer_keywords:
- C3155
ms.assetid: b04a42e1-64e7-40f8-81fe-c7945348b2cf
ms.openlocfilehash: 85ee53dff7ae50717eabfd1ac6504ebb74deaa2d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374848"
---
# <a name="compiler-error-c3155"></a>컴파일러 오류 C3155

속성 인덱서에 특성이 허용 되지 않습니다.

인덱싱된 속성을 잘못 선언 되었습니다. 자세한 내용은 [방법: 속성에서 사용 하 여 C++/CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3155 오류가 발생 합니다.

```
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