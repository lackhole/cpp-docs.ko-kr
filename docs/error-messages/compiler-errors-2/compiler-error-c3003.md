---
title: 컴파일러 오류 C3003
ms.date: 11/04/2016
f1_keywords:
- C3003
helpviewer_keywords:
- C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
ms.openlocfilehash: 6d15d8bde8855b8dcc4857492acdeb950731b503
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152503"
---
# <a name="compiler-error-c3003"></a>컴파일러 오류 C3003

' directive': OpenMP 지시문 이름이 지시문 절 올 수 없습니다

OpenMP 지시문 이름이 OpenMP 지시문 절 다음에 올 수 없습니다.

다음 샘플에서는 C3003을 생성합니다.

```
// C3003.c
// compile with: /openmp
int main()
{
   int x, y, z;
   #pragma omp parallel shared(x, y, z) for   // C3003
}
```