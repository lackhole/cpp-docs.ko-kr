---
title: 컴파일러 오류 C2648
ms.date: 11/04/2016
f1_keywords:
- C2648
helpviewer_keywords:
- C2648
ms.assetid: ce338337-9154-4f85-bb61-b05fdbfad75d
ms.openlocfilehash: fc563c6e85555b113734ec93fc545bb505bd3f38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282155"
---
# <a name="compiler-error-c2648"></a>컴파일러 오류 C2648

'identifier': 기본 매개 변수는 정적 멤버를 필요한 만큼 멤버 사용

비정적 멤버는 기본 매개 변수로 사용 됩니다.

다음 샘플에서는 C2648 오류가 생성 됩니다.

```
// C2648.cpp
// compile with: /c
class C {
public:
   int i;
   static int j;
   void func1( int i = i );  // C2648  i is not static
   void func2( int i = j );  // OK
};
```