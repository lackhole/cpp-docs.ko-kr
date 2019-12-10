---
title: 컴파일러 오류 C2470
ms.date: 11/04/2016
f1_keywords:
- C2470
helpviewer_keywords:
- C2470
ms.assetid: e17d2cb8-b84c-447c-976a-625f0c96f3fe
ms.openlocfilehash: 0f81ba26f346508c0178a99c537206762476b7cb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743746"
---
# <a name="compiler-error-c2470"></a>컴파일러 오류 C2470

' function ': 함수 정의 처럼 보이지만 매개 변수 목록이 없습니다. 명백한 본문을 건너뛰고 있습니다.

함수 정의에 인수 목록이 없습니다.

다음 샘플에서는 C2470를 생성 합니다.

```cpp
// C2470.cpp
int MyFunc {};  // C2470
void MyFunc2() {};  //OK

int main(){
   MyFunc();
   MyFunc2();
}
```
