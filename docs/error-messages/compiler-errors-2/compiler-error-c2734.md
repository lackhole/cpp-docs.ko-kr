---
title: 컴파일러 오류 C2734
ms.date: 11/04/2016
f1_keywords:
- C2734
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
ms.openlocfilehash: c20fcc7673c00ea7cfad32bdc3feae042f1f9086
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350769"
---
# <a name="compiler-error-c2734"></a>컴파일러 오류 C2734

'identifier': 경우 하지 extern const 개체를 초기화 해야 합니다

식별자 선언 `const` 되지만 초기화 되지는 않습니다 또는 `extern`합니다.

다음 샘플에서는 C2734 오류가 생성 됩니다.

```
// C2734.cpp
const int j;   // C2734
extern const int i;   // OK, declared as extern
```