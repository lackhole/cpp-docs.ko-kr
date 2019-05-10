---
title: 컴파일러 오류 C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 934e980149ad893e6799b0ab119a148fc5652fdc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402790"
---
# <a name="compiler-error-c3199"></a>컴파일러 오류 C3199

부동 소수점 pragma 잘못 사용 했습니다: 예외는 명확 하지 않은 모드에서 지원 되지 않습니다

합니다 [float_control](../../preprocessor/float-control.md) pragma는 아래에 있는 부동 소수점 예외 모델을 지정 하는 데 사용 된는 [/fp](../../build/reference/fp-specify-floating-point-behavior.md) 이외의 다른 위치로 설정 **/fp: 정확한**합니다.

다음 샘플에서는 C3199 오류가 생성 됩니다.

```
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```