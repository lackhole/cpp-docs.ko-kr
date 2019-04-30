---
title: 컴파일러 오류 C2908
ms.date: 11/04/2016
f1_keywords:
- C2908
helpviewer_keywords:
- C2908
ms.assetid: 49cd2a21-cad8-4ba0-9a0b-3a0190d9344c
ms.openlocfilehash: f798be5ef93eb3f072036888b800fa4008fa2de9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408565"
---
# <a name="compiler-error-c2908"></a>컴파일러 오류 C2908

명시적 특수화 이미 인스턴스화된 'template'

기본 템플릿의 특수화는 명시적 특수화는 그것이 전에 발생합니다.

다음 샘플에서는 C2908를 생성합니다.

```
// C2908.cpp
// compile with: /c
template<class T> class X {};

void f() {
X<int> x;   //specialization and instantiation
            //of X<int>
}

template<> class X<int> {}  // C2908, explicit specialization
```