---
title: 컴파일러 경고 (수준 1) C4028
ms.date: 11/04/2016
f1_keywords:
- C4028
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
ms.openlocfilehash: 19bfd2659ee9017d3a304dee2d647da091515876
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623846"
---
# <a name="compiler-warning-level-1-c4028"></a>컴파일러 경고 (수준 1) C4028

' number ' 형식 매개 변수가 선언과 다릅니다.

정식 매개 변수의 형식이 선언의 해당 매개 변수와 일치 하지 않습니다. 원래 선언의 형식이 사용 됩니다.

이 경고는 C 소스 코드에 대해서만 유효 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4028를 생성 합니다.

```c
// C4028.c
// compile with: /W1 /Za
void f(int , ...);
void f(int i, int j) {}   // C4028

void g(int , int);
void g(int i, int j) {}   // OK

int main() {}
```