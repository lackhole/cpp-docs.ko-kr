---
title: 컴파일러 경고 (수준 3) C4995
ms.date: 11/04/2016
f1_keywords:
- C4995
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
ms.openlocfilehash: 54bc8931b5eaa3bbb5053e5c21aa2aaaa73126fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401516"
---
# <a name="compiler-warning-level-3-c4995"></a>컴파일러 경고 (수준 3) C4995

'function': 사용 되지 않는 #pragma로 표시 되어 이름

컴파일러가 pragma를 사용 하 여 표시 된 함수를 발견 했습니다 [사용 되지 않는](../../preprocessor/deprecated-c-cpp.md)합니다. 이 함수는 이후 릴리스에서 제공되지 않을 수 있습니다. 이 경고를 사용 하 여 해제 해제할 수 있습니다 합니다 [경고](../../preprocessor/warning.md) pragma (아래 예제).

## <a name="example"></a>예제

다음 샘플에서는 C4995 오류가 생성 됩니다.

```
// C4995.cpp
// compile with: /W3
#include <stdio.h>

// #pragma warning(disable : 4995)
void func1(void)
{
    printf("\nIn func1");
}

int main()
{
    func1();
    #pragma deprecated(func1)
    func1();   // C4995
}
```