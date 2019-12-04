---
title: 컴파일러 오류 C2757
ms.date: 11/04/2016
f1_keywords:
- C2757
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
ms.openlocfilehash: a9f4661495e0fa5219a517b6f6ca410323a77269
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759531"
---
# <a name="compiler-error-c2757"></a>컴파일러 오류 C2757

' symbol ': 이름이 같은 기호가 이미 있으므로이 이름을 네임 스페이스 이름으로 사용할 수 없습니다.

현재 컴파일에서 네임 스페이스 식별자로 사용 되는 기호는 이미 참조 된 어셈블리에서 사용 되 고 있습니다.

다음 샘플에서는 C2757를 생성 합니다.

```cpp
// C2757a.cpp
// compile with: /clr /LD
public ref class Nes {};
```

그리고

```cpp
// C2757b.cpp
// compile with: /clr /c
#using <C2757a.dll>

namespace Nes {    // C2757
// try the following line instead
// namespace Nes2 {
   public ref class X {};
}
```
