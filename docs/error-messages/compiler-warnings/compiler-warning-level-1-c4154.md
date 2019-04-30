---
title: 컴파일러 경고 (수준 1) C4154
ms.date: 11/04/2016
f1_keywords:
- C4154
helpviewer_keywords:
- C4154
ms.assetid: 4511afeb-e893-4cc6-83b6-4c7a0477f76b
ms.openlocfilehash: 5d2d6316838e8f3ef4acdf60494a0450a5efbdbe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324560"
---
# <a name="compiler-warning-level-1-c4154"></a>컴파일러 경고 (수준 1) C4154

배열 식 삭제 제공 된 포인터 변환

사용할 수 없습니다 `delete` 배열에 있으므로 컴파일러는 배열 포인터로 변환 합니다.

## <a name="example"></a>예제

```
// C4154.cpp
// compile with: /c /W1
int main() {
   int array[ 10 ];
   delete array;   // C4154 can't delete stack object

   int *parray2 = new int [10];
   int (&array2)[10] = (int(&)[10]) parray2;
   delete [] array2;   // C4154

   // try the following line instead
   delete [] &array2;
}
```