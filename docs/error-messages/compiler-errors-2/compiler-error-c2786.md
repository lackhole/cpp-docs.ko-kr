---
title: 컴파일러 오류 C2786
ms.date: 11/04/2016
f1_keywords:
- C2786
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
ms.openlocfilehash: ba5d05e9c7cc702509144fb876a1301bfc8bf3d4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739612"
---
# <a name="compiler-error-c2786"></a>컴파일러 오류 C2786

' type ': __uuidof에 대 한 피연산자가 잘못 되었습니다.

[__Uuidof](../../cpp/uuidof-operator.md) 연산자는 GUID가 연결 된 사용자 정의 형식 또는 사용자 정의 형식의 개체를 사용 합니다.  가능한 원인

1. 인수가 사용자 정의 형식이 아닙니다.

1. `__uuidof`는 인수에서 GUID를 추출할 수 없습니다.

다음 샘플에서는 C2786를 생성 합니다.

```cpp
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
