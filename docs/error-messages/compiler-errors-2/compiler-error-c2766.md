---
title: 컴파일러 오류 C2766
ms.date: 11/04/2016
f1_keywords:
- C2766
helpviewer_keywords:
- C2766
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
ms.openlocfilehash: 87ea9f693265080d744746c6a8014b2b8b6db13a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257558"
---
# <a name="compiler-error-c2766"></a>컴파일러 오류 C2766

명시적 특수화 'specialization'가 이미 정의 되어

중복 된 명시적 특수화는 허용 되지 않습니다. 자세한 내용은 [명시적 함수 템플릿의 특수화](../../cpp/explicit-specialization-of-function-templates.md)합니다.

다음 샘플에서는 C2766 오류가 생성 됩니다.

```
// C2766.cpp
// compile with: /c
template<class T>
struct A {};

template<>
struct A<int> {};

template<>
struct A<int> {};   // C2766
// try the following line instead
// struct A<char> {};
```