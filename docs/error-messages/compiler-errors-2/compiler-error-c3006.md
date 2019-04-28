---
title: 컴파일러 오류 C3006
ms.date: 11/04/2016
f1_keywords:
- C3006
helpviewer_keywords:
- C3006
ms.assetid: 449082ec-fd45-4c47-8ab3-ba6a719e4dc4
ms.openlocfilehash: 7200d0ab3b14a1f9faa310f466963d74f7c98985
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350375"
---
# <a name="compiler-error-c3006"></a>컴파일러 오류 C3006

'clause': OpenMP 'directive' 지시문의 절에 필요한 인수가 없습니다.

OpenMP 지시문에 필요한 인수가 없습니다.

다음 샘플에서는 C3006을 생성합니다.

```
// C3006.c
// compile with: /openmp
int main()
{
   #pragma omp parallel shared   // C3006
   // Try the following line instead:
   // #pragma omp parallel shared(x) {}

}
```