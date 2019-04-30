---
title: 컴파일러 오류 C2073
ms.date: 11/04/2016
f1_keywords:
- C2073
helpviewer_keywords:
- C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
ms.openlocfilehash: 2b45d512224ec32459e6da040a6abb0211278e78
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303322"
---
# <a name="compiler-error-c2073"></a>컴파일러 오류 C2073

'identifier': 부분적으로 초기화 된 배열의 요소에는 기본 생성자가 있어야 합니다.

사용자 정의 형식 또는 상수 배열에 대 한 이니셜라이저를 너무 적게 지정 되었습니다. 배열 멤버에 대 한 명시적 이니셜라이저 및 해당 생성자는 지정 하지 않으면 기본 생성자를 제공 해야 합니다.

다음 샘플에서는 C2073 오류가 생성 됩니다.

```
// C2073.cpp
class A {
public:
   A( int );   // constructor for ints only
};
A a[3] = { A(1), A(2) };   // C2073, no default constructor
```

```
// C2073b.cpp
// compile with: /c
class B {
public:
   B();   // default constructor declared
   B( int );
};
B b[3] = { B(1), B(2) };   // OK
```