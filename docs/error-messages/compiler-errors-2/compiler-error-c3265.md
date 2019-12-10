---
title: 컴파일러 오류 C3265
ms.date: 11/04/2016
f1_keywords:
- C3265
helpviewer_keywords:
- C3265
ms.assetid: 10ab3e17-4a9f-4120-bab5-21473869b70f
ms.openlocfilehash: 633089115fe7edd0bdf06cdbcda6909ae7ac656e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754162"
---
# <a name="compiler-error-c3265"></a>컴파일러 오류 C3265

관리 되지 않는 ' 관리 되는 구문 '은 관리 되지 않는 ' 관리 되지 않는 구문 '에서 선언할 수 없습니다.

관리 되지 않는 컨텍스트에는 관리 되는 개체를 포함할 수 없습니다.

재현 C3265 샘플은 다음과 같습니다.

```cpp
// C3265_2.cpp
// compile with: /clr /LD
#include <vcclr.h>

ref class A { };

class B
// try the following line instead
// ref class B
{
   A ^a;   // C3265
   // or embed the managed handle using gcroot
   // try the following line instead
   // gcroot<A^> a;
};
```
