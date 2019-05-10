---
title: 컴파일러 오류 C2550
ms.date: 11/04/2016
f1_keywords:
- C2550
helpviewer_keywords:
- C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
ms.openlocfilehash: 2df6ae70be31bc519e6cfd826646073becf1ad61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353354"
---
# <a name="compiler-error-c2550"></a>컴파일러 오류 C2550

'identifier': 생성자 이니셜라이저 목록은 생성자 정의에 허용 됩니다

기본 클래스 이니셜라이저 목록 생성자가 아닌 함수의 정의에 사용 됩니다.

다음 샘플에서는 C2550를 생성합니다.

```
// C2550.cpp
// compile with: /c
class C {
public:
   C();
};

class D : public C {
public:
   D();
   void func();
};

void D::func() : C() {}  // C2550
D::D() : C() {}   // OK
```