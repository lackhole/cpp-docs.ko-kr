---
title: 컴파일러 오류 C2765
ms.date: 11/04/2016
f1_keywords:
- C2765
helpviewer_keywords:
- C2765
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
ms.openlocfilehash: 7b34bd8b352e8872722e9402d8d0113ae6157292
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257649"
---
# <a name="compiler-error-c2765"></a>컴파일러 오류 C2765

'function': 함수 템플릿의 명시적 특수화는 기본 인수를 가질 수 없습니다.

기본 인수는 함수 템플릿의 명시적 특수화에는 허용 되지 않습니다. 자세한 내용은 [명시적 함수 템플릿의 특수화](../../cpp/explicit-specialization-of-function-templates.md)합니다.

다음 샘플에서는 C2765를 생성합니다.

```
// C2765.cpp
template<class T> void f(T t) {};

template<> void f<char>(char c = 'a') {}   // C2765
// try the following line instead
// template<> void f<char>(char c) {}
```