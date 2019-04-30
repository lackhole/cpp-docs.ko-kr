---
title: 컴파일러 오류 C3200
ms.date: 11/04/2016
f1_keywords:
- C3200
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
ms.openlocfilehash: 7eb0c00f4f4c5c59766bf305acfef89e12a6cfb1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402777"
---
# <a name="compiler-error-c3200"></a>컴파일러 오류 C3200

'template': 템플릿 매개 변수 'parameter' 인수가 잘못 된 템플릿 클래스 템플릿이 필요

클래스 템플릿에 잘못 된 인수를 전달 합니다. 클래스 템플릿을에서는 템플릿 매개 변수로 사용 합니다. 다음 예에서 호출 `Y<int, int> aY` C3200를 생성 합니다. 첫 번째 매개 변수 해야 템플릿을 같은 `Y<X, int> aY`합니다.

```
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