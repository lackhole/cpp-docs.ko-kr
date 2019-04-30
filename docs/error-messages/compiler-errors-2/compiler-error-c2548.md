---
title: 컴파일러 오류 C2548
ms.date: 11/04/2016
f1_keywords:
- C2548
helpviewer_keywords:
- C2548
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
ms.openlocfilehash: 2c680d86a0ea69d67f9e53a481f2f096f4cc7878
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353471"
---
# <a name="compiler-error-c2548"></a>컴파일러 오류 C2548

'class::member': 매개 변수 매개 변수에 대 한 기본 매개 변수 누락

기본 매개 변수 목록에 매개 변수가 없습니다. 매개 변수 목록에서 아무 곳 이나 기본 매개 변수를 제공 하는 경우 모든 후속 매개 변수에 대 한 기본 매개 변수를 정의 해야 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2548 오류가 생성 됩니다.

```
// C2548.cpp
// compile with: /c
void func( int = 1, int, int = 3);  // C2548

// OK
void func2( int, int, int = 3);
void func3( int, int = 2, int = 3);
```