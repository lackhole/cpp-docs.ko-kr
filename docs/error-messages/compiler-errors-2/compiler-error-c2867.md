---
title: 컴파일러 오류 C2867
ms.date: 11/04/2016
f1_keywords:
- C2867
helpviewer_keywords:
- C2867
ms.assetid: 63be26b2-d9ab-4f3d-a8b7-981ce3e4d6b9
ms.openlocfilehash: 42b931d208000cc35e65c7bff9c20901cef24713
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755059"
---
# <a name="compiler-error-c2867"></a>컴파일러 오류 C2867

' identifier ': 네임 스페이스가 아닙니다.

`using` 지시어는 네임 스페이스 이외의 항목에 적용 됩니다.

다음 샘플에서는 C2867를 생성 합니다.

```cpp
// C2867.cpp
// compile with: /c
namespace N {
   class X {};
}
using namespace N::X;   // C2867
```
