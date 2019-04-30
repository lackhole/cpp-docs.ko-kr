---
title: 컴파일러 오류 C2372
ms.date: 11/04/2016
f1_keywords:
- C2372
helpviewer_keywords:
- C2372
ms.assetid: 406bea63-c8d3-4231-9d26-c70af6980840
ms.openlocfilehash: db13a6bc108588fbbd9c15e2bcc647bea073a333
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339028"
---
# <a name="compiler-error-c2372"></a>컴파일러 오류 C2372

'identifier': 재정의 다양 한 간접 참조

식별자는 다른 파생된 형식을 사용 하 여 이미 정의 되었습니다.

다음 샘플에서는 C2326을 생성합니다.

```
// C2372.cpp
// compile with: /c
extern int *fp;
extern int fp[];   // C2372
extern int fp2[];   // OK
```