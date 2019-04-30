---
title: 컴파일러 오류 C2094
ms.date: 11/04/2016
f1_keywords:
- C2094
helpviewer_keywords:
- C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
ms.openlocfilehash: 072c51ca4ae25c6f51b1841ea129a7b4fb495bdf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377100"
---
# <a name="compiler-error-c2094"></a>컴파일러 오류 C2094

'identifier' 레이블이 정의되지 않았습니다.

[goto](../../cpp/goto-statement-cpp.md) 문에서 사용하는 레이블이 함수에 존재하지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2094를 생성합니다.

```cpp
// C2094.c
int main() {
   goto test;
}   // C2094
```

해결 방법:

```cpp
// C2094b.c
int main() {
   goto test;
   test:
   {
   }
}
```