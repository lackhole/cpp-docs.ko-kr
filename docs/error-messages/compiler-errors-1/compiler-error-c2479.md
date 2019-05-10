---
title: 컴파일러 오류 C2479
ms.date: 11/04/2016
f1_keywords:
- C2479
helpviewer_keywords:
- C2479
ms.assetid: c74c7869-e65b-4ca1-b6fa-eb39fed4458a
ms.openlocfilehash: 8b3b226ccbe42ec88ed92c64b97256d80a983254
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383264"
---
# <a name="compiler-error-c2479"></a>컴파일러 오류 C2479

'identifier': 'allocate ()'는 정적 범위의 데이터 항목에 대 한 유효한만

`__declspec( allocate())` 구문은 정적 데이터에만 사용할 수 있습니다.

다음 샘플에서는 C2479 오류가 생성 됩니다.

```
// C2479.cpp
// compile with: /c
#pragma section("mycode", read)
static __declspec(allocate("mycode")) void DoNothing() {}   // C2479
__declspec(allocate("mycode"))  int i = 0;   // OK
```