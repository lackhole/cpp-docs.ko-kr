---
title: 컴파일러 오류 C3118
ms.date: 11/04/2016
f1_keywords:
- C3118
helpviewer_keywords:
- C3118
ms.assetid: 40fbe681-8868-4cb2-a2b2-4db4449319a7
ms.openlocfilehash: 876b007ce7e537a8871147637188b10a100e997b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741120"
---
# <a name="compiler-error-c3118"></a>컴파일러 오류 C3118

' interface ': 인터페이스가 가상 상속을 지원 하지 않습니다.

인터페이스에서 실질적으로 상속 하려고 했습니다. 예를 들어 입니다.

```cpp
// C3118.cpp
__interface I1 {
};

__interface I2 : virtual I1 {   // C3118
};
```

이 오류를 생성 합니다.
