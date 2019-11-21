---
title: 컴파일러 경고 (수준 1) C4618
ms.date: 11/04/2016
f1_keywords:
- C4618
helpviewer_keywords:
- C4618
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
ms.openlocfilehash: fa9fc7d4a86ee686a9cd5d8d21412bd3346bcd80
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052572"
---
# <a name="compiler-warning-level-1-c4618"></a>컴파일러 경고 (수준 1) C4618

pragma 매개 변수에 빈 문자열이 포함 되어 있습니다. pragma가 무시 되었습니다.

**#Pragma**에 대 한 인수로 null 문자열이 지정 되었습니다.

Pragma가 인수 없이 처리 되었습니다.

다음 샘플에서는 C4618를 생성 합니다.

```cpp
// C4618.cpp
// compile with: /W1 /LD
#pragma code_seg("")   // C4618
```