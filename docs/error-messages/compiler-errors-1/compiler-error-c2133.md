---
title: 컴파일러 오류 C2133
ms.date: 11/04/2016
f1_keywords:
- C2133
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
ms.openlocfilehash: b51b556ea576e02b85a5c2ee5032909af39c7b2f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758439"
---
# <a name="compiler-error-c2133"></a>컴파일러 오류 C2133

' identifier ': 알 수 없는 크기입니다.

크기 배열 배열은 클래스, 구조체, 공용 구조체 또는 열거형의 멤버로 선언 됩니다. /Za (ANSI C) 옵션은 크기 배열 멤버 배열을 허용 하지 않습니다.

다음 샘플에서는 C2133를 생성 합니다.

```cpp
// C2133.cpp
// compile with: /Za
struct X {
   int a[0];   // C2133 unsized array
};
```

가능한 해결 방법:

```cpp
// C2133b.cpp
// compile with: /c
struct X {
   int a[0];   // no /Za
};
```
