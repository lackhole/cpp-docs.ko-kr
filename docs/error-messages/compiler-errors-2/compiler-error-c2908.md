---
title: 컴파일러 오류 C2908
ms.date: 11/04/2016
f1_keywords:
- C2908
helpviewer_keywords:
- C2908
ms.assetid: 49cd2a21-cad8-4ba0-9a0b-3a0190d9344c
ms.openlocfilehash: ca07ef3c8240e6a55137e07bccbfc61ca8d96636
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750561"
---
# <a name="compiler-error-c2908"></a>컴파일러 오류 C2908

명시적 특수화 ' template '이 이미 인스턴스화 되었습니다.

기본 템플릿의 특수화는 명시적 특수화 이전에 발생 합니다.

다음 샘플에서는 C2908를 생성 합니다.

```cpp
// C2908.cpp
// compile with: /c
template<class T> class X {};

void f() {
X<int> x;   //specialization and instantiation
            //of X<int>
}

template<> class X<int> {}  // C2908, explicit specialization
```
