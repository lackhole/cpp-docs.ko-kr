---
title: 컴파일러 오류 C3055
ms.date: 11/04/2016
f1_keywords:
- C3055
helpviewer_keywords:
- C3055
ms.assetid: 60446ee0-18dd-48fc-9059-f0a14229dce8
ms.openlocfilehash: 2a770709b4958f446e8e5a64b245f2932f99460f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265583"
---
# <a name="compiler-error-c3055"></a>컴파일러 오류 C3055

'symbol': 'threadprivate' 지시문에 사용된 기호만 참조할 수 있습니다.

기호가 참조된 다음 [threadprivate](../../parallel/openmp/reference/threadprivate.md) 절에서 사용되며 이는 허용되지 않습니다.

다음 샘플에서는 C3055를 생성합니다.

```
// C3055.cpp
// compile with: /openmp
int x, y;
int z = x;
#pragma omp threadprivate(x, y)   // C3055

void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

해결 방법:

```
// C3055b.cpp
// compile with: /openmp /LD
int x, y, z;
#pragma omp threadprivate(x, y)

void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```