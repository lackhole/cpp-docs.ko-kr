---
title: 컴파일러 경고(수준 1) C4353
ms.date: 11/04/2016
f1_keywords:
- C4353
helpviewer_keywords:
- C4353
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
ms.openlocfilehash: 305c1156ae8dc664edba17287786db50bfabbd18
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384194"
---
# <a name="compiler-warning-level-1-c4353"></a>컴파일러 경고(수준 1) C4353

비표준 확장이 사용 됨: 함수 식으로 상수 0입니다. 내장 '__noop' 함수를 대신 사용

함수 식으로 상수 0 (0)를 사용할 수 없습니다. 자세한 내용은 [__noop](../../intrinsics/noop.md)합니다.

다음 샘플에서는 C4353 오류가 생성 됩니다.

```
// C4353.cpp
// compile with: /W1
void MyPrintf(void){};
#define X 0
#if X
   #define DBPRINT MyPrint
#else
   #define DBPRINT 0   // C4353 expected
#endif
int main(){
DBPRINT();
}
```