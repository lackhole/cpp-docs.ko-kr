---
title: 컴파일러 오류 C3011
ms.date: 11/04/2016
f1_keywords:
- C3011
helpviewer_keywords:
- C3011
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
ms.openlocfilehash: 453af6be844b1a3aa4f0e9c80f6b5733952c1557
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350311"
---
# <a name="compiler-error-c3011"></a>컴파일러 오류 C3011

병렬 영역 내부에서는 직접 인라인 어셈블리를 사용할 수 없습니다.

`omp` 병렬 영역은 인라인 어셈블리 명령을 포함할 수 없습니다.

다음 샘플에서는 C3011을 생성합니다.

```
// C3011.cpp
// compile with: /openmp
// processor: /x86
int main() {
   int   n = 0;

   #pragma omp parallel
   {
      _asm mov eax, n   // Delete this line to resolve this error.
   }   // C3011
}
```