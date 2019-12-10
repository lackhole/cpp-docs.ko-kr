---
title: 컴파일러 경고(수준 4) C4515
ms.date: 11/04/2016
f1_keywords:
- C4515
helpviewer_keywords:
- C4515
ms.assetid: 167b5177-3f89-418b-b6c8-7de634f6b28f
ms.openlocfilehash: 442852ba971fb1b9a687d5ccf2b2857aa9deab50
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990729"
---
# <a name="compiler-warning-level-4-c4515"></a>컴파일러 경고(수준 4) C4515

' namespace ': 네임 스페이스가 자신을 사용 합니다.

네임 스페이스는 재귀적으로 사용 됩니다.

다음 샘플에서는 C4515를 생성 합니다.

```cpp
// C4515.cpp
// compile with: /W4
namespace A
{
   using namespace A; // C4515
}

int main()
{
}
```
