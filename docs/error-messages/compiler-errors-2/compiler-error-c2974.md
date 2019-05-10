---
title: 컴파일러 오류 C2974
ms.date: 11/04/2016
f1_keywords:
- C2974
helpviewer_keywords:
- C2974
ms.assetid: 1b444260-f2bf-48d7-ab1e-35573d8c4a0e
ms.openlocfilehash: 2fa0fae07435f3ab63398b7b3f02f9c662e7b436
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256571"
---
# <a name="compiler-error-c2974"></a>컴파일러 오류 C2974

잘못 된 형식 인수 'number' 형식이 예상

제네릭 또는 템플릿 인수는 제네릭 또는 템플릿 선언을 일치 하지 않습니다. 형식 꺾쇠 괄호 안에 표시 됩니다. 올바른 유형을 검색 하는 제네릭 또는 템플릿 정의 확인 합니다.

다음 샘플에서는 C2974를 생성합니다.

```
// C2974.cpp
// C2974 expected
template <class T>
struct TC {};

template <typename T>
void tf(T){}

int main() {
   // Delete the following 2 lines to resolve
   TC<1>* tc;
   tf<"abc">("abc");

   TC<int>* tc;
   tf<const char *>("abc");
}
```

C2974는 제네릭을 사용할 때도 발생할 수 있습니다.

```
// C2974b.cpp
// compile with: /clr
// C2974 expected
using namespace System;
generic <class T>
ref struct GCtype {};

generic <typename T>
void gf(T){}

int main() {
   // Delete the following 2 lines to resolve
   GCtype<"a">^ gc;
   gf<"a">("abc");

   // OK
   GCtype<int>^ gc;
   gf<String ^>("abc");
}
```