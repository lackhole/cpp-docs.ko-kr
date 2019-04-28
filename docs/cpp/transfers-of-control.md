---
title: 컨트롤 전송
ms.date: 11/04/2016
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
ms.openlocfilehash: 1fc487628f26dcac097109bc71fa960e501d0797
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266818"
---
# <a name="transfers-of-control"></a>컨트롤 전송

**goto** 문을 사용하거나 **문에서** **switchcase** 레이블을 사용하여 분기가 이니셜라이저를 지나는 프로그램을 지정할 수 있습니다. 이 같은 코드는 이니셜라이저를 포함한 선언이 점프 명령문이 있는 블록이 둘러싼 블록에 없는 경우 올바르지 않습니다.

다음 예제에서는 `total`, `ch` 및 `i` 개체를 선언하고 초기화하는 루프를 보여 줍니다. 또한 이니셜라이저를 지나 컨트롤을 전송하는 잘못된 **goto** 문이 있습니다.

```cpp
// transfers_of_control.cpp
// compile with: /W1
// Read input until a nonnumeric character is entered.
int main()
{
   char MyArray[5] = {'2','2','a','c'};
   int i = 0;
   while( 1 )
   {
      int total = 0;

      char ch = MyArray[i++];

      if ( ch >= '0' && ch <= '9' )
      {
         goto Label1;

         int i = ch - '0';
      Label1:
         total += i;   // C4700: transfers past initialization of i.
      } // i would be destroyed here if  goto error were not present
   else
      // Break statement transfers control out of loop,
      //  destroying total and ch.
      break;
   }
}
```

위의 예제에서 **goto** 문은 `i`의 초기화를 지나 컨트롤을 전송합니다. 단, `i`가 선언되었지만 초기화되지 않은 경우 전송은 유효합니다.

`total` 문의 `ch` *statement* 역할을 하는 블록 안에서 선언된 개체 및 **while** 문은 해당 블록이 **break** 문을 사용하여 종료되는 경우 삭제됩니다.