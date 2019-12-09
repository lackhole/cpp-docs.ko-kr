---
title: 컴파일러 오류 C3852
ms.date: 11/04/2016
f1_keywords:
- C3852
helpviewer_keywords:
- C3852
ms.assetid: 194e5c5e-0dfb-414e-86db-791c11eb610c
ms.openlocfilehash: f264333d802967d0350caa8ab4ba4925ffe019af
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754877"
---
# <a name="compiler-error-c3852"></a>컴파일러 오류 C3852

' member ' 형식 ' type ': 집합체 초기화에서이 멤버를 초기화할 수 없습니다.

집계 초기화에서 기본 초기화를 받을 수 없는 데이터 멤버에 대 한 집계 초기화의 일부로 기본 초기화를 할당 하려고 했습니다.

다음 샘플에서는 C3852를 생성 합니다.

```cpp
// C3852.cpp
struct S
{
   short s;
};

struct S1
{
   int i;
   const S s;
};

struct S2
{
   int i;
   char & rc;
};

int main()
{
   S1 s1 = { 1 };   // C3852 const member
   // try the following line instead
   // S1 s1 = { 1, 2 };

   S2 s2 = { 2 };   // C3852 reference member
   // try the following line instead
   // char c = 'a';
   S2 s2 = { 2, c };
}
```
