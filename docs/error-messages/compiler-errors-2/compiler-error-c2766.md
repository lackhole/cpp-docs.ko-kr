---
title: 컴파일러 오류 C2766
ms.date: 11/04/2016
f1_keywords:
- C2766
helpviewer_keywords:
- C2766
ms.assetid: 8032f4ca-6827-4f04-9c61-c44643c85cc4
ms.openlocfilehash: 48faee02bba18754972954a2ca464417bd552758
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759804"
---
# <a name="compiler-error-c2766"></a>컴파일러 오류 C2766

명시적 특수화 ' 특수화 '는 이미 정의 되어 있습니다.

중복 된 명시적 특수화는 허용 되지 않습니다. 자세한 내용은 [함수 템플릿의 명시적 특수화](../../cpp/explicit-specialization-of-function-templates.md)를 참조 하세요.

다음 샘플에서는 C2766를 생성 합니다.

```cpp
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
