---
title: 컴파일러 오류 C2142
ms.date: 11/04/2016
f1_keywords:
- C2142
helpviewer_keywords:
- C2142
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
ms.openlocfilehash: eda60204e07fd025a8c62b19de70e8204f9f80f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353588"
---
# <a name="compiler-error-c2142"></a>컴파일러 오류 C2142

함수 선언이 서로 다릅니다. 그 중 하나에 지정 하는 가변 매개 변수

하나의 함수 선언에 가변 매개 변수 목록을 포함합니다. 다른 선언 되지 않습니다. ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md))만 합니다.

다음 샘플에서는 C2142 오류가 생성 됩니다.

```
// C2142.c
// compile with: /Za /c
void func();
void func( int, ... );   // C2142
void func2( int, ... );   // OK
```