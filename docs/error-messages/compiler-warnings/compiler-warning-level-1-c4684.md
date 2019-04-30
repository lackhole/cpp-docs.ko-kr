---
title: 컴파일러 경고(수준 1) C4684
ms.date: 11/04/2016
f1_keywords:
- C4684
helpviewer_keywords:
- C4684
ms.assetid: e95f1a83-2784-4b05-ae94-12148e056e26
ms.openlocfilehash: 8ba3d75ecb370ac86c9a6ab47f05dd49fc12ba23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374406"
---
# <a name="compiler-warning-level-1-c4684"></a>컴파일러 경고(수준 1) C4684

' attribute': 경고!! 특성으로 인해 잘못 된 코드가 생성 될 수 있습니다: 주의 하 여 사용

일반적으로 사용 하지 않아야 하는 특성을 사용 합니다.

다음 샘플에서는 C4684 오류가 생성 됩니다.

```
// C4684.cpp
// compile with: /W1 /LD
[module(name="xx")]; // C4684 expected
[no_injected_text];
```