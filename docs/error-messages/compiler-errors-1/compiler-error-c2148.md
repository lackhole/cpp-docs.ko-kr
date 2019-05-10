---
title: 컴파일러 오류 C2148
ms.date: 11/04/2016
f1_keywords:
- C2148
helpviewer_keywords:
- C2148
ms.assetid: e510c2c9-7b57-4ce8-be03-ba363e2cc5d9
ms.openlocfilehash: 893f1f029b2ea1aaf7ff53a5ee5cee7fcbe36e7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175383"
---
# <a name="compiler-error-c2148"></a>컴파일러 오류 C2148

배열의 총 크기 0x7fffffff 바이트를 초과할 수 없습니다.

배열 한도 초과합니다. 배열의 크기를 줄입니다.

## <a name="example"></a>예제

다음 샘플에서는 C2148를 생성합니다.

```
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