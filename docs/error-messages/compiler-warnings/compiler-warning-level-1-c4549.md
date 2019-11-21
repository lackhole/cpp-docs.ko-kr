---
title: 컴파일러 경고 (수준 1) C4549
ms.date: 11/04/2016
f1_keywords:
- C4549
helpviewer_keywords:
- C4549
ms.assetid: 81a07676-625b-4f58-9b0c-3ee22830b04a
ms.openlocfilehash: 728c3040f383632f2b4990c2f1d44e500a040138
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966388"
---
# <a name="compiler-warning-level-1-c4549"></a>컴파일러 경고 (수준 1) C4549

' operator ': 쉼표 앞의 연산자는 적용 되지 않습니다. ' operator '를 의도 했습니까?

컴파일러가 잘못 된 형식의 쉼표 식을 발견 했습니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.

다음 샘플에서는 C4549를 생성 합니다.

```cpp
// C4549.cpp
// compile with: /W1
#pragma warning (default : 4549)

int main() {
   int i = 0, k = 0;

   if ( i == 0, k )   // C4549
   // try the following line instead
   // if ( i == 0 )
      i++;
}
```