---
title: 컴파일러 오류 C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: ad241b656464746333760cfcbc134c91e49bf44e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761418"
---
# <a name="compiler-error-c3412"></a>컴파일러 오류 C3412

' template ': 현재 범위에서 템플릿을 특수화할 수 없습니다.

템플릿은 전역 또는 네임 스페이스 범위 에서만 클래스 범위에서 특수화할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3412를 생성 합니다.

```cpp
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

## <a name="example"></a>예제

다음 샘플에서는 가능한 해결 방법을 보여 줍니다.

```cpp
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```
