---
title: 컴파일러 오류 C2970
ms.date: 11/04/2016
f1_keywords:
- C2970
helpviewer_keywords:
- C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
ms.openlocfilehash: 425d1bf50d56c4455ccd9292b300e744625d34c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256338"
---
# <a name="compiler-error-c2970"></a>컴파일러 오류 C2970

'class': 템플릿 매개 변수 'param': 'arg': 내부 링크가 있는 개체를 포함 하는 식을 비형식 인수로 사용할 수 없습니다

이름 또는 정적 변수의 주소를 템플릿 인수로 사용할 수 없습니다. 템플릿 클래스는 컴파일 타임에 평가할 수 있는 상수 값이 필요 합니다.

다음 샘플에서는 C2970 오류가 생성 됩니다.

```
// C2970.cpp
// compile with: /c
static int si;
// could declare nonstatic to resolve all errors
// int si;

template <int i>
class X {};

template <int *pi>
class Y {};

X<si> anX;   // C2970 cannot use static variable in templates

// this would also work
const int i = 10;
X<i> anX2;
```