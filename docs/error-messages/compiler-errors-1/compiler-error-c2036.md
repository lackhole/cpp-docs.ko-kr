---
title: 컴파일러 오류 C2036
ms.date: 11/04/2016
f1_keywords:
- C2036
helpviewer_keywords:
- C2036
ms.assetid: 895821a9-65d1-44b5-bde1-dae827f3e486
ms.openlocfilehash: 47e691a045b3d1bd79226bdda8d96d24e2a80d80
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400502"
---
# <a name="compiler-error-c2036"></a>컴파일러 오류 C2036

'identifier': 알 수 없는 크기

에 대 한 작업 `identifier` 확인할 수 있는 데이터 개체의 크기가 필요 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2036 오류가 발생 합니다.

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

다음 샘플에서는 C2036 오류가 발생 합니다.

```
// C2036_2.cpp
// a C++ program
struct A* pA;
int main() {
   pA++;   // C2036, size of A not known
   ((char*&)pA)++;   // OK, if sizeof(A) == sizeof(char)
}
```