---
title: 컴파일러 오류 C2036
ms.date: 11/04/2016
f1_keywords:
- C2036
helpviewer_keywords:
- C2036
ms.assetid: 895821a9-65d1-44b5-bde1-dae827f3e486
ms.openlocfilehash: c0d6c06a72e6ffbd2090577eeee9739394ee2791
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755098"
---
# <a name="compiler-error-c2036"></a>컴파일러 오류 C2036

' identifier ': 알 수 없는 크기입니다.

`identifier`에 대 한 작업에는 확인할 수 없는 데이터 개체의 크기가 필요 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2036를 생성 합니다.

```
// C2036.c
// a C program
struct A* pA;
struct B { int i; } *pB;
int main() {
   pA++;   // C2036, size of A not known
   ((char*)pA)++;   // OK

   pB++;   // OK
}
```

## <a name="example"></a>예제

다음 샘플에서는 C2036를 생성 합니다.

```cpp
// C2036_2.cpp
// a C++ program
struct A* pA;
int main() {
   pA++;   // C2036, size of A not known
   ((char*&)pA)++;   // OK, if sizeof(A) == sizeof(char)
}
```
