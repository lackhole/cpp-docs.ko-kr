---
title: 컴파일러 오류 C2386
ms.date: 11/04/2016
f1_keywords:
- C2386
helpviewer_keywords:
- C2386
ms.assetid: aaaa1284-34a0-4da2-8547-9fcbb559dae0
ms.openlocfilehash: 1ac58d63498df32488c1a0743aa6ad9f7b77b7ca
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745111"
---
# <a name="compiler-error-c2386"></a>컴파일러 오류 C2386

'symbol': 이름이 같은 기호가 현재 범위에 이미 있습니다.

네임스페이스 별칭을 만들려고 했지만 선택한 이름이 이미 있습니다.

다음 샘플에서는 C2386을 생성합니다.

```cpp
// C2386.cpp
namespace A {
   int k;
}

int i;
namespace i = A;   // C2386, i already exists
```
