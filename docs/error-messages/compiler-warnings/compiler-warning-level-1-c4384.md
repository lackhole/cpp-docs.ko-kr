---
title: 컴파일러 경고 (수준 1) C4384
ms.date: 11/04/2016
f1_keywords:
- C4384
helpviewer_keywords:
- C4384
ms.assetid: fafa8eb2-cbfc-4edb-8b0f-511ff5d37ac0
ms.openlocfilehash: 467f15522503d16d3b023661ee339c986f74ddec
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73964881"
---
# <a name="compiler-warning-level-1-c4384"></a>컴파일러 경고 (수준 1) C4384

\#pragma ' make_public '은 (는) 전역 범위 에서만 사용 해야 합니다.

[Make_public](../../preprocessor/make-public.md) pragma가 제대로 적용 되지 않았습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4384를 생성 합니다.

```cpp
// C4384.cpp
// compile with: /c /W1
namespace n {
   #pragma make_public(N::C)   // C4384
   namespace N {
      class C {};
   }
}
```