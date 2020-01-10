---
title: 컴파일러 오류 C2032
ms.date: 11/04/2016
f1_keywords:
- C2032
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
ms.openlocfilehash: d20bc61df2d0bab9115768b3bc0589f11a9bcdb9
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302096"
---
# <a name="compiler-error-c2032"></a>컴파일러 오류 C2032

' identifier ': 함수는 구조체/공용 구조체 ' structorunion '의 멤버일 수 없습니다.

구조체 또는 공용 구조체에 멤버 함수가 C++ 있지만 C에서는 허용 되지 않습니다. 오류를 해결 하려면 C++ 프로그램으로 컴파일하거나 멤버 함수를 제거 합니다.

다음 샘플에서는 C2032를 생성 합니다.

```c
// C2032.c
struct z {
   int i;
   void func();   // C2032
};
```

가능한 해결 방법:

```c
// C2032b.c
// compile with: /c
struct z {
   int i;
};
```
