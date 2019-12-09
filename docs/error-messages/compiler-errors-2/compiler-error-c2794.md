---
title: 컴파일러 오류 C2794
ms.date: 11/04/2016
f1_keywords:
- C2794
helpviewer_keywords:
- C2794
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
ms.openlocfilehash: 8163a52cd95638e9d24d587f78fb9e20a0da2bb6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739274"
---
# <a name="compiler-error-c2794"></a>컴파일러 오류 C2794

' function ': ' class '의 직접 또는 간접 기본 클래스의 멤버가 아닙니다.

[Super](../../cpp/super.md) 를 사용 하 여 존재 하지 않는 멤버 함수를 호출 하려고 했습니다.

다음 샘플에서는 C2794를 생성 합니다.

```cpp
// C2794.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::f();  // C2794
   }
};
```
