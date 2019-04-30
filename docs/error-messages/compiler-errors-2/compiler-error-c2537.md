---
title: 컴파일러 오류 C2537
ms.date: 11/04/2016
f1_keywords:
- C2537
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
ms.openlocfilehash: 437727b334087aef496dbb0a1f3f1c8cf2b45458
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345594"
---
# <a name="compiler-error-c2537"></a>컴파일러 오류 C2537

'specifier': 링크 사양이 올바르지 않습니다

가능한 원인:

1. 링크 지정 자가 지원 되지 않습니다. "C" 링크 지정자만 지원 됩니다.

1. "C" 링크가 둘 이상의 함수 오버 로드 된 함수 집합에 대해 지정 됩니다. 이것은 허용되지 않습니다.

다음 샘플에서는 C2537를 생성합니다.

```
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```