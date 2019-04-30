---
title: 컴파일러 오류 C2794
ms.date: 11/04/2016
f1_keywords:
- C2794
helpviewer_keywords:
- C2794
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
ms.openlocfilehash: 1e9d3ee84b72dc9a4f83337f79f38c0237e0b505
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360140"
---
# <a name="compiler-error-c2794"></a>컴파일러 오류 C2794

'function': 'class' 모든 직접 또는 간접 기본 클래스의 멤버가 아닙니다.

사용 하려는 [super](../../cpp/super.md) 존재 하지 않는 멤버 함수를 호출 합니다.

다음 샘플에서는 C2794

```
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