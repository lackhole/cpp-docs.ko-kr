---
title: 컴파일러 오류 C3008
ms.date: 11/04/2016
f1_keywords:
- C3008
helpviewer_keywords:
- C3008
ms.assetid: 04d93201-28e5-4be0-945c-aad616376f4b
ms.openlocfilehash: 4f3b0e8ec935a4425977ea89993677704681a9e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165166"
---
# <a name="compiler-error-c3008"></a>컴파일러 오류 C3008

'arg': OpenMP 'directive' 지시문의 인수에 닫는 ')'가 없습니다.

인수를 사용하는 OpenMP 지시문에 닫는 괄호가 없습니다.

다음 샘플에서는 C3008을 생성합니다.

```
// C3008.c
// compile with: /openmp
int main()
{
   int x, y, z;
   #pragma omp parallel shared(x   // C3008
   // Try the following line instead:
   #pragma omp parallel shared(x)
   {
   }
}
```