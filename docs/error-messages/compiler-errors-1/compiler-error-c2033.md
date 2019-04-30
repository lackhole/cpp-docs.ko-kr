---
title: 컴파일러 오류 C2033
ms.date: 11/04/2016
f1_keywords:
- C2033
helpviewer_keywords:
- C2033
ms.assetid: fd5a1637-9db2-4c98-a7cc-b63b39737cd9
ms.openlocfilehash: 8147c707c70e6c3f21ed81b2acf0a59b72065408
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400489"
---
# <a name="compiler-error-c2033"></a>컴파일러 오류 C2033

'identifier': 비트 필드에 간접 참조를 사용할 수 없습니다.

비트 필드가 허용되지 않는 포인터로 선언되었습니다.

다음 샘플에서는 C2033을 생성합니다.

```
// C2033.cpp
struct S {
   int *b : 1;  // C2033
};
```

해결 방법:

```
// C2033b.cpp
// compile with: /c
struct S {
   int b : 1;
};
```