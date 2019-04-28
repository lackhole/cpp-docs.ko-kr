---
title: 컴파일러 오류 C3219
ms.date: 11/04/2016
f1_keywords:
- C3219
helpviewer_keywords:
- C3219
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
ms.openlocfilehash: a93e9ed1a8e00eaecc664bda02a70c81b6c81ded
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243039"
---
# <a name="compiler-error-c3219"></a>컴파일러 오류 C3219

'param': 제네릭 매개 변수는 여러 개의 비인터페이스('class')에 의해 제약을 받을 수 없습니다.

제네릭 매개 변수를 둘 이상의 관리되는 클래스로 제한할 수 없습니다.

다음 샘플에서는 C3219를 생성합니다.

```
// C3219.cpp
// compile with: /clr
ref class A {};
ref class B {};

generic <class T>
where T : A, B
ref class E {};   // C3219
```

다음 샘플에는 가능한 해결 방법을 보여 줍니다.

```
// C3219b.cpp
// compile with: /clr /c
ref class A {};

interface struct C {};

generic <class T>
where T : A
ref class E {};
```