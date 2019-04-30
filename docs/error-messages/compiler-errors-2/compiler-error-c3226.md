---
title: 컴파일러 오류 C3226
ms.date: 11/04/2016
f1_keywords:
- C3226
helpviewer_keywords:
- C3226
ms.assetid: 636106ca-6f4e-4303-a6a0-8803221ec67d
ms.openlocfilehash: 39b715b580d6fca9c15e5b9e2b63a9afb609eb16
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174005"
---
# <a name="compiler-error-c3226"></a>컴파일러 오류 C3226

제네릭 선언 내부에서는 템플릿을 선언할 수 없습니다.

제네릭 클래스 내부에서는 제네릭 선언을 사용합니다.

다음 샘플에서는 C3226을 생성합니다.

```
// C3226.cpp
// compile with: /clr
generic <class T>
ref class C {
   template <class T1>   // C3226
   ref struct S1 {};
};
```

다음 샘플에는 가능한 해결 방법을 보여 줍니다.

```
// C3226b.cpp
// compile with: /clr /c
generic <class T>
ref class C {
   generic <class T1>
   ref struct S1 {};
};
```