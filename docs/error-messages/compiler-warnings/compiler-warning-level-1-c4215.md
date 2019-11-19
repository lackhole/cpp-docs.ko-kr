---
title: 컴파일러 경고 (수준 1) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: 91be04f927c63ccbb0668bbe70cbd7c5813f8dfc
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627342"
---
# <a name="compiler-warning-level-1-c4215"></a>컴파일러 경고 (수준 1) C4215

비표준 확장이 사용 됨: long float

기본 Microsoft 확장 (/Ze)은 **long float** 를 **double**로 처리 합니다. ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))은 그렇지 않습니다. **Double** 을 사용 하 여 호환성을 유지 합니다.

다음 샘플에서는 C4215를 생성 합니다.

```cpp
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```