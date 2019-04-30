---
title: 컴파일러 오류 C2436
ms.date: 11/04/2016
f1_keywords:
- C2436
helpviewer_keywords:
- C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
ms.openlocfilehash: 335d4a304e16814243894c9524a9e4a2a7356110
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375108"
---
# <a name="compiler-error-c2436"></a>컴파일러 오류 C2436

'identifier': 멤버 함수 또는 생성자 이니셜라이저 목록에서 중첩된 클래스

멤버 함수 또는 생성자 이니셜라이저 목록에서 로컬 클래스를 초기화할 수 없습니다.

다음 샘플에서는 C2436 오류가 생성 됩니다.

```
// C2436.cpp
struct S{
   int f();
   struct Inner{
      int i;
   };
   S():f(10), Inner(0){}   // C2436
};
```