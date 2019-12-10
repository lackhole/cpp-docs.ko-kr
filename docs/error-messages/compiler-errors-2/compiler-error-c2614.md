---
title: 컴파일러 오류 C2614
ms.date: 11/04/2016
f1_keywords:
- C2614
helpviewer_keywords:
- C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
ms.openlocfilehash: 202d7f4caec3aabfde5d69adeaafa3da5dd67623
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737675"
---
# <a name="compiler-error-c2614"></a>컴파일러 오류 C2614

' class1 ': 잘못 된 멤버 초기화: ' class2 '은 (는) 기본 또는 멤버가 아닙니다.

멤버 또는 기본 클래스만 클래스 또는 구조체의 초기화 목록에 표시 될 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2614를 생성 합니다.

```cpp
// C2614.cpp
// compile with: /c
struct A {
   int i;
   A( int ia ) : B( i ) {};   // C2614 B is not a member of A
};

struct A2 {
   int B;
   int i;
   A2( int ia ) : B( i ) {};   // OK
};
```
