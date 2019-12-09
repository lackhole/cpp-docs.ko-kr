---
title: 컴파일러 오류 C2913
ms.date: 11/04/2016
f1_keywords:
- C2913
helpviewer_keywords:
- C2913
ms.assetid: c6cf6090-02e8-49a5-913f-5bc6f864b769
ms.openlocfilehash: 89f9e9393d0b4ee4075b24c20f0755a5317e94eb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761074"
---
# <a name="compiler-error-c2913"></a>컴파일러 오류 C2913

명시적 특수화 ' 선언 '은 클래스 템플릿의 특수화가 아닙니다.

템플릿이 아닌 클래스를 특수화할 수 없습니다.

다음 샘플에서는 C2913를 생성 합니다.

```cpp
// C2913.cpp
// compile with: /c
class X{};
template <class T> class Y{};

template<> class X<int> {};   // C2913
template<> class Y<int> {};
```
