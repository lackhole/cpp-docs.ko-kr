---
title: 컴파일러 경고 (수준 3) C4995
ms.date: 11/04/2016
f1_keywords:
- C4995
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
ms.openlocfilehash: 4c31023fbcb36c53a7d0f5138c280ff12c4d495e
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541173"
---
# <a name="compiler-warning-level-3-c4995"></a>컴파일러 경고 (수준 3) C4995

' function ': 이름이 #pragma 사용 되지 않는 것으로 표시 되었습니다.

컴파일러가 pragma를 [사용 하지 않는](../../preprocessor/deprecated-c-cpp.md)것으로 표시 된 함수를 발견 했습니다. 이 함수는 이후 릴리스에서 제공되지 않을 수 있습니다. [경고](../../preprocessor/warning.md) pragma (아래 예제)를 사용 하 여이 경고를 해제할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4995를 생성 합니다.

```cpp
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