---
title: 컴파일러 오류 C2036
ms.date: 11/04/2016
f1_keywords:
- C2036
helpviewer_keywords:
- C2036
ms.assetid: 895821a9-65d1-44b5-bde1-dae827f3e486
ms.openlocfilehash: df36dc5d6e399a0fc35b71e6d3a82ea77aeb5105
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302083"
---
# <a name="compiler-error-c2036"></a>컴파일러 오류 C2036

' identifier ': 알 수 없는 크기입니다.

`identifier`에 대 한 작업에는 확인할 수 없는 데이터 개체의 크기가 필요 합니다.

## <a name="example"></a>예

다음 샘플에서는 C2036를 생성 합니다.

```c
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

## <a name="example"></a>예

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
