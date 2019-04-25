---
title: 컴파일러 오류 C2159
ms.date: 11/04/2016
f1_keywords:
- C2159
helpviewer_keywords:
- C2159
ms.assetid: 925a2cbd-43c9-45ee-a373-84004350b380
ms.openlocfilehash: fd845fffe9778e51af7db77144607233ed9ddefd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174850"
---
# <a name="compiler-error-c2159"></a>컴파일러 오류 C2159

스토리지 클래스를 두 개 이상 지정했습니다.

선언에 스토리지 클래스가 둘 이상 포함되어 있습니다.

다음 샘플에서는 C2159를 생성합니다.

```
// C2159.cpp
// compile with: /c
static int i;   // OK
extern static int i;   // C2159
```