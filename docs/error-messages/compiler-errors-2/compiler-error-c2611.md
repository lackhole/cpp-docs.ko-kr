---
title: 컴파일러 오류 C2611
ms.date: 11/04/2016
f1_keywords:
- C2611
helpviewer_keywords:
- C2611
ms.assetid: 3f2d5253-f24f-4724-83d0-6b2aa6a4e551
ms.openlocfilehash: b3c043f8aa8b6fcf4f63e9432e4a1b7222528285
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243312"
---
# <a name="compiler-error-c2611"></a>컴파일러 오류 C2611

'token': 잘못 된 다음 ' ~' 식별자가 필요

토큰을 식별자가 아닙니다.

다음 샘플에서는 C2611를 생성합니다.

```
// C2611.cpp
// compile with: /c
class C {
   C::~operator int();   // C2611
   ~C();   // OK
};
```