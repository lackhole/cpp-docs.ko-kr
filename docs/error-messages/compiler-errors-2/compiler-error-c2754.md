---
title: 컴파일러 오류 C2754
ms.date: 11/04/2016
f1_keywords:
- C2754
helpviewer_keywords:
- C2754
ms.assetid: 1cab66c5-da9d-4b81-b7fb-9cdc48ff1ccc
ms.openlocfilehash: cfe6f8faa1b00faf32ae53e6c25c23532c9f3a3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228527"
---
# <a name="compiler-error-c2754"></a>컴파일러 오류 C2754

'specialization': 부분 특수화는 종속적 비형식 템플릿 매개 변수를 사용할 수 없습니다

부분적으로 종속적 비형식 템플릿 매개 변수가 있는 템플릿 클래스 특수화 하려고 했습니다. 이것은 허용되지 않습니다.

다음 샘플에서는 C2754를 생성합니다.

```
// C2754.cpp
// compile with: /c

template<class T, T t>
struct A {};

template<class T, int N>
struct B {};

template<class T> struct A<T,5> {};   // C2754
template<> struct A<int,5> {};   // OK
template<class T> struct B<T,5> {};   // OK
```