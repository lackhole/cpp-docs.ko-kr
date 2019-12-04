---
title: 컴파일러 오류 C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 2f0ca98dc44a78adde378a0f80078ae30c590e11
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738819"
---
# <a name="compiler-error-c3199"></a>컴파일러 오류 C3199

부동 소수점 pragma를 잘못 사용 했습니다. 비 precise 모드에서는 예외가 지원 되지 않습니다.

[Float_control](../../preprocessor/float-control.md) pragma가 **/fp: precise**이외의 [/fp](../../build/reference/fp-specify-floating-point-behavior.md) 설정에서 부동 소수점 예외 모델을 지정 하는 데 사용 되었습니다.

다음 샘플에서는 C3199를 생성 합니다.

```cpp
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```
