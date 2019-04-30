---
title: while 문 (C++)
ms.date: 11/04/2016
f1_keywords:
- while_cpp
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
ms.openlocfilehash: 669618e9807109be18117968b1f5b6f49ec15e07
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325418"
---
# <a name="while-statement-c"></a>while 문 (C++)

*표현식(expression)* 이 0이 될 때까지 *명령문(statement)* 을 반복 실행합니다.

## <a name="syntax"></a>구문

```
while ( expression )
   statement
```

## <a name="remarks"></a>설명

*표현식*의 실행은 루프가 실행되기 전에 수행됩니다. 따라서 **while** 루프는 0번 이상 실행됩니다. *표현식*은 정수 형식, 포인터 형식이나 정수 또는 포인터 유형으로의 모호하지 않은 변환이 되는 클래스 형식이어야 합니다.

**while** 루프는 명령문 본문 내에서 [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md)나 [return](../cpp/return-statement-cpp.md)이 실행될 때 종료 될 수도 있습니다. [continue](../cpp/continue-statement-cpp.md)를 사용하여 **while** 루프를 종료하지 않고 현재의 반복을 종료합니다. **continue**를 만나면 제어가 **while** 루프의 다음 반복으로 계속됩니다.

다음 코드는 **while** 루프를 사용하여 문자열에서 뒷부분의 밑줄을 잘라냅니다.

```cpp
// while_statement.cpp

#include <string.h>
#include <stdio.h>
char *trim( char *szSource )
{
    char *pszEOS = 0;

    //  Set pointer to character before terminating NULL
    pszEOS = szSource + strlen( szSource ) - 1;

    //  iterate backwards until non '_' is found
    while( (pszEOS >= szSource) && (*pszEOS == '_') )
        *pszEOS-- = '\0';

    return szSource;
}
int main()
{
    char szbuf[] = "12345_____";

    printf_s("\nBefore trim: %s", szbuf);
    printf_s("\nAfter trim: %s\n", trim(szbuf));
}
```

종료 조건은 루프의 맨 위에서 평가됩니다. 문자열 뒷부분에 밑줄이 없다면 루프는 실행되지 않습니다.

## <a name="see-also"></a>참고자료

[반복 문](../cpp/iteration-statements-cpp.md)<br/>
[키워드](../cpp/keywords-cpp.md)<br/>
[do-while 문(C++)](../cpp/do-while-statement-cpp.md)<br/>
[for 문(C++)](../cpp/for-statement-cpp.md)<br/>
[범위 기반 for 문(C++)](../cpp/range-based-for-statement-cpp.md)