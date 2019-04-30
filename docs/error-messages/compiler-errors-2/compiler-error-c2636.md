---
title: 컴파일러 오류 C2636
ms.date: 11/04/2016
f1_keywords:
- C2636
helpviewer_keywords:
- C2636
ms.assetid: 379873ec-8d05-49f8-adf1-b067bc07bdb8
ms.openlocfilehash: f196058bf458cf0732e3a19b98df366eb046e93a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395445"
---
# <a name="compiler-error-c2636"></a>컴파일러 오류 C2636

'identifier': 참조 멤버에 대 한 포인터가 잘못 되었습니다

참조 멤버에 대 한 포인터를 선언 했습니다.

다음 샘플에서는 C2636를 생성합니다.

```
// C2636.cpp
struct S {};
int main() {
   int &S::*prs;   // C2636
   int S::*prs1;   // OK
   int *S::*prs2;   // OK
}
```