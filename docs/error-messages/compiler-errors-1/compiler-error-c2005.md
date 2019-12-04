---
title: 컴파일러 오류 C2005
ms.date: 11/04/2016
f1_keywords:
- C2005
helpviewer_keywords:
- C2005
ms.assetid: 090530ed-e0ec-4358-833a-ca24260e7ffe
ms.openlocfilehash: ff998beaa1d954f05a07d8ccf1b59cec0f4e3958
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737480"
---
# <a name="compiler-error-c2005"></a>컴파일러 오류 C2005

\#줄에 줄 번호가 있어야 하는데 ' token '이 있습니다.

`#line` 지시문 뒤에는 줄 번호가와 야 합니다.

다음 샘플에서는 C2005를 생성 합니다.

```cpp
// C2005.cpp
int main() {
   int i = 0;
   #line i   // C2005
}
```

가능한 해결 방법:

```cpp
// C2005b.cpp
int main() {
   int i = 0;
   #line 0
}
```
