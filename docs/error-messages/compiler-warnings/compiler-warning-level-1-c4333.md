---
title: 컴파일러 경고 (수준 1) C4333
ms.date: 11/04/2016
f1_keywords:
- C4333
helpviewer_keywords:
- C4333
ms.assetid: d3763c52-6110-4da0-84db-5264e3f3f166
ms.openlocfilehash: 0b4e567f07d15b47d3c1f507b43257dac9a49d66
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966049"
---
# <a name="compiler-warning-level-1-c4333"></a>컴파일러 경고 (수준 1) C4333

' operator ': 오른쪽 시프트 횟수가 너무 커 데이터가 손실 됩니다.

오른쪽 시프트 연산의 크기가 너무 깁니다.  모든 중요 한 비트는 이동 되며 결과는 항상 0입니다.

## <a name="example"></a>예제

다음 샘플에서는 C4333를 생성 합니다.

```cpp
// C4333.cpp
// compile with: /c /W1
unsigned shift8 (unsigned char c) {
   return c >> 8;   // C4333

   // try the following line instead
   // return c >> 4;   // OK
}
```