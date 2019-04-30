---
title: true (C++)
ms.date: 11/04/2016
f1_keywords:
- true_cpp
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
ms.openlocfilehash: 5cfc99f446499201a0f54c8e5b1dcc2d7152445c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404704"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>구문

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>설명

이 키워드는 [bool](../cpp/bool-cpp.md) 형식의 변수 또는 조건식의 값 2개 중 하나입니다. 이제 조건식이 부울 식입니다. `i`가 **bool** 형식이면 `i = true;`문이 `i`에 **true**를 할당합니다.

## <a name="example"></a>예제

```cpp
// bool_true.cpp
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