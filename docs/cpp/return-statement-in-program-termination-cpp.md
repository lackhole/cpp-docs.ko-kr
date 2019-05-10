---
title: 프로그램 종료 시 return 문 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
ms.openlocfilehash: 9c7b6130ee1a0b49ab75a70d84764d3a1f8c5ef0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267615"
---
# <a name="return-statement-in-program-termination-c"></a>프로그램 종료 시 return 문 (C++)

`main`에서 **return** 문을 실행하는 것은 `exit` 함수를 호출하는 것과 기능적으로 동일합니다. 다음 예제를 참조하십시오.

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

위의 예제에서 `exit` 및 **return** 문은 기능적으로 동일합니다. 그러나 C++에서는 **void**가 아닌 반환 형식을 가지는 함수가 값을 반환해야 합니다. **return** 문을 사용하면 `main`에서 값을 반환할 수 있습니다.

## <a name="see-also"></a>참고 항목

[프로그램 종료](../cpp/program-termination.md)