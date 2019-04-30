---
title: 컴파일러 오류 C2118
ms.date: 11/04/2016
f1_keywords:
- C2118
helpviewer_keywords:
- C2118
ms.assetid: bf4315d0-f085-4323-b813-96ee61a13bde
ms.openlocfilehash: 71b8273aaee52420f8a9c9c2dd2d015bea72ddf6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338911"
---
# <a name="compiler-error-c2118"></a>컴파일러 오류 C2118

첨자가 음수.

배열 크기를 정의 하는 값이 최대 배열 크기 보다 크거나 0 보다 작은 경우

다음 샘플에서는 C2118 오류가 생성 됩니다.

```
// C2118.cpp
int main() {
   int array1[-1];   // C2118
   int array2[3];   // OK
}
```