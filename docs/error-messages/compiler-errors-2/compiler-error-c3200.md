---
title: 컴파일러 오류 C3200
ms.date: 11/04/2016
f1_keywords:
- C3200
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
ms.openlocfilehash: 7f6b514231bcda18404e891e0acbe457c8f95146
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738780"
---
# <a name="compiler-error-c3200"></a>컴파일러 오류 C3200

' template ': 템플릿 매개 변수 ' parameter '의 템플릿 인수가 잘못 되었습니다. 클래스 템플릿이 필요 합니다.

잘못 된 인수를 클래스 템플릿에 전달 했습니다. 클래스 템플릿에는 매개 변수로 템플릿이 필요 합니다. 다음 예에서는 `Y<int, int> aY`를 호출 하면 C3200이 생성 됩니다. 첫 번째 매개 변수는 `Y<X, int> aY`와 같은 템플릿 이어야 합니다.

```cpp
// C3200.cpp
template<typename T>
class X
{
};

template<template<typename U> class T1, typename T2>
class Y
{
};

int main()
{
   Y<int, int> y;   // C3200
}
```
