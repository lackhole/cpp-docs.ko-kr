---
title: 컴파일러 오류 C2477
ms.date: 11/04/2016
f1_keywords:
- C2477
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
ms.openlocfilehash: 27db194cb308d711a259127b628c60b4d10b94ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383232"
---
# <a name="compiler-error-c2477"></a>컴파일러 오류 C2477

'member': 파생된 클래스를 통해 정적 데이터 멤버를 초기화할 수 없습니다

템플릿 클래스의 정적 데이터 멤버를 잘못 초기화 되었습니다. 이 시각적 개체의 버전을 사용 하 여 주요 변경 내용 C++ ISO를 준수 하기 위해 Visual Studio.NET 2003 이전 컴파일러 C++ 표준.

다음 샘플에서는 C2477 오류가 생성 됩니다.

```
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