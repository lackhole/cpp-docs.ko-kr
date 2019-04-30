---
title: 컴파일러 경고(수준 1) C4237
ms.date: 11/04/2016
f1_keywords:
- C4237
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
ms.openlocfilehash: 04fcb99e1dd1e348716e25affb22b54079d53aa9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207385"
---
# <a name="compiler-warning-level-1-c4237"></a>컴파일러 경고(수준 1) C4237

'keyword' 키워드는 아직 지원 되지 않지만 나중에 사용

키워드는 C++ 사양 시각적 개체에서 구현 되지 않습니다 C++ 컴파일러와 이지만 키워드를 사용자 정의 기호로 사용할 수 없습니다.

다음 샘플에서는 C4237 오류가 생성 됩니다.

```
// C4237.cpp
// compile with: /W1 /c
int export;   // C4237
```