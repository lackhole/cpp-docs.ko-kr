---
title: 컴파일러 오류 C2493
ms.date: 11/04/2016
f1_keywords:
- C2493
helpviewer_keywords:
- C2493
ms.assetid: 68316cd5-682b-49c3-b6ea-23c4e5d296cf
ms.openlocfilehash: d5e64b2586803f7463582710721d2cb5c0eac200
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360868"
---
# <a name="compiler-error-c2493"></a>컴파일러 오류 C2493

__based의

`__based` 식에 대 한 포인터 기반으로 해야 합니다.

다음 샘플에서는 C2493 오류가 생성 됩니다.

```
// C2493.cpp
// compile with: /c
char mybase;
int __based(mybase) ptr;   // C2493

// OK
char * mybase;
int __based(mybase) * ptr;
```