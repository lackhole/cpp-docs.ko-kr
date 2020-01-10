---
title: 컴파일러 오류 C3003
ms.date: 11/04/2016
f1_keywords:
- C3003
helpviewer_keywords:
- C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
ms.openlocfilehash: 2f7b645f0b76f500502faea86a9fe20bb8eb5a62
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298898"
---
# <a name="compiler-error-c3003"></a>컴파일러 오류 C3003

'directive': 지시문 절 다음에는 OpenMP 지시문 이름이 올 수 없습니다.

OpenMP 지시문 이름이 OpenMP 지시문 절 다음에 올 수 없습니다.

다음 샘플에서는 C3003을 생성합니다.

```c
// C3003.c
// compile with: /openmp
int main()
{
   int x, y, z;
   #pragma omp parallel shared(x, y, z) for   // C3003
}
```
