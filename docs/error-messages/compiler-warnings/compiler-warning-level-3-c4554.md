---
title: 컴파일러 경고(수준 3) C4554
ms.date: 11/04/2016
f1_keywords:
- C4554
helpviewer_keywords:
- C4554
ms.assetid: 55bb68f0-2e80-4330-8921-51083c4f8d53
ms.openlocfilehash: 45f9d85f272bb5093fd418981ea3dbdc8cb7f1c0
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74992011"
---
# <a name="compiler-warning-level-3-c4554"></a>컴파일러 경고(수준 3) C4554

' operator ': 연산자 우선 순위를 검사 하 여 가능한 오류를 확인 하십시오. 괄호를 사용 하 여 우선 순위를 명확 하 게 설명

다음 샘플에서는 C4554를 생성 합니다.

```cpp
// C4554.cpp
// compile with: /W3 /WX
int main() {
   int a = 0, b = 0, c = 0;
   a = a << b + c;   // C4554
   // probably intended (a << b) + c,
   // but will get a << (b + c)
}
```
