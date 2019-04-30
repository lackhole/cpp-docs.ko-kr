---
title: 컴파일러 오류 C2624
ms.date: 11/04/2016
f1_keywords:
- C2624
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
ms.openlocfilehash: 407629ad2eecd0d3ca6081fefa59ddd60702f913
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395484"
---
# <a name="compiler-error-c2624"></a>컴파일러 오류 C2624

'extern' 변수를 선언 하는 로컬 클래스를 사용할 수 없습니다.

로컬 클래스 또는 구조체 선언에 사용할 수 없습니다 `extern` 변수입니다.

다음 샘플에서는 C2624를 생성합니다.

```
// C2624.cpp
int main() {
   struct C {};
   extern C ac;   // C2624
}
```