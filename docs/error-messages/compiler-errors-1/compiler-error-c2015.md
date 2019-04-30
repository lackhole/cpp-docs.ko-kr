---
title: 컴파일러 오류 C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: d761dfde26cce9c99ccd4c3e6fd86ae1d6e16ddc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351094"
---
# <a name="compiler-error-c2015"></a>컴파일러 오류 C2015

상수 문자가 너무 많습니다.

문자 상수에는 두 개 이상의 문자가 들어 있습니다. 표준 문자 상수에 대해 문자 하나 및 긴 문자 상수에 대 한 두 개의 문자도 제한이 됩니다.

예: \t 이스케이프 시퀀스를 하나의 문자로 변환 됩니다.

## <a name="example"></a>예제

다음 샘플에서는 C2015 오류가 생성 됩니다.

```
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

## <a name="example"></a>예제

C2015는 Microsoft 확장을 정수로 변환 하는 문자 상수를 사용 하는 경우에 발생할 수 있습니다.  다음 샘플에서는 C2015 오류가 생성 됩니다.

```
// C2015b.cpp
#include <stdio.h>

int main()
{
    int a = 'abcde';   // C2015

    int b = 'a';   // 'a' = ascii 0x61
    printf_s("%x\n", b);
}
```