---
title: 컴파일러 오류 C3198
ms.date: 11/04/2016
f1_keywords:
- C3198
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
ms.openlocfilehash: b9e0ce4a84b312e3a9277898b3fc264ea3ae22bb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739157"
---
# <a name="compiler-error-c3198"></a>컴파일러 오류 C3198

부동 소수점 pragma를 잘못 사용 했습니다. fenv_access pragma는 정확한 모드 에서만 작동 합니다.

[fenv_access](../../preprocessor/fenv-access.md) pragma가 **/fp: precise**이외의 [/fp](../../build/reference/fp-specify-floating-point-behavior.md) 설정에서 사용 되었습니다.

다음 샘플에서는 C3198를 생성 합니다.

```cpp
// C3198.cpp
// compile with: /fp:fast
#pragma fenv_access(on)   // C3198
```
