---
title: 컴파일러 오류 C2477
ms.date: 11/04/2016
f1_keywords:
- C2477
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
ms.openlocfilehash: aa276ea839f11574609b183d78b46e08581a1b51
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743655"
---
# <a name="compiler-error-c2477"></a>컴파일러 오류 C2477

' member ': 정적 데이터 멤버는 파생 클래스를 통해 초기화할 수 없습니다.

템플릿 클래스의 정적 데이터 멤버가 잘못 초기화 되었습니다. 이는 ISO C++ 표준을 준수 하기 위해 Visual Studio .net C++ 2003 이전 버전의 Microsoft 컴파일러에 대 한 주요 변경 내용입니다.

다음 샘플에서는 C2477를 생성 합니다.

```cpp
// C2477.cpp
// compile with: /Za /c
template <class T>
struct S {
   static int n;
};

struct X {};
struct A: S<X> {};

int A::n = 0;   // C2477

template<>
int S<X>::n = 0;
```
