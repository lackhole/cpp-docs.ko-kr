---
title: 심각한 오류 C1191
ms.date: 11/04/2016
f1_keywords:
- C1191
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
ms.openlocfilehash: 7c6756dec29138af534278742d99c2f77109b1cc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747295"
---
# <a name="fatal-error-c1191"></a>심각한 오류 C1191

' d l l '은 전역 범위 에서만 가져올 수 있습니다.

/Clr 프로그래밍을 사용 하는 프로그램에 mscorlib.dll을 가져오는 명령은 네임 스페이스나 함수에 표시 될 수 없지만 전역 범위에는 표시 되어야 합니다.

다음 샘플에서는 C1191를 생성 합니다.

```cpp
// C1191.cpp
// compile with: /clr
namespace sample {
   #using <mscorlib.dll>   // C1191 not at global scope
}
```

가능한 해결 방법:

```cpp
// C1191b.cpp
// compile with: /clr /c
#using <mscorlib.dll>
namespace sample {}
```
