---
title: 컴파일러 오류 C2537
ms.date: 11/04/2016
f1_keywords:
- C2537
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
ms.openlocfilehash: 0dfe9f88fcdfda1325150d480670777a4d42d896
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758634"
---
# <a name="compiler-error-c2537"></a>컴파일러 오류 C2537

' 지정자 ': 잘못 된 링크 사양입니다.

가능한 원인

1. 링크 지정 자가 지원 되지 않습니다. "C" 링크 지정자만 지원 됩니다.

1. 오버 로드 된 함수 집합에서 둘 이상의 함수에 대해 "C" 링크를 지정 했습니다. 이는 허용되지 않습니다.

다음 샘플에서는 C2537를 생성 합니다.

```cpp
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```
