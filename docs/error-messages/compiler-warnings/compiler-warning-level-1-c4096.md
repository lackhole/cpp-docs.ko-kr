---
title: 컴파일러 경고 (수준 1) C4096
ms.date: 11/04/2016
f1_keywords:
- C4096
helpviewer_keywords:
- C4096
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
ms.openlocfilehash: 287465e9a3f5681f459f0823a4409b0906309a55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280466"
---
# <a name="compiler-warning-level-1-c4096"></a>컴파일러 경고 (수준 1) C4096

'a': 인터페이스는 COM 인터페이스 아닙니다. IDL로 내보내지 않습니다.

COM 인터페이스로 계획 했던 인터페이스 정의 COM 인터페이스로 정의 되지 않은 및 따라서 내보내지 않습니다 IDL 파일에 있습니다.

참조 [인터페이스 특성](../../windows/attributes/interface-attributes.md) 인터페이스는 COM 인터페이스를 나타내는 목록 특성에 대 한 합니다.

다음 샘플에서는 C4096 오류가 생성 됩니다.

```
// C4096.cpp
// compile with: /W1 /LD
#include "windows.h"
[module(name="xx")];

// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct b : a
{
};   // C4096, remove coclass or uncomment object
```