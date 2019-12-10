---
title: 컴파일러 오류 C2087
ms.date: 11/04/2016
f1_keywords:
- C2087
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
ms.openlocfilehash: 576ac394585b91f7c6ceadcdd07d25c639854990
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757906"
---
# <a name="compiler-error-c2087"></a>컴파일러 오류 C2087

' identifier ': 첨자가 없습니다.

여러 첨자가 있는 배열의 정의에 1 보다 큰 차원에 대 한 첨자 값이 누락 되었습니다.

다음 샘플에서는 C2087를 생성 합니다.

```cpp
// C2087.cpp
int main() {
   char a[10][];   // C2087
}
```

가능한 해결 방법:

```cpp
// C2087b.cpp
int main() {
   char b[4][5];
}
```
