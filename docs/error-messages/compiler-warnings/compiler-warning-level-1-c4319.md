---
title: 컴파일러 경고(수준 1) C4319
ms.date: 1/18/2018
f1_keywords:
- C4319
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
ms.openlocfilehash: 20b268bacd6e7e259e9b4fa1c9e98fa6fd353718
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385474"
---
# <a name="compiler-warning-level-1-c4319"></a>컴파일러 경고(수준 1) C4319

> ' ~': 0 확장 '*type1*'to'*type2*' 큰 크기의

결과 **~** 큰 형식으로 변환 될 때 서명 되지 않고 다음 0 확장 (비트 보수) 연산자가 있습니다.

## <a name="example"></a>예제

다음 예에서 `~(a - 1)` 32 비트 부호 없는 long 식으로 계산 되 고 그런 다음 0 확장을 통해 64 비트로 변환 합니다. 따라서 예기치 않은 결과가 발생할 수 있습니다.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
