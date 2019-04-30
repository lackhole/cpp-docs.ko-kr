---
title: 컴파일러 오류 C3737
ms.date: 11/04/2016
f1_keywords:
- C3737
helpviewer_keywords:
- C3737
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
ms.openlocfilehash: b6c2a85556e96ff6176e158b7d75a844bb5710d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327888"
---
# <a name="compiler-error-c3737"></a>컴파일러 오류 C3737

'delegate': 대리자에서 명시적 호출 규칙에 없을 수 있습니다

지정할 수 없습니다는 [호출 규칙이](../../cpp/calling-conventions.md) 에 대 한는 `delegate`합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3737 오류가 생성 됩니다.

```
// C3737a.cpp
// compile with: /clr
delegate void __stdcall MyFunc();   // C3737
// Try the following line instead.
// delegate void MyFunc();

int main() {
}
```
