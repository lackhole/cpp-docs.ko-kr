---
title: 컴파일러 오류 C2337
ms.date: 09/19/2019
f1_keywords:
- C2337
helpviewer_keywords:
- C2337
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
ms.openlocfilehash: bf9b3e782804add13aeaef0e6672d2dd66d193be
ms.sourcegitcommit: f907b15f50a6b945d0b87c03af0050946157d701
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71158769"
---
# <a name="compiler-error-c2337"></a>컴파일러 오류 C2337

> '*attribute-name*': 특성을 찾을 수 없습니다.

코드가이 컨텍스트에서 지원 되지 않는 특성을 사용 합니다. 또는이 버전의 컴파일러에서는 특성을 사용할 수 없습니다. 이 문제를 해결 하려면 지원 되지 않는 특성을 제거 합니다.

다음 샘플에서는 C2337을 생성합니다.

```cpp
// C2337.cpp
// compile with: /c
[emitidl];
[module(name="x")];
[grasshopper]   // C2337, not a supported attribute
class a{};
```
