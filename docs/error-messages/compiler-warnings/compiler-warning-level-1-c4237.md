---
title: 컴파일러 경고(수준 1) C4237
ms.date: 11/04/2016
f1_keywords:
- C4237
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
ms.openlocfilehash: c68e84daa2ca1aa023123203bb851e92758f9e40
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447683"
---
# <a name="compiler-warning-level-1-c4237"></a>컴파일러 경고(수준 1) C4237

'keyword' 키워드는 아직 지원 되지 않지만 나중에 사용

키워드는 C++ 사양 Microsoft에서는 구현 되지 않습니다 C++ 컴파일러와 이지만 키워드를 사용자 정의 기호로 사용할 수 없습니다.

다음 샘플에서는 C4237 오류가 생성 됩니다.

```
// C4237.cpp
// compile with: /W1 /c
int export;   // C4237
```