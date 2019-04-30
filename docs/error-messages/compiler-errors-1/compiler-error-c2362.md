---
title: 컴파일러 오류 C2362
ms.date: 11/04/2016
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: 17656b2a48a3680a9269d3ca300fd4188eda6b84
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364326"
---
# <a name="compiler-error-c2362"></a>컴파일러 오류 C2362

'identifier' 초기화가 'goto 레이블' 의해 생략 되었습니다.

사용 하 여 컴파일하면 [/Za](../../build/reference/za-ze-disable-language-extensions.md)에서 레이블로 점프 식별자를 초기화할 수 없습니다.

를 입력 하지 않으면 하는 블록에서 선언 묶입니다 않으면 이니셜라이저를 사용 하는 선언이 점프할 수 없습니다 또는 변수가 이미 초기화 되었습니다.

다음 샘플에서는 C2326을 생성합니다.

```
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

해결 방법:

```
// C2362b.cpp
// compile with: /Za
int main() {
   goto label1;
   {
      int j = 1;   // OK, this block is never entered
   }
label1:;
}
```