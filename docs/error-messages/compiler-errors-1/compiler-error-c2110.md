---
title: 컴파일러 오류 C2110
ms.date: 11/04/2016
f1_keywords:
- C2110
helpviewer_keywords:
- C2110
ms.assetid: 48fd76ed-90d6-4a60-9c7b-f6ce9355b4ca
ms.openlocfilehash: 91c674623624f4c156376faffd6aeae804a9308d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741198"
---
# <a name="compiler-error-c2110"></a>컴파일러 오류 C2110

'+': 두 포인터를 더할 수 없습니다.

더하기( `+` ) 연산자를 사용하여 두 포인터 값을 더하려고 했습니다.

다음 샘플에서는 C2110을 생성합니다.

```cpp
// C2110.cpp
int main() {
   int a = 0;
   int *pa;
   int *pb;
   a = pa + pb;   // C2110
}
```
