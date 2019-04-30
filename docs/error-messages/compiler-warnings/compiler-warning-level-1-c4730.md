---
title: 컴파일러 경고 (수준 1) C4730
ms.date: 11/04/2016
f1_keywords:
- C4730
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
ms.openlocfilehash: 4da60194deaeac3c79f8c3e9be3bd87d91bc7ca2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386358"
---
# <a name="compiler-warning-level-1-c4730"></a>컴파일러 경고 (수준 1) C4730

'main': _m64 혼합 및 부동 소수점 식이 잘못 된 코드에서 발생할 수 있습니다

함수를 사용 하 여 [__m64](../../cpp/m64.md) 하 고 **float**/**double** 형식입니다. 동일한 물리적 MMX 및 부동 소수점 레지스터를 공유 하기 때문에 레지스터 공간 (사용할 수 없습니다 동시에)를 사용 하 여 `__m64` 하 고 **float**/**double** 동일한 형식 함수는 예외를 일으킬 수 있는 데이터가 손상에서 될 수 있습니다.

안전 하 게 사용 `__m64` 형식과 동일한 함수에 부동 소수점 형식에 형식 중 하나를 사용 하는 각 명령으로 구분 해야 합니다 **_m_empty** (MMX 용) 또는 **_m_femms** (3DNow! 용) 내장 함수입니다.

다음 샘플에서는 C4730 오류가 생성 됩니다.

```
// C4730.cpp
// compile with: /W1
// processor: x86
#include "mmintrin.h"

void func(double)
{
}

int main(__m64 a, __m64 b)
{
   __m64 m;
   double f;
   f = 1.0;
   m = _m_paddb(a, b);
   // uncomment the next line to resolve C4730
   // _m_empty();
   func(f * 3.0);   // C4730
}
```