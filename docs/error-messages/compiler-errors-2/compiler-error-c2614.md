---
title: 컴파일러 오류 C2614
ms.date: 11/04/2016
f1_keywords:
- C2614
helpviewer_keywords:
- C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
ms.openlocfilehash: 71f0fe3211ce253bcf30347658692651e84ab608
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344740"
---
# <a name="compiler-error-c2614"></a>컴파일러 오류 C2614

'class1': 멤버 초기화가 잘못: 'class2' 기본 또는 멤버가 아닙니다

멤버 또는 기본 클래스는 클래스 또는 구조체에 대 한 초기화 목록에 나타날 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2614 오류가 발생 합니다.

```
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