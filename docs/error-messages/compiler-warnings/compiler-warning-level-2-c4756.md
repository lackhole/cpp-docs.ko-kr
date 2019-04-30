---
title: 컴파일러 경고(수준 2) C4756
ms.date: 11/04/2016
f1_keywords:
- C4756
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
ms.openlocfilehash: 0e4e0d5e227795a45eb22e3fcb17bdfa600d69e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402426"
---
# <a name="compiler-warning-level-2-c4756"></a>컴파일러 경고(수준 2) C4756

상수 산술 연산에서 오버플로가 발생 했습니다

컴파일러에서 컴파일하는 동안 상수 산술 연산 수행 하는 동안 예외가 생성 합니다.

다음 샘플에서는 C4756 오류가 생성 됩니다.

```
// C4756.cpp
// compile with: /W2 /Od
int main()
{
   float f = 1e100+1e100;   // C4756
}
```