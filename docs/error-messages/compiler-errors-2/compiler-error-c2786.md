---
title: 컴파일러 오류 C2786
ms.date: 11/04/2016
f1_keywords:
- C2786
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
ms.openlocfilehash: b03155ad1a209ae59327dd31d432f5623f380ac9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265999"
---
# <a name="compiler-error-c2786"></a>컴파일러 오류 C2786

'type': __uuidof의 피연산자가 잘못 되었습니다

합니다 [__uuidof](../../cpp/uuidof-operator.md) 연산자 연결 된 GUID 또는 사용자 정의 형식의 개체를 사용 하 여 사용자 정의 형식을 사용 합니다.  가능한 원인:

1. 사용자 정의 형식 인수가 아닙니다.

1. `__uuidof` 인수에서 GUID를 추출할 수 없습니다.

다음 샘플에서는 C2786 오류가 생성 됩니다.

```
// C2786.cpp
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};

int main() {
   __uuidof(int);   // C2786
   __uuidof(int *);   // C2786
   __uuidof(A **);   // C2786

   // no error
   __uuidof(A);
   __uuidof(A *);
   __uuidof(A &);
   __uuidof(A[]);

   int i;
   int *pi;
   A **ppa;

   __uuidof(i);      // C2786
   __uuidof(pi);     // C2786
   __uuidof(ppa);    // C2786
}
```