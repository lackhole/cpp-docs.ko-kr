---
title: 컴파일러 오류 C2148
ms.date: 11/04/2016
f1_keywords:
- C2148
helpviewer_keywords:
- C2148
ms.assetid: e510c2c9-7b57-4ce8-be03-ba363e2cc5d9
ms.openlocfilehash: aac14024e7ed2942eaf80c45817ba9c208e7e1ce
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756502"
---
# <a name="compiler-error-c2148"></a>컴파일러 오류 C2148

배열의 전체 크기는 0x7fffffff 바이트를 초과할 수 없습니다.

배열이 제한을 초과 하는 경우 배열의 크기를 줄입니다.

## <a name="example"></a>예제

다음 샘플에서는 C2148를 생성 합니다.

```cpp
// C2148.cpp
#include <stdio.h>
#include <stdlib.h>

int main( ) {
   char MyArray[0x7ffffffff];   // C2148
   char * MyArray2 = (char *)malloc(0x7fffffff);

   if (MyArray2)
      printf_s("It worked!");
   else
      printf_s("It didn't work.");
}
```
