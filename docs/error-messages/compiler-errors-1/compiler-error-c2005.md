---
title: 컴파일러 오류 C2005
ms.date: 11/04/2016
f1_keywords:
- C2005
helpviewer_keywords:
- C2005
ms.assetid: 090530ed-e0ec-4358-833a-ca24260e7ffe
ms.openlocfilehash: 49d0375d5733410d728797d2a881075377b33ba6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209005"
---
# <a name="compiler-error-c2005"></a>컴파일러 오류 C2005

\#줄 'token' 찾을 줄 번호 필요

`#line` 지시문 뒤에 줄 번호와 합니다.

다음 샘플에서는 C2005 오류가 생성 됩니다.

```
// C2005.cpp
int main() {
   int i = 0;
   #line i   // C2005
}
```

해결 방법:

```
// C2005b.cpp
int main() {
   int i = 0;
   #line 0
}
```