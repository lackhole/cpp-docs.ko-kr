---
title: 컴파일러 경고 (수준 1) C4555
ms.date: 11/04/2016
f1_keywords:
- C4555
helpviewer_keywords:
- C4555
ms.assetid: 50b286c1-f7bf-4292-b1fa-baaac9538611
ms.openlocfilehash: e2c6a12b26754d7823252554950c124bdff4e6e8
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965982"
---
# <a name="compiler-warning-level-1-c4555"></a>컴파일러 경고 (수준 1) C4555

식이 효과가 없습니다. 파생 작업이 있는 식이어야 합니다.

이 경고는 식이 영향을 주지 않는 경우 사용자에 게 알려 줍니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

예를 들어 다음과 같은 가치를 제공해야 합니다.

```cpp
// C4555.cpp
// compile with: /W1
#pragma warning(default:4555)

void func1()
{
   1;   // C4555
}

void func2()
{
   int x;
   x;   // C4555
}

int main()
{
}
```