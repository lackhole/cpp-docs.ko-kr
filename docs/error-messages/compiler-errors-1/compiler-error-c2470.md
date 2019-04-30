---
title: 컴파일러 오류 C2470
ms.date: 11/04/2016
f1_keywords:
- C2470
helpviewer_keywords:
- C2470
ms.assetid: e17d2cb8-b84c-447c-976a-625f0c96f3fe
ms.openlocfilehash: 2a4f8c8052081fe90801dfeb30d942fbb9a91a01
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303114"
---
# <a name="compiler-error-c2470"></a>컴파일러 오류 C2470

'function': 함수 정의 보이지만 매개 변수 목록이 없습니다. 명백한 본문을 건너뜁니다.

함수 정의 인수 목록이 없습니다.

다음 샘플에서는 C2470 오류가 생성 됩니다.

```
// C2470.cpp
int MyFunc {};  // C2470
void MyFunc2() {};  //OK

int main(){
   MyFunc();
   MyFunc2();
}
```