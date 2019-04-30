---
title: 컴파일러 경고 (수준 2) C4056
ms.date: 11/04/2016
f1_keywords:
- C4056
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
ms.openlocfilehash: 59c66f2f7dcbd1e20463df613b1b7deae6a1c349
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349869"
---
# <a name="compiler-warning-level-2-c4056"></a>컴파일러 경고 (수준 2) C4056

부동 소수점 상수 산술 연산에서 오버플로가 발생 했습니다

부동 소수점 상수 산술 연산에 허용 되는 최대값을 초과 하는 결과 생성 합니다.

이 경고는 컴파일러 최적화 상수 산술 연산 중에 수행 하 여 발생할 수 있습니다. 최적화를 해제할 때 경우에 안전 하 게이 경고를 무시할 수 있습니다 ([/Od](../../build/reference/od-disable-debug.md)).

다음 샘플에서는 C4056 오류가 생성 됩니다.

```
// C4056.cpp
// compile with: /W2 /LD
#pragma warning (default : 4056)
float fp_val = 1.0e300 * 1.0e300;   // C4056
```