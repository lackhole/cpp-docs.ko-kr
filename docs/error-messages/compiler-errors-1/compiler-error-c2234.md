---
title: 컴파일러 오류 C2234
ms.date: 11/04/2016
f1_keywords:
- C2234
helpviewer_keywords:
- C2234
ms.assetid: cfa42458-c803-4717-a017-9eca1c0cbfb0
ms.openlocfilehash: 9f13b33c9e6c56e4ec82e6542ff0869849f0f822
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759245"
---
# <a name="compiler-error-c2234"></a>컴파일러 오류 C2234

' name ': 참조 배열이 잘못 되었습니다.

참조에 대 한 포인터는 허용 되지 않으므로 참조 배열을 사용할 수 없습니다.

다음 샘플에서는 C2234를 생성 합니다.

```cpp
// C2234.cpp
int main() {
   int i = 0, j = 0, k = 0, l = 0;
   int &array[4] = {i,j,k,l};   // C2234
   int array2[4] = {i,j,k,l};   // OK
}
```
