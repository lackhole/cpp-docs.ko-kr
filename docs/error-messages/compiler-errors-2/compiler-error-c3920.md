---
title: 컴파일러 오류 C3920
ms.date: 11/04/2016
f1_keywords:
- C3920
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
ms.openlocfilehash: d7163cf07a440a0afd1216b3e5cf665326ffb963
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386605"
---
# <a name="compiler-error-c3920"></a>컴파일러 오류 C3920

' operator ': 후 위 증가/감소 WinRT 또는 CLR 연산자는 후 위를 정의할 수 없습니다 WinRT 또는 CLR 연산자는 해당 접두사를 호출 하는 후 위 의미 체계를 사용 하 여 WinRT 또는 CLR 연산자 (op_Increment/op_Decrement)가 있지만

Windows 런타임 및 CLR은 후위 연산자를 지원하지 않으며, 사용자 정의 후위 연산자는 허용되지 않습니다.  전위 연산자를 정의할 수 있으며, 그러면 전위 연산자가 전위 증가 작업 및 후위 증가 작업에 모두 사용됩니다.

다음 샘플에서는 C3920 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C3920.cpp
// compile with: /clr /LD
public value struct V {
   static V operator ++(V me, int)
   // try the following line instead
   // static V operator ++(V me)
   {   // C3920
      me.m_i++;
      return me;
   }

   int m_i;
};
```