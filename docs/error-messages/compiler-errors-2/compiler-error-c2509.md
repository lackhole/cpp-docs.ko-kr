---
title: 컴파일러 오류 C2509
ms.date: 11/04/2016
f1_keywords:
- C2509
helpviewer_keywords:
- C2509
ms.assetid: 339c1fcd-ec4a-456c-9f18-a9b24d9921af
ms.openlocfilehash: 21ca3bdcb156aaa654ae3d5d0c1c467a97129dcc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165010"
---
# <a name="compiler-error-c2509"></a>컴파일러 오류 C2509

'identifier': 'class'에서 선언 되지 멤버 함수

함수는 지정된 된 클래스에서 선언 되지 않았습니다.

## <a name="example"></a>예제

다음 샘플 C2509를 생성합니다.

```
// C2509.cpp
// compile with: /c
struct A {
   virtual int vfunc() = 0;
   virtual int vfunc2() = 0;
};

struct B : private A {
   using A::vfunc;
   virtual int vfunc2();
};

int B::vfunc() { return 1; }   // C2509
int B::vfunc2() { return 1; }   // OK
```