---
title: 컴파일러 오류 C3198
ms.date: 11/04/2016
f1_keywords:
- C3198
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
ms.openlocfilehash: 61a3d14f9ad47edaa1e9b9f2b25d38b8dae7165c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243224"
---
# <a name="compiler-error-c3198"></a>컴파일러 오류 C3198

부동 소수점 pragma 잘못 사용 했습니다: fenv_access pragma는 precise 모드 에서만에서 작동

[fenv_access](../../preprocessor/fenv-access.md) pragma에서 사용한를 [/fp](../../build/reference/fp-specify-floating-point-behavior.md) 이외의 다른 위치로 설정 **/fp: 정확한**합니다.

다음 샘플에서는 C3198 오류가 생성 됩니다.

```
// C3198.cpp
// compile with: /fp:fast
#pragma fenv_access(on)   // C3198
```