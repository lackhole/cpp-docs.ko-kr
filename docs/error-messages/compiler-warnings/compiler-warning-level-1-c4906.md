---
title: 컴파일러 경고(수준 1) C4906
ms.date: 11/04/2016
f1_keywords:
- C4906
helpviewer_keywords:
- C4906
ms.assetid: 05318e74-799b-412a-9dce-f02b8161d762
ms.openlocfilehash: a62b10ca96dc9c27e57eafdcc87cf0d5e0605b4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380554"
---
# <a name="compiler-warning-level-1-c4906"></a>컴파일러 경고(수준 1) C4906

문자열 리터럴을 'LPWSTR'로 캐스팅했습니다.

컴파일러는 안전 하지 않은 캐스트를 발견 했습니다. 캐스트가 성공 했지만 있지만 변환 루틴을 사용 해야 합니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4906 오류가 생성 됩니다.

```
// C4906.cpp
// compile with: /W1
#pragma warning(default : 4906)
#include <windows.h>
#include <stdlib.h>
#include <stdio.h>

int main()
{
    LPWSTR x = (LPWSTR)"1234";   // C4906

    // try the following lines instead
    // char y[128];
    // size_t numberOfCharConverted = 0;
    // errcode err = 0;
    // err = wcstombs_s(&numberOfCharConverted , &y[0], 128,
    //                  L"12345", 4);
    // if (err != 0)
    // {
    //     printf_s("wcstombs_s failed!");
    //     return -1;
    // }
    // printf_s("%s\n", y);

    return 0;
}
```