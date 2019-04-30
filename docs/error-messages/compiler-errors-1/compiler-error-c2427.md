---
title: 컴파일러 오류 C2427
ms.date: 11/04/2016
f1_keywords:
- C2427
helpviewer_keywords:
- C2427
ms.assetid: a7d421af-6180-40b4-b7a6-9f3bc7dfaaf9
ms.openlocfilehash: b794b90a476f7712c80e7617ec3c0696afb290ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402829"
---
# <a name="compiler-error-c2427"></a>컴파일러 오류 C2427

'class':이 범위에서 클래스를 정의할 수 없습니다.

중첩된 클래스를 정의 하려고 했습니다 하지만 중첩 된 클래스는 대부분의 포함 된 클래스가 아닌 기본 클래스의 멤버입니다.

다음 샘플에서는 C2427 오류가 생성 됩니다.

```
// C2427.cpp
// compile with: /c
template <class T>
struct S {
   struct Inner;
};

struct Y : S<int> {};

struct Y::Inner {};   // C2427

// OK
template<typename T>
struct S<T>::Inner {};
```