---
title: 컴파일러 경고 (수준 2) C4056
ms.date: 11/04/2016
f1_keywords:
- C4056
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
ms.openlocfilehash: 20e7c2693c14c0ea05cc6f07f8dad4ce76c1ef5e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052186"
---
# <a name="compiler-warning-level-2-c4056"></a>컴파일러 경고 (수준 2) C4056

부동 소수점 상수 산술 연산에서 오버플로가 발생 했습니다.

부동 소수점 상수 산술 연산은 최대 허용 값을 초과 하는 결과를 생성 합니다.

이 경고는 상수 산술 연산 중에 컴파일러 최적화가 수행 했을 때 발생할 수 있습니다. 최적화 ([/od](../../build/reference/od-disable-debug.md))를 해제할 때이 경고를 무시 해도 안전 하 게 무시할 수 있습니다.

다음 샘플에서는 C4056를 생성 합니다.

```cpp
// C4056.cpp
// compile with: /W2 /LD
#pragma warning (default : 4056)
float fp_val = 1.0e300 * 1.0e300;   // C4056
```