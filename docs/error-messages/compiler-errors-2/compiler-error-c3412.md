---
title: 컴파일러 오류 C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: 7c16ffa37f4d7192956afae26c825b63add1bfdd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173459"
---
# <a name="compiler-error-c3412"></a>컴파일러 오류 C3412

'template': 현재 범위에서 템플릿을 특수화할 수 없습니다.

전역에 클래스 범위 또는 네임 스페이스 범위에서 템플릿을 특수화할 수 없습니다.

## <a name="example"></a>예제

다음 샘플 C3412를 생성합니다.

```
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

## <a name="example"></a>예제

다음 샘플에서는 가능한 해결 방법을 보여 줍니다.

```
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```