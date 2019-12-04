---
title: 컴파일러 오류 C2436
ms.date: 11/04/2016
f1_keywords:
- C2436
helpviewer_keywords:
- C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
ms.openlocfilehash: 2fd910f18e8d863c6894a7fe99449d5ba213bf61
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744383"
---
# <a name="compiler-error-c2436"></a>컴파일러 오류 C2436

' identifier ': 생성자 이니셜라이저 목록에 멤버 함수 또는 중첩 클래스가 있습니다.

생성자 이니셜라이저 목록의 멤버 함수 또는 로컬 클래스를 초기화할 수 없습니다.

다음 샘플에서는 C2436를 생성 합니다.

```cpp
// C2436.cpp
struct S{
   int f();
   struct Inner{
      int i;
   };
   S():f(10), Inner(0){}   // C2436
};
```
