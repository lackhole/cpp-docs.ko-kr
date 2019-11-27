---
title: 컴파일러 경고(수준 4) C4019
ms.date: 11/04/2016
f1_keywords:
- C4019
helpviewer_keywords:
- C4019
ms.assetid: 4ecfe85d-673f-4334-8154-36fe7f0b3444
ms.openlocfilehash: b15d024f217280fb4fc49242f4bfc1e7fcc2b303
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541233"
---
# <a name="compiler-warning-level-4-c4019"></a>컴파일러 경고(수준 4) C4019

전역 범위에 빈 문이 있습니다.

전역 범위의 세미콜론 앞에 문이 오지 않습니다.

불필요한 세미콜론을 제거하면 이 경고를 해결할 수 있습니다.

## <a name="example"></a>예제

```c
// C4019.c
// compile with: /Za /W4
#define declint( varname ) int varname;
declint( a );   // C4019, int a;;
declint( b )   // OK, int b;

int main()
{
}
```