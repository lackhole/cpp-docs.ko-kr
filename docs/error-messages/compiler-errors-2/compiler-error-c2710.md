---
title: 컴파일러 오류 C2710
ms.date: 11/04/2016
f1_keywords:
- C2710
helpviewer_keywords:
- C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
ms.openlocfilehash: 54d501d43652bb8e54092d44042a9525ef6f708f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160915"
---
# <a name="compiler-error-c2710"></a>컴파일러 오류 C2710

'construct': '__declspec(modifier)'에 대 한 포인터를 반환 하는 함수에만 적용 될 수 있습니다

반환 값이 함수는 유일한 구문입니다 `modifier` 적용할 수 있습니다.

다음 샘플에서는 C2710 오류가 생성 됩니다.

```
// C2710.cpp
__declspec(restrict) void f();   // C2710
// try the following line instead
__declspec(restrict) int * g();
```