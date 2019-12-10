---
title: 컴파일러 오류 C2765
ms.date: 11/04/2016
f1_keywords:
- C2765
helpviewer_keywords:
- C2765
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
ms.openlocfilehash: 0c646d0ab28b97b546721180e46b0f22ea376f7d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759830"
---
# <a name="compiler-error-c2765"></a>컴파일러 오류 C2765

' function ': 함수 템플릿의 명시적 특수화에는 기본 인수를 사용할 수 없습니다.

함수 템플릿의 명시적 특수화에는 기본 인수를 사용할 수 없습니다. 자세한 내용은 [함수 템플릿의 명시적 특수화](../../cpp/explicit-specialization-of-function-templates.md)를 참조 하세요.

다음 샘플에서는 C2765를 생성 합니다.

```cpp
// C2765.cpp
template<class T> void f(T t) {};

template<> void f<char>(char c = 'a') {}   // C2765
// try the following line instead
// template<> void f<char>(char c) {}
```
