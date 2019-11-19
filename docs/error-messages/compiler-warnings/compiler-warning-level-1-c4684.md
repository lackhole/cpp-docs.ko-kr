---
title: 컴파일러 경고 (수준 1) C4684
ms.date: 11/04/2016
f1_keywords:
- C4684
helpviewer_keywords:
- C4684
ms.assetid: e95f1a83-2784-4b05-ae94-12148e056e26
ms.openlocfilehash: f6ce86cc297a6529d58573f3e7d906f51771013b
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052513"
---
# <a name="compiler-warning-level-1-c4684"></a>컴파일러 경고 (수준 1) C4684

' attribute ': 경고 특성으로 인해 잘못 된 코드가 생성 될 수 있습니다. 주의 해 서 사용 하세요.

일반적으로 사용 하지 않아야 하는 특성을 사용 했습니다.

다음 샘플에서는 C4684를 생성 합니다.

```cpp
// C4684.cpp
// compile with: /W1 /LD
[module(name="xx")]; // C4684 expected
[no_injected_text];
```