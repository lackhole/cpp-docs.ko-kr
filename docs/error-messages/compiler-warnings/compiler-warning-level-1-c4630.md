---
title: 컴파일러 경고(수준 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 98ea72bef0cb95163604144c1069a13c3b27d81c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324534"
---
# <a name="compiler-warning-level-1-c4630"></a>컴파일러 경고(수준 1) C4630

'symbol': 멤버 정의에 잘못 된 'extern' 저장소 클래스 지정자

데이터 멤버 또는 멤버 함수는으로 정의 `extern`합니다. 멤버는 전체 개체 수 있지만 외부 일 수 없습니다. 컴파일러에서 무시 된 `extern` 키워드입니다. 다음 샘플에서는 C4630 오류가 생성 됩니다.

```
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```