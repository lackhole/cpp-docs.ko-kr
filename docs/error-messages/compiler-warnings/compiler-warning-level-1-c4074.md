---
title: 컴파일러 경고 (수준 1) C4074
ms.date: 11/04/2016
f1_keywords:
- C4074
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
ms.openlocfilehash: d9b0259e95198396d8c34ca43781045248e22ad9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374744"
---
# <a name="compiler-warning-level-1-c4074"></a>컴파일러 경고 (수준 1) C4074

이니셜라이저가 컴파일러 예약 초기화 영역

으로 지정 되 고 컴파일러 초기화 영역을 [#pragma init_seg](../../preprocessor/init-seg.md), Microsoft에서 예약 됩니다. C 런타임 라이브러리를 초기화 하기 전에이 영역에서 코드를 실행할 수 있습니다.

다음 샘플에서는 C4074 오류가 생성 됩니다.

```
// C4074.cpp
// compile with: /W1
#pragma init_seg( compiler )   // C4074

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```