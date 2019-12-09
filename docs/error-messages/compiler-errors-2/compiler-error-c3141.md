---
title: 컴파일러 오류 C3141
ms.date: 11/04/2016
f1_keywords:
- C3141
helpviewer_keywords:
- C3141
ms.assetid: b4fd65c3-50cc-46cd-8de0-6a6d24cb9cda
ms.openlocfilehash: 71f5a69bf96098b41bc2eb3945e1360955870657
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746190"
---
# <a name="compiler-error-c3141"></a>컴파일러 오류 C3141

' interface_name ': 인터페이스는 공용 상속만 지원 합니다.

[Interface (또는 __interface)](../../cpp/interface.md) 키워드로 정의 된 인터페이스는 공용 상속만 지원 합니다.

다음 샘플에서는 C3141를 생성 합니다.

```cpp
// C3141.cpp
__interface IBase {};
__interface IDerived1 : protected IBase {};  // C3141
__interface IDerived2 : private IBase {};    // C3141
```
