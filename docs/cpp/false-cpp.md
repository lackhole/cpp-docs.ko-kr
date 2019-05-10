---
title: false (C++)
ms.date: 11/04/2016
f1_keywords:
- false_cpp
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
ms.openlocfilehash: 5fc27c7f1dfde7d1f686f0a752652773ade9cc0e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183728"
---
# <a name="false-c"></a>false (C++)

이 키워드는 [bool](../cpp/bool-cpp.md) 형식의 변수나 조건식(조건식은 이제 **true** 부울 식임)에 대한 두 값 중 하나입니다. 예를 들어 `i`가 **bool** 형식의 변수인 경우 `i = false;` 문은 **false**를 `i`에 할당합니다.

## <a name="example"></a>예제

```cpp
// bool_false.cpp
#include <stdio.h>

int main()
{
    bool bb = true;
    printf_s("%d\n", bb);
    bb = false;
    printf_s("%d\n", bb);
}
```

```Output
1
0
```

## <a name="see-also"></a>참고자료

[C++ 키워드](../cpp/keywords-cpp.md)